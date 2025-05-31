# Python

[Return to top README.md](../../README.md)

## Install Python on Windows

[Link](https://www.python.org/downloads/) to download Python.

During installation, be sure to add Python to PATH:

![1670921358303](1670921358303.png)

Check the version of Python. Note that it can have different aliases, e.g. `python`, `py`, `python3` etc.

```bash
python --version
>>> Python3.11.0
```

If you use VSCode, be sure that the desired Python Interpreter is used: from the Command Pallette search for `Python: Select Interpreter`. Can check the bottom right of the window:

![1670921755378](1670921755378.png)

## Install Python on WSL

[Guide](https://computingforgeeks.com/how-to-install-python-on-ubuntu-linux-system/)

give an [alias](https://askubuntu.com/questions/320996/how-to-make-python-program-command-execute-python-3?newreg=a3ae2d11b44641baba3120c0f6ca6111)

`alias python = python3.10`

[Guide](https://stackoverflow.com/questions/63591163/python3-pip-has-no-installation-candidate) to install `pip`

```shell
sudo apt-get update
sudo apt-get upgrade # not needed according to guide, but may as well
sudo apt install python3-pip
```

## Project structure

* Things to consider adding/using when making a new Python project
  * [Cookiecutter and Makefile](https://www.ianwootten.co.uk/2021/01/07/bootstrapping-python-projects-with-cookiecutter-and-makefiles/)
  * `README.md`
  * `LICENSE`
  * `.gitignore`
  * `.gitattributes`: use to control end-of-line characters when committing to remote
  * `.gitconfig`: configure local credentials (and many other things). Do not commit to the repo!
  * `.env`: file with environment variables that be be used by easily used containers and code (via `python-dotenv`). Be very careful to not commit sensitive information to the repo!
  * `.pre-commit-config.yaml` [link](src\python\pre-commit\README.md)
  * `venv`: set up virtual environments
  * `pyproject.toml`: A configuration file introduced by [PEP 518](https://peps.python.org/pep-0518/) used by Python packaging tools
  * `requirements.txt`: alternative to `pyproject.toml` to handle package dependencies
  * logging config file
  * `src` and `tests` directories
  * CI config files, e.g. `.github/workflows/ci.yaml`

## Python Code Environment

Download and install Python from [link](https://www.python.org/downloads/)

### `venv` on Windows

To create an environment via the terminal, use

`python -m venv env`

To activate environment, use

`env/Scripts/activate`

In `git bash` may have to use `. env/Scripts/activate`

To update `pip`, use

`python -m pip install --upgrade pip`

To install libraries, use

`pip install -r requirements.txt`

To deactivate an active environment, use

`deactivate`

### `venv` on Ubuntu

On Ubuntu, you may need to install `python3-venv`, [link](https://askubuntu.com/questions/1328392/how-to-activate-a-virtual-environment-in-ubuntu)

`sudo apt install python3-venv`

Create the virtual environment

`python3 -m venv env`

Activate the environment

`. env/bin/activate`

Upgrade `pip`

`python -m pip install --upgrade pip`

Install python libraries

`pip install -r requirements.txt`

Deactivate the environment

`deactivate`

### `uv` on Windows

#### Installation

[Guide](https://www.datacamp.com/tutorial/python-uv)

As administrator, run the following on Windows PowerShell

```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

To verify installation, open a new terminal and run

```bash
uv version
```

This ran in PowerShell and git bash

#### New Project

To start a new project, run

```bash
uv init <project name>
```

if a `git` repo already exists, within the repo you can just run

```bash
uv init
```

(or maybe)

```bash
 uv init .
 ```

 ?

This creates several files, including `pyproject.toml`

#### Virtual Environment and Package Management

To create a virtual environment (equivalent to `python -m venv .venv`), run

```bash
uv venv
```

However, with one command we can create both a virtual environment and install packages, for example by running

```bash
uv add pandas
```

results in

```bash
Creating virtual environment at: .venv
Resolved 7 packages in 487ms
Prepared 6 packages in 21.42s
Installed 6 packages in 2.29s
 + numpy==2.2.6
 + pandas==2.2.3
 + python-dateutil==2.9.0.post0
 + pytz==2025.2
 + six==1.17.0
 + tzdata==2025.2
 ```

and it also updates `pyproject.toml` to include `pandas` as a dependency.

To remove a dependency,

```bash
uv remove scikit-learn
```

#### Run code

`uv` created a `.venv` folder which VSCode noticed and is not using as the virtual environment path.

To run code from the terminal,

```bash
uv run <python file>
```

## Testing

* [Testing](src/python/testing/README.md)

## Importing local code from other directories

Assume you have the following folder structure:

```shell
parent
  scriptE.py
  folder1
    scriptA.py
    scriptB.py
    folder3
      scriptF.py
  folder2
    scriptC.py
    scriptD.py
```

and the current working directory is `folder1`.

If you need to run from a submodule directly such that `__name__` is `'__main__'`, try adding the parent directory to the system path

```python
try:
    from folder1.folder3 import scriptF
except ModuleNotFoundError as e:
    sys.path.append(os.getcwd())
    from folder1.folder3 import scriptF
```

If you want to do relative imports: good [write-up](https://stackoverflow.com/questions/14132789/relative-imports-for-the-billionth-time). My current understanding is that whatever script is `'__main__'` will not be able to utilize relative imports!

Again assume the current working directory is `folder1`:

* For `scriptB.py`, use `import scriptB`
* For `scriptF.py`, use `import folder3.scriptF`
* For `scriptE.py`, you _must_ use the `from` syntax; `from ..scriptE import *`
* For `scriptC.py`, use `from ..folder2.scriptC`

Here are some useful commands to help debug some of these issues:

```python
    import sys
    print(f'system path: {sys.path}')
    import os
    print(f'current working dir (cwd): {os.getcwd()}')
    print(f'ls within cwd: {os.listdir('./')}')
    print(f'ls within ../cwd: {os.listdir('../')}')
```

## Running Python code in VSCode

To use the IPython terminal, install IPython

```bash
pip install ipython
```

Then in the VSCode terminal run

```bash
ipython
```

need to load (once) the `%autoreload` extension, [guide](https://ipython.readthedocs.io/en/stable/config/extensions/autoreload.html),

```Python
%load_ext autoreload
```

now can use `%autoreload`

```Python
%autoreload
%run main.py
```

I was able to run both of these lines together in the VSCode terminal by using **Ctrl+o** in the terminal to have multiple lines of input.

This will have the same effect as clicking **Run** within Spyder on whatever Python file Spyder has open. This also has the benefit of seeing changes to the code while still in IPython, which is not working when using the "import main" approach.

(old) and then within the IPython terminal that has now been instantiated, import the module you want to use

```Python
import main; main.main()
```

## `pyproject.toml`

The [documentation](https://black.readthedocs.io/en/stable/usage_and_configuration/the_basics.html) for `black` suggests that we can use a `pyproject.toml` file to replace both `setup.py` and `setup.cfg` files.

![1670897817471](1670897817471.png)

## Packaging

Learn how to package code, there are several options, so first want to just look at all of them before picking one to run with

[Guide](https://stackoverflow.com/questions/1471994/what-is-setup-py)

[Guide](https://packaging.python.org/en/latest/guides/distributing-packages-using-setuptools/#configuring-your-project)

[Guide](https://godatadriven.com/blog/a-practical-guide-to-using-setup-py/), in it, they say: nowadays the use of setup.py is discouraged in favour of pyproject.toml together with setup.cfg. Find out how to use those [here](https://godatadriven.com/blog/a-practical-guide-to-setuptools-and-pyproject-toml/).

Poetry also does a similar thin? There may be some [serious problems](https://www.youtube.com/watch?v=Gr9o8MW_pb0) with Poetry. [webpage](https://python-poetry.org/) Sounds like poetry also does dependance management, so maybe use it instead of `venv`? [Poetry intro](https://youtu.be/0f3moPe_bhk) from ArjanCodes, who seems happy with it. Sounds like it can help with package publishing.

What the heck is a wheel?

## Plotting

I can plot out-of-the box to a pop-up window in VSCode if I use Run, but if I use ipython to run the code, I can't seem to be able to get the plots.

In `./src/plotting.py` I placed sample code for a plotting function that handles the aesthetics well. It Accounts for; uncertainty bands, `.eps` formatting, size of plot for two column paper, and several other minor details.

## Data Validation

[Pydantic](https://www.youtube.com/watch?v=zN4VCb0LbQI)

## Pandas

### Data Types for DataFrames

[Guide](https://youtu.be/-tU7fuUiq7w)

[Guide](https://towardsdatascience.com/validate-your-pandas-dataframe-with-pandera-2995910e564)

### `df.apply()`

[df.apply()](https://www.geeksforgeeks.org/apply-function-to-every-row-in-a-pandas-dataframe/)

### `SettingWithCopyWarning`

[Guide](https://realpython.com/pandas-settingwithcopywarning/), simple explanation on how to deal with this. First line of defense: use `.loc` and `.iloc`

```Python
df.loc[idx_label, col_label] = some_new_value
```

I think `idx_label` then just needs to be an element found within `df.index()`.

Alternatively, you could use a mask. By example:

```Python
mask = df[column_label]==some_value
```

This returns a mask of boolean values to pick out rows. Now use this mask instead of `idx_label`

```Python
df.loc[mask, col_label] = some_new_value
```

## SciKit-Learn

Want to be able to use sklearn without having to switch back and forth between numpy arrays and dataframes. Use [sklearn-pandas](https://github.com/scikit-learn-contrib/sklearn-pandas). I have successfully used this in `make_features.py` within the `dsc_roadmap` project; import `DataFrameMapper` and use it in conjunction with the sklearn `SimpleImputer`.

### ShuffleSplit

[StackOverflow](https://stackoverflow.com/questions/34731421/whats-the-difference-between-kfold-and-shufflesplit-cv#:~:text=As%20your%20data%20set%20grows,ShuffleSplit%20is%20an%20attractive%20option.) on why ShuffleSplit is useful as training data size grows

### `FutureWarning: This Pipeline instance is not fitted yet`

I created a custom class to use as part of a feature engineering `Pipeline` and was getting this warning. One way to get this warning to go away is to add an `Estimator` at the end of the `Pipeline` but that is undesirable as I want this pipeline to be dedicated to feature engineering.

[This](https://stackoverflow.com/a/79479302/9205210) post has as solution that I think is better. Essentially, in variables defined within the custom class, name them with an underscore suffix.

```python
class CustomClass(BaseEstimator, TransformerMixin):
    def __init__(self, attribute):
        self.attribute_ = attribute

    def fit(self, X, y=None):
        scale_cols_ = X[self.attribute_]
        return self
```

It seems like this works even if I only apply an underscore suffix to one (and not all) the attributes. Also not sure if it matter if it's a method instead. I don't understand why this works in the first place, but I can live with it and it enables the use of custom transformers to be used in `Pipelines`!

## Experimental Setup

[Guide](https://hydra.cc/docs/intro/) into how to use Hydra to help run experiments using Python.

[Video](https://youtu.be/tEsPyYnzt8s) intro

[Video](https://www.youtube.com/watch?v=bNGu8A6F3-8) mentions integration with mlflow around 20min mark, talks about parallelization (26min mark)

[Video](https://www.youtube.com/watch?v=3gk9CvMOdzE) for hydra-zen

## Model based testing

There is the `hypothesis` python package. [Docs](https://hypothesis.readthedocs.io/en/latest/), [demonstration](https://youtu.be/-S3BFkNn0rQ)

## Logging

Don't pass logger around as a function input, instead import `logger` into each script of interest

Very simple logging:

```python
import logging

logger = logging.getLogger(__name__)
logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(levelname)s - %(message)s',
)

logger.info('Added an entry to the logger')
```

More sophisticated logging:

```python
"""
Logging Configuration Module

This module sets up a centralized logging configuration for use across the application.
It configures a logger that writes to both a file (overwriting it on each run) and the console.
The timestamp in log messages is set to GMT (UTC) time.
Log messages include the filename and line number instead of the logger name.

The module provides a pre-configured logger object that can be imported and used in other modules.

To use this in another script
  from src.logging.log_config import logger
  logger.info('Write this to the log')

Attributes:
    logger (logging.Logger): A configured logger object for use across the application.
"""

import logging
import sys
from time import gmtime

# Configure the logger
logging.Formatter.converter = gmtime  # Set time to GMT

# Create a logger
logger = logging.getLogger(__name__)
logger.setLevel(logging.INFO)

# Create file handler which logs even debug messages
file_handler = logging.FileHandler('src/logging/app.log', mode='w')
file_handler.setLevel(logging.INFO)

# Create console handler with a higher log level
console_handler = logging.StreamHandler(sys.stdout)
console_handler.setLevel(logging.INFO)

# Create formatter and add it to the handlers
formatter = logging.Formatter('%(asctime)s - %(levelname)s - %(filename)s:%(lineno)d\n\t%(message)s')
file_handler.setFormatter(formatter)
console_handler.setFormatter(formatter)

# Add the handlers to the logger
logger.addHandler(file_handler)
logger.addHandler(console_handler)
```
