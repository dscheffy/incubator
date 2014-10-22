# Incubator

This project is intended to how a company that's too cheapo to pay for more private repositories can use branches on an incubator project to incubate new applications while their waiting for the finance group to give the go-ahead on creating a dedicated github hosting repository for them.

## Usage

**Don't commit anything to master!**

The only thing you should see on the master branch of this repo is this readme file.

### Incubating a new Project

#### From scratch

For the less command line savvy the easiest way to do this may just be to use the github webui.

1. Assuming you're viewing this README from the main page of this repo, click on the `branch: ...` button above (read ahead before you continue because this page will disappear).
2. Select the branch called `initial-commit`.
3. Click on that same `branch: initial-commit` button again.
4. This time type the name of the branch you want to create in the text box:

    incubate/<your-project-name>

5. Type enter and your new branch should be created.

Now that your branch is created on Github, you just have to clone it locally. In your terminal, navigate to your usual development folder where you maintain your various projects and type (remember to replace <your-project-name> with your actual project name):

    git clone --single-branch --branch incubate/<your-project-name> https://github.com/dscheffy/incubator.git <your-project-name>

Now you should be able to `cd` into that new project directory and develop for the most part like you would with a standard github repo.

#### Merging in an existing repo

If you already have an existing git repository (i.e. you've been working locally so far, making lots of commits, but now you'd like to share youre work with the world...) use the following commands from the root folder of your repo to merge (rebase) it ontop of the _initial-commit_ of the incubator repo.

> Note, you may get an error from the first line if your repo doesn't already have a remote origin (you can ignore the error).

```
git remote remove origin
git remote add origin https://github.com/dscheffy/incubator.git
git fetch
git checkout -b incubate/sample-project
git rebase origin/initial-commit
git push
```

### Contributing to an existing Project


### Noteworthy Branches

Of all the branches in this repo, the following are being considered for leaving incubation. Paste the clone command into your terminal to clone that branch into a dedicated directory the way you would normally clone a standard repository.

branch | clone command
-------|--------------
[sample application](../../tree/incubate/sample-app)|`git clone --single-branch --branch incubate/sample-app https://github.com/dscheffy/incubator.git sample-app`
[sample project](../../tree/incubate/sample-project)|`git clone --single-branch --branch incubate/sample-project https://github.com/dscheffy/incubator.git sample-project`