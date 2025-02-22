Learning Material
=================

# Project Ideas

* [7 MLOPs Projects for Beginners](https://www.kdnuggets.com/7-mlops-projects-beginners)
* Python project setup; `setup.py`, `.tox`, `project.toml`
  * setup .tox as described in mCoding video; want to make it so that testing suite has an easy time when it needs to look for code; done by "installing" the src code
* Deploy container to EC2
* Be able to develop in remote Dockerized code-base
* Database migration with Alembic: Chapter 6, building data science applications with fastapi
  * FastAPI Ch 10: FastAPI app with Docker, [Bigger apps](https://fastapi.tiangolo.com/tutorial/bigger-applications/)
* Set up db with SQLite. Backend APIs
* GitHub Actions / GitLab CI/CD
* Docker + PyTorch [link](https://youtu.be/Gx_I2y3L8is?si=SEMipRHS52h9HNYU)
* Deploy Docker container to VPS using Docker Swarm [link](https://youtu.be/ZmL46xVdYzM?si=Z12p5LcWR2byaQZV) and use docker context to work remotely (also ssh-add was used)
* Software for gym owners
* App that correlates food and medicine intake habits to how you are feeling; eg today I had fiber and 6hrs I feel it

# [git](src/git/README.md)

# [Markdown](src/markdown/README.md)

# [LaTeX](src/latex/README.md)

# [Linux](src/linux/README.md)

# [WSL](src/wsl/README.md)

# [VSCode](src/vscode/README.md)

# [Vim](src/vim/README.md)

# Project template

* [Cookiecutter and Makefile](https://www.ianwootten.co.uk/2021/01/07/bootstrapping-python-projects-with-cookiecutter-and-makefiles/)
* `pre-commit install`
* set up `venv` and install packages
* `.gitignore`
* `.gitconfig`
* `README.md`

# Terminal

* To print out a tree view of the current directory use the `tree` command

# Data Versioning

* DVC (Data Version Control)
* Guild.ai

# MLOps

* Orchestration
* Monitoring
  The **LGTM stack** (short for **Loki, Grafana, Tempo, and Mimir**) is primarily used for observability, monitoring, and logging in cloud-native environments. The job roles responsible for using the LGTM stack typically include:

  1. **Site Reliability Engineer (SRE)** – Uses LGTM for monitoring system performance, troubleshooting issues, and ensuring uptime.
  2. **DevOps Engineer** – Implements and maintains LGTM for observability in CI/CD pipelines and cloud infrastructure.
  3. **Cloud/Infrastructure Engineer** – Uses LGTM for managing cloud environments and infrastructure monitoring.
  4. **Platform Engineer** – Integrates LGTM into internal developer platforms for better operational insights.
  5. **Security Engineer** – Analyzes logs and traces for security incidents and anomaly detection.
  6. **Software Engineer (especially Backend)** – Uses LGTM to debug applications and optimize performance.

Would you be looking to implement LGTM for your company’s infrastructure, or just exploring it?

# Cloud

* [Terraform](src/terraform/README.md)
* AWS
  * [AWS CLI](src/aws/aws_cli/README.md)
  * [AWS CDK](src/aws/cdk/README.md)
  * [SageMaker](src/aws/sagemaker/README.md)

# Python

* [Python installation](src/python/README.md)
* [Testing](src/python/testing/README.md)
* [pre-commit](src/python/pre-commit/README.md)

# Data Engineering

* [Basic SQL](https://github.com/francisco-camargo/learn-sql)
* [Georgia Tech - CS6400 Database Design](https://github.com/francisco-camargo/cs6400-database-design-tradeplaza)

# [Docker](src/docker/README.md)

* [Docker installation](https://github.com/francisco-camargo/dev-workflow/blob/main/src/docker/README.md)
* [The Ultimate Docker Course](https://codewithmosh.com/p/the-ultimate-docker-course) by Mosh Hamedani
  * [docker-hello-world](https://github.com/francisco-camargo/docker-hello-world.git)
  * [docker-fundamentals](https://github.com/francisco-camargo/docker-fundamentals)
  * [multi-container-application](https://github.com/francisco-camargo/vidly) via `docker compose`
* [premade-db-with-docker](https://github.com/francisco-camargo/premade-db-with-docker)
* [toy-db-with-docker](https://github.com/francisco-camargo/toy-db-with-docker)
* [Docker exercises](https://github.com/bregman-arie/devops-exercises/blob/master/topics/containers/README.md)

## Docker for Python

* Use Docker for dev work
* Use Docker to dev on local machine while hosting container on Cloud
* [Python language-specific guide](https://docs.docker.com/guides/python/)
* [Docker for Python tutorial](https://github.com/patrickloeber/python-docker-tutorial.git)
* [Optimizing Docker Images for Python Production Services](https://martynassubonis.substack.com/p/optimizing-docker-images-for-python)

# [FastAPI](src/fastapi/README.md)

* [crud-fastapi](https://github.com/francisco-camargo/crud-fastapi)
* [build-deploy-fastapi-web-backend](https://github.com/francisco-camargo/build-deploy-fastapi-web-backend)
* [fastapi-prediction-endpoint](https://github.com/francisco-camargo/fastapi-prediction-endpoint)
* [fastapi-app-with-docker](https://github.com/francisco-camargo/fastapi-app-with-docker)

# Misc

* [Software testing](src/testing/README.md)
* [Georgia Tech - ISYE6501 Analytics Modeling](https://github.com/francisco-camargo/isye6501-analyticsmodeling)
* [Georgia Tech - ISYE6644 Simulation and Statistics](https://github.com/francisco-camargo/isye6644-simulation)
* [Georgia Tech - CS6515 Graduate Algorithms](https://github.com/francisco-camargo/cs6515-intro-grad-algo)
* [Georgia Tech - CS6603 AI, Ethics, and Society](https://github.com/francisco-camargo/cs6603-ai-ethics-society)

# Technical Presentations for a General Audience

* Have a slide or two to introduce yourself and your team. You can consider this talk as an opportunity to do marketing for you and your team; sell us on the notion that you are doing good work and inform us as to when the rest of the company should think to reach out to you
* What are the 2 or 3 big points that you want the audience to think about after the talk is over. If they were to summarize your presentation to someone else, what would you want them to say? I strongly recommend that you write these down for yourself and as you put slides together, ask yourself "is this content in service of the main points I want my audience to take away?"
* Assume that the audience is not familiar with your domain; there are audience members from across the whole company. We have members coming from very different departments; finance, supply chain, HR, engineering, etc. So keep this in mind when introducing the problem.
* Given that your domain may be new to some people, also try to motivate the project; why is this an important problem to solve? What's the bigger picture? What will deploying this solution into production mean for the business?
* Why did you choose the approach you did? Compare and contrast your methods against other "popular" approaches
* Consider walking us through a specific example of the type of question your model is trying to answer; e.g. if you are classifying images, show us an example and explain what makes this problem different than other similar ones.
* Both the business value and the technical details are important. Aim the talk for a data scientist with about a year of work experience. So they should know the basics of DS and ML but if you can connect what you could read in an ML textbook to how you were able to implement a solution, that would be very instructive to this audience. However, the business impact is also significant; it would be great to convey that we want to solve valuable problems that affect the business, and therefore communicate the challenges of what it took/takes to go from a solution that is great on paper (or on your laptop) to a solution that can be embedded within a business process.
* Another way to think about it: if a junior engineer was going to try to replicate what you have done, what do they need to know? What were the technical and business challenges, and how did you tackle them? e.g. if you had to spend a lot of time working with stakeholders because the previous solution was deeply embedded within the business process and you needed to get significant buy-in stakeholders, then this is an important lesson to hear about.
