# research-template
A suggested repository structure for research and analysis projects.

## Getting this Repository
You can clone this repository anywhere on your machine and copy the file structure into a new research project repository.
```bash
$ git clone git@github.com:thejunglejane/research-template.git
$ mkdir my-research-project # initialize a new project directory
$ cp -R research-template/. my-research-project # copy the repo contents into the project directory
$ ls my-research-project
README.md        analysis         bin              data             requirements.txt results
```

I use [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/) to bind project directories to virtual environments.
```bash
$ git clone git@github.com:thejunglejane/research-template.git
$ mkproject my-research-project # initialize a new project and virtual env
(my-research-project)$ cp -R ~/research-template/. . # copy the repo contents into the current working directory
(my-research-project)$ ls
README.md        analysis         bin              data             requirements.txt results
```

Once you've copied the repo contents into a new directory, set the remote URL for that new directory to a repository remote within your own GitHub organization or account. This will allow you to push and pull changes to your project instead of to the research-template repo.
```
my-research-project$ git remote set-url origin <URL>
```
Or, you can edit the .git/config file in the directory's root.
```
[remote "origin"]
  url = git@github.com:<your GitHub username or organizaztion>/<your repo>.git
  # url = git@github.com:thejunglejane/research-template.git
  fetch = +refs/heads/*:refs/remotes/origin/*
```

You will always have the original repository cloned (unless you delete the directory), and can always initialize new projects by copying its contents into a new directory and changing the remote URL to a new GitHub repo.

## Using This Repository
This repository is just a suggestion for what your research project repository might contain, and reflects the general structure of our research projects at [@CaseCommonsDataScience](https://github.com/CaseCommonsDataScience/).

#### Audit Branch
This repository has an audit branch that can be used for internal verification of results. The audit branch contains an additional audit/ directory that has its own analysis, queries, and scripts. The idea is, given a set of steps in the research design, we should be able to reproduce the results of the original analysis. The output of the analysis, queries, and scripts on the audit branch should match the output of the analysis, queries, and scripts on the master branch.
