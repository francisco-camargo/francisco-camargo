# Project Ideas

* [7 MLOPs Projects for Beginners](https://www.kdnuggets.com/7-mlops-projects-beginners)
* Set up db with MariaDB. Backend APIs
* Use a free cloud hosting service
  * Theo [guide](https://youtu.be/prjMJtXCR-g?si=r44nau8MSZ-sRmI4). Internet likes DigitalOcean
* GitHub Actions / GitLab CI/CD
* Efficient Docker image for Python; [guide](https://youtu.be/tc713anE3UY?si=eaMOsSrTHICPMz0u)
* Docker + PyTorch [link](https://youtu.be/Gx_I2y3L8is?si=SEMipRHS52h9HNYU)
* Python project setup; `setup.py`, `.tox`, `pyproject.toml`
  * setup .tox as described in mCoding video; want to make it so that testing suite has an easy time when it needs to look for code; done by "installing" the src code
* On Cloud
  * Be able to develop in remote Dockerized code-base
  * Deploy container to EC2
  * Deploy Docker container to VPS using Docker Swarm [link](https://youtu.be/ZmL46xVdYzM?si=Z12p5LcWR2byaQZV) and use docker context to work remotely (also ssh-add was used)
* Database migration with Alembic: Chapter 6, building data science applications with fastapi
  * FastAPI Ch 10: FastAPI app with Docker, [Bigger apps](https://fastapi.tiangolo.com/tutorial/bigger-applications/)
* Software for gym owners
* App that correlates food and medicine intake habits to how you are feeling; eg today I had fiber and 6hrs I feel it
* Model generalizability book
* Mortgage rates
  * Web scrape for mortgage rates
  * Website where I can sign up to get an email when mortgage rates exceed some value

## Dev on the Cloud

Below is a snapshot of popular ways to get a **real VM‑style instance you can SSH or RDP into—without paying anything up‑front.**  I’ve grouped them by the kind of service you’re likely to use first.

---

### 1. Big “general‑purpose” cloud providers

| Provider                                      | What you get for free                                                                          | How long                          | Key caveats                                                                                                            |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **AWS EC2**                             | 1 ×`t2.micro` or `t3.micro`, 750 instance‑hours/month (≈one always‑on VM)          | 12 months after signup           | Linux*or* Windows; you still pay for EBS >30 GB and outbound data; credit card required citeturn8search0     |
| **Google Cloud Compute Engine**         | 1 ×`e2‑micro` (US regions), 30 GB SSD, 1 GB egress                                      | **Always‑free**            | Only in `us‑east1`, `us‑west1`, `us‑central1`; no GPUs/TPUs; still need billing account citeturn4view0 |
| **Microsoft Azure**                    | 750 hrs/month of `B1s` (Linux or Windows) burstable VM                                      | 12 months + $200 30‑day credit | Once the 12 months are up you pay on‑demand; outbound bandwidth is metered citeturn9view0                     |
| **Oracle Cloud Infrastructure (OCI)** | Up to**4 × Ampere A1 Arm** cores **or** 2 × AMD VMs, plus 24 GB RAM total | **Always‑free**            | Region availability can vary; instances are pre‑emptible if Oracle hits capacity limits citeturn11view0       |

**When to pick one of these:**

* You want full root/administrator control.
* You need to install arbitrary software or expose custom network ports.
* Long‑running workloads or self‑hosted services.

---

### 2. “Hobby platform” hosts (easier UX, lighter VMs/containers)

| Host              | Free compute allowance                                                                           | Notable limits                                                                                         |
| ----------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| **Fly.io**  | Up to**3 × shared‑CPU‑1x** VMs (256 MB RAM) + 3 GB storage + 160 GB egress/month | VMs are tiny; credit card still required; pricing page can change without notice citeturn2view0 |
| **Render**  | 1 free web service/container & one Postgres/KV instance (auto‑sleeps after 15 min idle)        | 512 MB RAM, 100 ms cold‑start, limited concurrency citeturn1search1                          |
| **Railway** | “Free Trial” credits that cover ~500 cpu‑minutes & 1 GB RAM/month before you start paying   | Designed for staging/demo work, not persistent servers citeturn1search2                         |

**Why use them:** seamless Git‑push deploys, HTTPS & DNS pre‑wired, no VPC/network setup. Great for small APIs, prototypes, or toy side‑projects that can tolerate cold‑starts.

---

### 3. On‑demand development environments (browser or VS Code remote)

| Service                       | Included free tier                                                                                                                 | Typical use case                                                                      |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **GitHub Codespaces**   | 120 core‑hours + 15 GB storage every month for GitHub Free accounts (≈60 hrs on a 2‑core machine) citeturn13search0 | Instant dev box with Visual Studio Code—ideal for coding, not for public services. |
| **Google Cloud Shell** | 5 GB home dir + 1 vCPU/1.7 GB VM (Ephemeral; auto‑shuts down after 60 min idle) citeturn4view0                        | Quick admin tasks or demos directly from the browser, no billing surprises.           |

---

## Connecting from your local machine

1. **SSH/RDP:** All of the “big four” clouds let you attach a public IP or tunnel through a managed bastion.
2. **VS Code Remote SSH / JetBrains Gateway:** Gives you full IDE experience while computation happens in the cloud.
3. **Port‑forwarding:** For web apps or APIs, forward cloud ports (e.g., 22, 80, 443) to your local tools.
4. **Budget guards:** Set billing alerts (AWS Budgets, GCP Budgets, Azure Cost Management) so a forgotten instance doesn’t blow past the free quota.

### Quick decision tips

* **Always‑free vs 12‑month promo:** If this is a long‑term personal server, Oracle Cloud or Google Cloud’s always‑free VMs are the safest bet.
* **Windows requirement:** Azure or AWS free tiers include Windows licenses; GCP/OCI don’t.
* **Arm experiments:** Oracle’s Ampere A1 gives you four Arm cores for free; AWS only offers a time‑limited t4g.small promo.
* **Simplest deploy flow:** If git‑push is more important than root access, a platform like Render or Fly.io is less hassle.

---

### Next steps

1. Sign up with your preferred provider (using a separate billing email helps keep things tidy).
2. Spin up the smallest free‑tier VM; confirm you can SSH in.
3. Immediately set **budget alerts** and **instance idle‑shutdown policies**.
4. Snapshot any data you care about—free tiers often reclaim resources after 30 days of inactivity.

That’s it! With a free‑tier VM you can compile code, host a lightweight API, or run personal automation from anywhere while only paying (at most) for extras like storage or heavy network egress.
