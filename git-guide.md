# Guide for working with workshop repositories via Git

Git is a version control system - a program that keeps track of all the changes of files in a folder on your computer. Using it you can browse through the history of changes, revert back to a saved state, keep track of several "branches" of different changes and share your "work-in-progress" projects with others, while retaining the whole "progress".

To use it, first you have to install Git itself.

## Git Installation

Instructions mostly taken from here: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

### Windows

Go to this page and click the link "Click here to download" - https://git-scm.com/download/win


This should download the installer that will install Git just like any other program.

At one of the steps during installation, you will be asked if you want to add Git to PATH. This means that you will be able to use Git console commands from Powershell or cmd (that is, regular Windows terminal) without specifying the whole path to the Git executable.

In simple terms, adding Git to PATH means you can do `git <command>` in regular terminal, instead of writing `C:\Program Files\Git\bin\git.exe <command>`. However, if you use the Git terminal (which is installed together with Git), you will be able to use the commands even if Git is not in your PATH.

I would add Git to PATH, as there are few downsides to this.

### Mac

If you installed Xcode Command Line Tools, you already have Git. Otherwise, you can go to https://git-scm.com/download/mac and choose "Binary installer".

## GUI Installation (optional)

Git is a command line application, meaning it doesn't have its own window, and to run it you just write commands in the terminal. However, there are some applications that allow you to use Git through graphical interface.

GUI clients can simplify your work if you prefer graphical applications. You can find the list of clients here: https://git-scm.com/downloads/guis

I personally used TortoiseGit (Windows only) and GitKraken (all systems), but you can choose any client from here, as you will mostly need only simple commands. GitHub Desktop should be a simple enough one.

There is also the Git GUI client that comes with  Git itself (automatically on Windows, can be installed separately on Mac via Homebrew). It is very simple, but should also be enough for this course.

## Git workflow for workshops

### Downloading repositories

A remote repository (for example, a GitHub one) can be downloaded using the command `git clone <link>`. The link can be an http one to the GitHub site, a SSH one (that allows to push your code to GitHub easier) or it can be a path to your local folder. This command creates a copy of that repository with all its branches.

Examples:

```
git clone https://github.com/dsba-z/week3cpp2021
git clone git@github.com:dsba-z/week3cpp2021.git
git clone ../../workshops/week3
```

### Saving your changes

As you work on your code, you might want to save your changes, especially if you want to have several versions (branches) of your code in the same repository.

Git only keeps track of special "saved states" of your repository folder: **commits**. To save something you must create a commit with the changes using the command `git commit`. However, there is an extra step where you have to figure out what to save. First, you use the command `git add file.cpp` to **add (stage)** a file to a potential commit. Then, as you added all the files you want, you can use `git commit` to save the new state of all added files.

A good tool to check that everything is as you expect it to be is the command `git status`. It tells you which files were staged for a commit and which files were not, as well as some other useful information.

An example should make this easier.

#### Example

You downloaded a repository. There are several tasks, and you changed a single file, `main.cpp` from problem 1. Now you want to save your changes.

```
git add code/src/problem1_name/main.cpp
git commit -m "Add solution for problem 1"
```

The first command here adds that file using its path. The second command creates a commit with the added file. Parameter `-m` means "message". Each commit has to include a message, and here the command includes it right away. If you write `git commit`, you will be asked to enter a message in a text editor. In many cases this text editor is *vim*, which is quite unintuitive in its use, so if you use a command line, try to always include `-m "Message"` in your commits.

Alternative version:

```
git add .
git commit -m "Add solution for problem 1"
```

In this version the added "file" is `.`, a single dot. A dot has a special meaning when used as a path, it means "current directory". If you use a directory to add files to a commit, Git will add all files in it. So, `git add .` means "add all files in the current folder (and nested folders)". Be careful not to add unnecessary files if you do this. Workshop repositories come with some filters, so that your `CMakeLists.txt.user` and you build directories don't get added to commits, but you never know what else might appear in your folders. Use `git status` to make sure you don't add anything unnecessary.

### Branches

Git is structured in a way where you can have different "versions" of your code and switch between them. These "versions" are called "branches". We don't need to go into detail about them now, and you should be fine for now if you work in the default branch `master`. I will mostly update branched with group names, so if you don't use them for your code, it should be fine.

You can switch between branches with `git checkout branch-name`. You can also switch to a branch that doesn't exist yet (that is, create a branch) using `git checkout -b new-branch-name`.

Be sure to commit your code before switching, otherwise you might lose the changes.

### Updating local repositories

After a workshop I usually update the GitHub repository with the results of that particular workshop. If you downloaded the workshop before that, you may want to update your local version, to load my new changes.

This operation is called "pull" and "fetch" in Git. Here I will use "pull". To pull the changes:

1. Switch to the branch you want to update. For example: `git checkout 215-1"
2. Run the `pull` command with the corresponding branch. `git pull origin 215-1`

This should do it if you haven't changed anything locally for that branch.
