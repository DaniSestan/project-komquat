# Project configuration

## Overview

The TOML file is now the de-facto standard for the configuration of a Python app, which includes defining the 
project settings and dependencies. Information about package configuration was previously included in the setup.cfg 
file; this is now listed in the pyproject.toml file. The minimum required tables required are "project", 
"build-system", and "tool.setuptools.packages.find":

```
[build-system]
requires = ["setuptools"]
build-backend = "setuptools.build_meta"

[project]
name = "alembic-sample"
version = "1.0.0"
dependencies = [
    "Flask",
    "Flask-Migrate",
    "Flask-SQLAlchemy",
    "alembic"
]

[tool.setuptools.packages.find]
where = ["."]
```

## Understanding the difference between TOML and setup.py

Using a setup.py file in place of a more streamlined process that only uses the pyproject.toml file is obsolete; however, it is good to know the purpose of a setup.py file as python projects still implement it:

- The setup.py file is necessary to be able to install package dependencies using pip. This file is essentially a 
module that only needs to contain a call to the setuptools setup function.

- To simplify things even further, it can be understood that the pyproject.toml file answers the question of "how the 
project is built", while the setup.py file answers "what package dependencies are required to build it".

- The "tool.setuptools.packages.find" table of the TOML file specifies where the setup function is going to start 
traversing through the project to find the packages that are to be installed using the pip pkg manager.

## Installing packages

It is recommended to use the "editable" mode when installing these packages with pip, as any changes to the 
project's packages are going to be reflected within the project without having to re-install the packages in the 
aftermath. From what I'm understanding at this point, configuring the project in this way makes the requirements.txt file obsolete. Note that setup function arguments can include fields such as the name, the version, etc. However, it is redundant to include this information, as it's already defined in pyproject.toml.

___

##### Sources

Hopkinson, Ian. “Understanding setup.py, setup.cfg and pyproject.toml in Python.” SomeBeans, 10 Mar. 2025, ianhopkinson.org.uk/2022/02/understanding-setup-py-setup-cfg-and-pyproject-toml-in-python.

Van Der Geer, Rogier. “A Practical Guide to Using Setup.py | Xebia.” Xebia, 22 June 2026, xebia.com/blog/a-practical-guide-to-using-setup-py. 