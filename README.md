# CodeOrbit Cloud Computing Internship — Project Submissions

**Intern:** Arya Yaligar · **Program:** CodeOrbit Tech Cloud Computing Internship (Batch 8)
**Duration:** 1 Oct 2026 – 30 Oct 2026

This repository contains all completed tasks for the 1-month Cloud Computing internship:
a fundamentals report plus two hands-on AWS free-tier builds (virtual machine + cloud storage),
each documented with a step-by-step guide and screenshots.

## Tasks

| # | Task | Folder | Status |
|---|---|---|---|
| 1 | Cloud Fundamentals Report — IaaS, PaaS, SaaS explained with examples + AWS vs Azure comparison (2–3 pages) | [`task1-cloud-fundamentals/`](task1-cloud-fundamentals/) | ✅ Complete |
| 2 | Virtual Machine Setup — EC2 `t3.micro` (Amazon Linux 2023) + nginx, documented with screenshots | [`task2-vm-setup/`](task2-vm-setup/) | ✅ Complete |
| 3 | Cloud Storage & File Management — S3 bucket with folders, uploads and presigned-URL access demo, screenshots | [`task3-cloud-storage/`](task3-cloud-storage/) | ✅ Complete |

## Technologies used

- **Cloud platform:** Amazon Web Services (AWS Free Tier) — EC2, S3, CloudWatch billing alarms
- **OS / server:** Amazon Linux 2023, nginx
- **Docs:** Markdown + PDF (built with WeasyPrint)

## Setup instructions

Each task folder is self-contained:

1. **Task 1** — just read it: [`task1-cloud-fundamentals/Cloud-Fundamentals-Report.pdf`](task1-cloud-fundamentals/Cloud-Fundamentals-Report.pdf)
   (Markdown source alongside it).
2. **Task 2** — follow [`task2-vm-setup/VM-Setup-Guide.md`](task2-vm-setup/VM-Setup-Guide.md)
   in order (AWS account → billing alarm → launch EC2 → install nginx → screenshots).
   Needs an AWS account; everything used is free-tier eligible.
3. **Task 3** — follow [`task3-cloud-storage/Cloud-Storage-Guide.md`](task3-cloud-storage/Cloud-Storage-Guide.md)
   (create S3 bucket → folders + uploads → permissions + presigned URL → screenshots).

To reproduce the PDF report locally: `pip install weasyprint` then
`weasyprint report.html report.pdf` (HTML sources kept with the working notes).

## GitHub repository link

> TODO: replace with the real URL after creating the repo —
> `https://github.com/arya123-sudo/CodeOrbit_CloudComputing`

## Demo video

A 2–5 minute screen recording walking through the EC2 + nginx build
will be posted on LinkedIn (link added here once published).
