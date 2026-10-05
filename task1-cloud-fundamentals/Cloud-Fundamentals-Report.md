# Cloud Computing Fundamentals

**Understanding IaaS, PaaS and SaaS — with a comparison of Amazon Web Services and Microsoft Azure**

*Arya Yaligar | CodeOrbit Tech — Cloud Computing Internship (Batch 8) | Task 1 | October 2026*

---

## 1. Introduction: What Is Cloud Computing?

Cloud computing is the **on-demand delivery of computing resources** — servers, storage, databases, networking and software — over the internet, billed on a pay-as-you-go basis. Instead of buying and maintaining physical machines, a business rents exactly what it needs from a cloud provider and releases it when done. A widely used definition (from the U.S. National Institute of Standards and Technology) describes it as convenient, on-demand network access to a shared pool of configurable resources that can be provisioned rapidly with minimal management effort.

Three ideas sit at the heart of the cloud: **elasticity** (scale up or down in minutes), **measured service** (you pay only for what you use, like an electricity bill), and **broad network access** (resources reachable from anywhere). These are why startups can launch global products without a server room, and why retailers can absorb festival-season traffic spikes without buying hardware that sits idle the rest of the year.

## 2. The Three Service Models: IaaS, PaaS and SaaS

Cloud services are usually grouped into three models. They differ in **how much the provider manages for you** — and therefore how much control you keep.

### 2.1 IaaS — Infrastructure as a Service

With IaaS you rent the raw building blocks: **virtual machines, storage and networks**. The provider owns the physical data centre; you install and manage the operating system, middleware and applications. It is the closest thing to owning your own servers, minus the hardware headaches.

- **Examples:** Amazon EC2, Microsoft Azure Virtual Machines, Google Compute Engine.
- **Typical uses:** hosting websites and backend servers, development and test environments, "lift-and-shift" migration of existing applications.
- **Good for:** teams that want full control over the software stack and are comfortable managing servers.

### 2.2 PaaS — Platform as a Service

With PaaS the provider manages everything up to the runtime: operating system, patching, scaling and load balancing. **You simply deploy your code**, and the platform runs it.

- **Examples:** AWS Elastic Beanstalk, Microsoft Azure App Service, Google App Engine, Heroku.
- **Typical uses:** web applications and APIs, rapid prototyping, student and startup projects.
- **Good for:** developers who want to ship features instead of babysitting servers.

### 2.3 SaaS — Software as a Service

With SaaS you use **finished software directly in the browser**. Nothing to install, patch or scale — the provider handles it all, and you typically pay per user per month.

- **Examples:** Gmail, Microsoft 365, Google Workspace, Salesforce, Dropbox, Zoom.
- **Typical uses:** email, collaboration, customer relationship management, file sharing.
- **Good for:** end users and businesses that want a tool that "just works".

> **A simple analogy — pizza as a service.** Making pizza at home with your own oven is like an on-premises data centre: you manage everything. Ordering a pizza kit with pre-made dough is IaaS (the basics are provided, you do the rest). Ordering a pizza for delivery is PaaS (you just choose the toppings — your code). Dining at a restaurant is SaaS (everything is done for you; you simply enjoy the result). Each step trades control for convenience.

**Who is responsible for what?** In an on-premises setup you manage everything from the building to the application. With IaaS the provider secures the physical infrastructure while you manage the OS upward. With PaaS the provider additionally manages the OS and runtime. With SaaS the provider manages the entire stack — your responsibility shrinks to managing your users, data and access. This "shared responsibility" idea is one of the most important concepts in cloud security.

## 3. Deployment Models (A Quick Note)

Alongside the service models are **deployment models**: *public* cloud (shared over the internet, e.g. AWS), *private* cloud (dedicated to one organisation), *hybrid* (a mix of both) and *multi-cloud* (using two or more providers). Beginners almost always start with the public cloud because of its generous free tiers.

## 4. The Major Providers

Three companies dominate global cloud infrastructure. **Amazon Web Services (AWS)**, launched in 2006, is the pioneer and market leader with the broadest catalogue of services. **Microsoft Azure**, launched in 2010, is the enterprise favourite, deeply integrated with Windows, Office and corporate identity systems. **Google Cloud Platform (GCP)** is the challenger, strongest in data analytics, Kubernetes (which Google created) and AI infrastructure. Together the three held about two-thirds of worldwide cloud infrastructure spending in Q2 2026 (Synergy Research Group, via CRN).

## 5. Comparison: AWS vs Microsoft Azure

| Aspect | Amazon Web Services (AWS) | Microsoft Azure |
|---|---|---|
| **Launched** | 2006 — the first major cloud | 2010 — built for the enterprise |
| **Market share (Q2 2026)** | **~28%** — the leader | **~20%** — a strong second |
| **Global reach** | 30+ geographic regions | 60+ regions — more than any other provider |
| **Virtual machines** | EC2 — the widest range of instance types | Virtual Machines — tight Windows/AD integration |
| **Object storage** | S3 — the industry standard | Blob Storage — equivalent, strong hybrid story |
| **Pricing** | Pay-as-you-go, per-second billing | Pay-as-you-go, per-second billing |
| **Free tier** | $200 in credits over 6 months (Free Plan) — no charges unless you upgrade to Paid | $200 credit for 30 days + 12 months of free services |
| **Strengths** | Maturity, service breadth, huge community and documentation | Enterprise contracts, hybrid cloud (Azure Arc), Microsoft 365 synergy |
| **Best for** | Startups, the widest job market, learning the cloud from scratch | Companies already on Windows/Office, hybrid on-premises setups |

*Sources: Synergy Research Group Q2 2026 figures via CRN; provider documentation for free-tier terms.*

The honest summary: for most workloads the two are **functionally interchangeable** — both offer virtual machines, managed databases, object storage and serverless functions. AWS wins on maturity and ecosystem size; Azure wins where a company already lives inside Microsoft's world. For a student, the deciding factor is simpler: pick the one whose free tier and tutorials you find friendliest, because the core concepts transfer directly.

## 6. Putting It Together: One Website, Three Ways

Imagine deploying a simple portfolio website. **On IaaS**, you launch an EC2 virtual machine, install a web server such as Nginx yourself, and copy your files over — full control, but you handle updates and security patches. **On PaaS**, you upload the same site to Elastic Beanstalk or Azure App Service and the platform provisions the server, the runtime and HTTPS for you. **On SaaS**, you would not deploy anything at all — you would simply build the site in a hosted tool like WordPress.com or Wix. Same end result, three very different amounts of work: that trade-off is the entire service-model story in one example.

## 7. Conclusion

Cloud computing replaces upfront hardware investment with flexible, pay-as-you-go rental of computing power. IaaS gives you raw infrastructure to manage yourself, PaaS gives you a ready platform for your code, and SaaS gives you finished software in the browser — each step trading control for convenience. AWS and Microsoft Azure, the two largest providers, both offer generous free tiers that make them ideal for hands-on learning. The concepts in this report — elasticity, pay-as-you-go billing and the shared-responsibility model — are the foundation on which the practical tasks of this internship (setting up a virtual machine and cloud storage) are built.

## References

1. Mell, P. & Grance, T. — *The NIST Definition of Cloud Computing*, NIST Special Publication 800-145.
2. Synergy Research Group, Q2 2026 cloud infrastructure market data, via CRN — AWS ~28%, Microsoft ~20%, Google Cloud ~15%.
3. AWS Free Tier documentation — aws.amazon.com/free; Microsoft Azure free account — azure.microsoft.com/free.
4. Microsoft, "Azure has more regions than any other cloud provider" — azure.microsoft.com/global-infrastructure.
