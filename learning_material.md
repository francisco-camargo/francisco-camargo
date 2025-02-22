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
* Book on Test, Training, Validation / Genarizability of Models
  * What we desire is generalizable models; models that perform well on unseen/inference data. [link](https://people.csail.mit.edu/delimitrou/papers/2024.cal.generalizability.pdf), [link](https://www.rudderstack.com/learn/machine-learning/generalization-in-machine-learning/), [link](https://pmc.ncbi.nlm.nih.gov/articles/PMC9885377/), [link](https://www.cs.toronto.edu/~lczhang/321/notes/notes09.pdf), [link](https://www.computer.org/csdl/journal/ca/2024/01/10488711/1VORtAtSeuA), [link](https://arxiv.org/pdf/2202.01337)
  * Most underappreciated concept in Machine Learning
  * Write up case-studies of it going well and poorly
    * [link](https://pmc.ncbi.nlm.nih.gov/articles/PMC8637230/), [link](https://www.thelancet.com/journals/landig/article/PIIS2589-7500(20)30186-2/fulltext)
  * Bias and variance. Under- and over-fitting
  * How do we use ttv to debug and improve model performance
    * Learning and validation curves
  * How do diff model learning algorithms utilize data
    * Early stopping based on validation set
    * DL epochs and continual learning on previously seen training data
  * ITTV
    * (I)nference data is critically overlooked in ML education. Every decision you make must be for the sake of desired behavior/performance on inference data. If the cost of having a bad model in production is low and it is easy to get new Test data (or it's easy to run inference) then you could consider production to be your Test data.q
    * (T)est data is there *only* to measure the performance of your model on unseen data. This is of value to the customer of your model. Test data must *not* be used to feedback to the model training. If it does, the resulting performance on said data *cannot* be used to quote performance to your customer.
      * When the thought enters your mind that you are ready to run the model on Test data, you should be ready to have go back out into the world and find new Test data if you are unhappy with performance on the original Test data. If you are not willing to do that, then the moment you checked performance on the original Test data *you are done* with model training.
    * Test data *only* tells you about the performance of a model after you are *done* training. You could segment the Test data such that you get a distribution of results.
  * Cross-Validation
    * K-Fold Cross-Validation
    * Chronology obeying Cross-Validation
    * [Nested Cross-Validation](https://scikit-learn.org/stable/auto_examples/model_selection/plot_nested_cross_validation_iris.html)

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
