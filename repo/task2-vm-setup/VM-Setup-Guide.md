# Task 2 — Virtual Machine Setup (AWS EC2, Free Tier)

**What you will build:** a virtual server on Amazon EC2 (Amazon Linux 2023, `t3.micro`)
running the **nginx** web server, visible in your browser via its public IP.

**Time:** ~30–45 minutes (mostly waiting on the AWS signup if you don't have an account).

**Cost safety (read this — AWS changed its free tier in 2025):** New AWS accounts no
longer get the old "750 hrs/month for 12 months" deal. Instead you get the **Free Plan**:
**$100 in credits at signup + up to $100 more** for completing onboarding tasks
($200 total), valid **6 months**. Key point from AWS: **on the Free Plan you cannot be
charged** — no charges unless you *choose* to upgrade to a Paid plan. This whole task
(2–3 hours of a small VM) costs **well under $1 in credits**, so your $200 covers it
hundreds of times over. The one rule: **terminate the instance when you're done**
(don't leave it running for weeks — a running VM burns a few cents/hour in credits,
mostly the public IPv4 address).

---

## Part A — Create your AWS account (skip if you already have one)

1. Go to **aws.amazon.com** → **Create a free account**.
2. Enter your email, choose a password, pick an account name (e.g. `arya-personal`).
3. Fill contact info → verify your phone via OTP → choose the **Free Plan**
   (not the Paid plan — the Free Plan is the one that can't charge you).
4. Sign in to the **AWS Management Console**.
5. Confirm your credits: search **Billing** → **Credits** — you should see
   **$100** (earn up to $100 more via the onboarding tasks on the console home page).

### A1. Set a $0 billing alarm (2 minutes, optional safety net)

On the Free Plan you can't be charged anyway, but this is good hygiene:

1. In the console search bar type **Billing** → open **Billing and Cost Management**.
2. Left menu → **Billing preferences** → tick **Receive Billing Alerts** → Save.
3. Search **CloudWatch** → left menu **Alarms** → **Create alarm** →
   **Select metric** → **Billing** → **Total Estimated Charge** → pick **USD**.
4. Statistic: Maximum, Period: 6 hours, Threshold: **Greater than 0**, value **0**.
5. Notification: create a new SNS topic, enter your email → Create alarm.
6. Confirm the subscription email AWS sends you.

📸 **Screenshot 0 (optional but good):** the billing alarm in CloudWatch Alarms list.

---

## Part B — Launch the EC2 instance

1. In the console search bar type **EC2** → open it.
2. Make sure the region (top-right, next to your name) is **Asia Pacific (Mumbai) ap-south-1**.
   (Any region works; Mumbai is closest to you.)
3. Click **Launch instance**.
4. **Name:** `codeorbit-vm`
5. **Application and OS Images:** keep **Amazon Linux 2023 AMI** (look for a
   "Free Tier eligible" tag).
6. **Instance type:** choose **t3.micro** (current Free Plan eligible family;
   if the console tags a different type as Free Tier eligible, pick that one).
7. **Key pair:** click **Create new key pair** → name it `codeorbit-key` → keep
   **.pem** → **Create key pair**. Your browser downloads `codeorbit-key.pem` —
   keep it somewhere safe (you likely won't need it thanks to Instance Connect).
8. **Network settings** → click **Edit**:
   - Auto-assign public IP: **Enable**
   - Firewall (security groups): **Create security group**
   - Tick **Allow SSH traffic from** → choose **My IP**
   - Tick **Allow HTTP traffic from the internet**
9. **Configure storage:** keep **8 GiB gp3** (free tier includes 30 GB).
10. Right panel **Summary**: check "Free tier eligible" tags → click **Launch instance** →
    **View all instances**.

Wait ~1 minute until **Instance state** = **Running** and **Status check** = **2/2 checks passed**.

📸 **Screenshot 1:** the EC2 Instances list showing `codeorbit-vm` **Running**,
with the **Public IPv4 address** column visible.

---

## Part C — Connect to the VM (browser, no key needed)

1. Tick the checkbox next to `codeorbit-vm` → click **Connect** (top-right).
2. Keep the **EC2 Instance Connect** tab → **Connect**.
3. A terminal opens in your browser, logged in as `ec2-user`. Run:

```
whoami
```

It should print `ec2-user`. You are now inside your cloud VM.

---

## Part D — Install the nginx web server

Paste these commands **one block at a time** into the terminal, pressing Enter after each:

```bash
sudo dnf update -y
```

```bash
sudo dnf install -y nginx
```

```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

```bash
systemctl is-active nginx
```

The last command must print **`active`**. If it does, your web server is running.

📸 **Screenshot 2:** the terminal showing the `dnf install` output and
`systemctl is-active nginx` printing `active`.

---

## Part E — See it in your browser

1. Back in the EC2 Instances list, copy the **Public IPv4 address**
   (looks like `13.232.45.178`).
2. Open `http://<that-IP>` in a new browser tab.
3. You should see the **"Welcome to nginx!"** page.

📸 **Screenshot 3:** the browser showing the nginx welcome page, with the public IP
visible in the address bar.

---

## Part F — Clean up (important)

- **Right after screenshots:** select the instance → **Instance state → Stop instance**.
  A stopped instance burns no per-hour credits (a *running* one costs a few cents/hour,
  mostly for the public IPv4 address — that's why we don't leave it on).
- **After Task 2's report is assembled:** select the instance →
  **Instance state → Terminate instance** to delete it permanently.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Browser shows nothing / times out | Security group missing the HTTP rule → EC2 → Security → check inbound rules allow port 80 from 0.0.0.0/0 |
| "Connection refused" on Instance Connect | Status checks not yet 2/2 — wait a minute and retry |
| `dnf` command not found | You picked the wrong AMI — relaunch and choose **Amazon Linux 2023** |

---

## What to send back to Muse

The **4 screenshots** (0 optional, 1–3 required) plus your instance's public IP.
Muse will assemble them into your Task 2 setup report.
