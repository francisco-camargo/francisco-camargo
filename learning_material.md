Learning & Reference Material
=============================

# Project Ideas

* [7 MLOPs Projects for Beginners](https://www.kdnuggets.com/7-mlops-projects-beginners)
* Set up db with MariaDB. Backend APIs
* Docker + PyTorch [link](https://youtu.be/Gx_I2y3L8is?si=SEMipRHS52h9HNYU)
* Python project setup; `setup.py`, `.tox`, `pyproject.toml`
  * setup .tox as described in mCoding video; want to make it so that testing suite has an easy time when it needs to look for code; done by "installing" the src code
* On Cloud
  * Be able to develop in remote Dockerized code-base
  * Deploy container to EC2
  * Deploy Docker container to VPS using Docker Swarm [link](https://youtu.be/ZmL46xVdYzM?si=Z12p5LcWR2byaQZV) and use docker context to work remotely (also ssh-add was used)
* Database migration with Alembic: Chapter 6, building data science applications with fastapi
  * FastAPI Ch 10: FastAPI app with Docker, [Bigger apps](https://fastapi.tiangolo.com/tutorial/bigger-applications/)
* GitHub Actions / GitLab CI/CD
* Software for gym owners
* App that correlates food and medicine intake habits to how you are feeling; eg today I had fiber and 6hrs I feel it
* Book on Test, Training, and Validation.
  * Most underappreciated concept in Machine Learning
  * Write up case-studies of it going well and poorly
  * How do we use ttv to debug and improve model performance
    * Learning and validation curves
  * How do diff model learning algorithms utilize data
    * Early stopping based on validation set
    * DL epochs and continual learning on previously seen training data
  * ITTV
    * (I)nference data is critically overlooked in ML education. Every decision you make must be for the sake of desired behavior/performance on inference data

# [Advice](src/advice/README.md)

# Cloud

* [Terraform](src/terraform/README.md)
* AWS
  * [AWS CLI](src/aws/aws_cli/README.md)
  * [AWS CDK](src/aws/cdk/README.md)
  * [SageMaker](src/aws/sagemaker/README.md)

# Data Engineering

* [Basic SQL](https://github.com/francisco-camargo/learn-sql)
* [Georgia Tech - CS6400 Database Design](https://github.com/francisco-camargo/cs6400-database-design-tradeplaza)
* Data Versioning
  * DVC (Data Version Control)
  * Guild.ai

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

# [git](src/git/README.md)

# [LaTeX](src/latex/README.md)

# [Linux](src/linux/README.md)

# [Markdown](src/markdown/README.md)

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

# Python

* [Python installation](src/python/README.md)
* [Testing](src/python/testing/README.md)
* [pre-commit](src/python/pre-commit/README.md)
* Python Project template
  * [Cookiecutter and Makefile](https://www.ianwootten.co.uk/2021/01/07/bootstrapping-python-projects-with-cookiecutter-and-makefiles/)
  * `pre-commit install`
  * set up `venv` and install packages
  * `.gitignore`
  * `.gitconfig`
  * `README.md`

# [Vim](src/vim/README.md)

# [VSCode](src/vscode/README.md)

# [WSL](src/wsl/README.md)

# Misc

* [Software testing](src/testing/README.md)
* [Georgia Tech - ISYE6501 Analytics Modeling](https://github.com/francisco-camargo/isye6501-analyticsmodeling)
* [Georgia Tech - ISYE6644 Simulation and Statistics](https://github.com/francisco-camargo/isye6644-simulation)
* [Georgia Tech - CS6515 Graduate Algorithms](https://github.com/francisco-camargo/cs6515-intro-grad-algo)
* [Georgia Tech - CS6603 AI, Ethics, and Society](https://github.com/francisco-camargo/cs6603-ai-ethics-society)
