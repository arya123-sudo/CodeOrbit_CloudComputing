# Task 3 — Cloud Storage & File Management (Amazon S3, Free Tier)

**What you will build:** an S3 bucket in the Mumbai region holding organized
folders and files, with access permissions configured and demonstrated.

**Time:** ~20–30 minutes. **Prerequisite:** an AWS account (Part A of the Task 2 guide).

**Cost safety:** S3's 5 GB of standard storage is **always-free**, plus 20,000 GET and
2,000 PUT requests/month. This task uses a few MB — effectively zero cost, and your
$200 new-account credits cover everything regardless.

> Everything below happens in the AWS console in your browser. No software to install.

---

## Part A — Create the bucket

1. Console search bar → **S3** → **Create bucket**.
2. **Bucket name:** must be globally unique — use `codeorbit-arya-xxxx`
   (replace `xxxx` with any 4 digits, e.g. `codeorbit-arya-2026`).
3. **AWS Region:** **Asia Pacific (Mumbai) ap-south-1**.
4. **Object Ownership:** keep **ACLs disabled (recommended)**.
5. **Block Public Access settings:** keep **Block *all* public access ON** (the default —
   this is the secure setting; you will grant controlled access later instead).
6. Leave everything else default → **Create bucket**.

📸 **Screenshot 1:** the S3 Buckets list showing your new bucket, region
`Asia Pacific (Mumbai)`, and "Access: Bucket and objects not public".

---

## Part B — Organize: folders + uploads

First, make two tiny sample files on your laptop (any content works):

- `hello.txt` containing `Hello from my cloud storage!`
- any small image, e.g. a photo renamed to `sample.jpg`

Then, inside your bucket:

1. Click the bucket name → **Create folder** → name it `documents/` → Create.
2. **Create folder** again → name it `images/` → Create.
3. Open `documents/` → **Upload** → **Add files** → choose `hello.txt` → **Upload**.
4. Back to the bucket root → open `images/` → **Upload** → add `sample.jpg` → **Upload**.

📸 **Screenshot 2:** inside the bucket showing the two folders `documents/` and
`images/`, with one of them open showing the uploaded file.

---

## Part C — Manage files

1. Open `images/` → tick `sample.jpg` → **Download** — confirm it downloads to your laptop.
2. Tick `sample.jpg` → **Delete** → type `permanently delete` to confirm.
3. Re-upload `sample.jpg` (so your final state is tidy), then open `hello.txt`
   and confirm its content looks right.

(There is no rename button in S3 — files are renamed by copying to a new name and
deleting the old one. You don't need to demo this; just know it.)

---

## Part D — Access permissions

### D1. Confirm the bucket is private (the secure default)

1. Open your bucket → **Permissions** tab.
2. Under **Block public access (bucket settings)** it should say **On**.

📸 **Screenshot 3:** the Permissions tab showing **Block public access: On**.

### D2. Grant time-limited access to one file (presigned URL)

This is how you share a private file without making anything public:

1. Go to **Objects** tab → open `documents/` → click `hello.txt`.
2. Top-right → **Object actions** → **Share with a presigned URL**.
3. Set expiry to **10 minutes** → **Create presigned URL**.
4. Copy the long URL, open it in a **private/incognito** browser window —
   the file content (or download) appears. After 10 minutes the same link stops working.

📸 **Screenshot 4:** the "Share object with a presigned URL" dialog (or the opened
URL showing the file) — this proves controlled, expiring access.

> **Why not "make public"?** Real teams keep buckets private and share via presigned
> URLs or bucket policies. Your report will say exactly that — it reads as genuine
> understanding, which is what the internship is assessing.

---

## Part E — Clean up (optional)

S3 free tier is generous, but tidy is tidy: once your report is assembled you may
**Empty** the bucket (select all objects → Delete) and then **Delete** the bucket.
Do this only *after* Muse confirms the report is done.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "Bucket name already exists" | Add more digits/letters — names are global, not just yours |
| Upload button greyed out | You are inside a folder view — uploads go into the open folder; that's fine |
| Presigned URL shows AccessDenied | You copied it wrong or it expired — regenerate with 1-hour expiry and retry quickly |

---

## What to send back to Muse

The **4 screenshots** (1–4) plus your bucket name and region.
Muse will assemble them into your Task 3 setup report.
