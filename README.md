# Project Komquat

## Overview

Every document quacks, or hacks. I've made my process of working on project repositories somewhat easier with a templated set of standard documents that can be requested for any software project.
Technical documentation is organized in different branches:

```
# Branches storing programming languages for writing standalone scripts that run on your local machine or CI/CD 
pipeline scripts
programs/<PROGRAMMING_LANGUAGE>

# Branches storing programming languages for writing applications using a language-based framework
applications/<PROGRAMMING_LANGUAGE>
```

## How to use this project
```
wget -O <LOCAL_FILENAME> <GITHUB_LINK_TO_RAW_FILE>

# Example:
wget -O ~/my-repository/README.md https://github.com/DaniSestan/project-komquat/raw/refs/heads/programs/python/README/README.md
```

OR

```
git clone git@github.com:DaniSestan/project-komquat.git
git checkout <BRANCH>
git pull git@github.com:DaniSestan/project-komquat.git --all
git push git@github.com:DaniSestan/project-komquat.git --all
cp README/README.md <LOCAL_FILEPATH_OF_README>
```

## Additional Information

Useful documentation templates available online:
* [Git-Cliff](https://git-cliff.org/): CHANGELOG generator
* [GitHub gitignore](https://github.com/github/gitignore/tree/main): gitignore templates officially maintained by GitHub
* [The Good Docs Project](https://thegooddocsproject.dev/): Open-source collection of software documentation templates
