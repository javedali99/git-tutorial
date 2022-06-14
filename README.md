
<p align="center"><a href="https://lab.github.com/"><img alt="Learning Lab bot" src="https://user-images.githubusercontent.com/16547949/62085817-83232580-b22a-11e9-8693-7c54205b04e5.png"></a></p>

<h1 align="center">Hands-on Tutorial: Introduction to Git and GitHub </h1>

This tutorial provides an introduction to version control systems using `git` and `GitHub`. It focuses on teaching you the techniques you need to actually get started.

We will use the ⌨️ Command Line Interface (CLI) (i.e. `Bash` for Windows and `Terminal` in Mac) to perform essential command line techniques. 

## Git
`Git` is a free and open-source version control software that provides you with a set of command line tools for tracking changes to your files. 

All of the files in a project directory (referred to as a `repository`, or `repo`) are tracked by a hidden `.git` file in the root of the project.  You can initiate a repository on your local machine with the `git init` command.  

Git allows you to roll back to a previous snapshot of your project called a `commit`.  When you want to take a snapshot of your work, you'll need to `add` your the changes to your files to a **staging area**.  You can think of a staging area (literally) like a staging area.  The changes that you want to be included in your next snapshot need to be put on stage in order to be captured by the `commit`.  Each time you take a snapshot (`commit`), you'll need to include a short message that describes the set of changes.  These steps fit together as follows:

![local git process](imgs/local-git-process.png)

<br>

Here is additional information on each (of these) `git` commands (note, this **_is not_** a full list -- see [documentation](https://git-scm.com/docs)):

| Command  | Function |
| ------------- | ------------- |
| `git init` | Initialize a new repository in the current directory. This creates a database to track file changes, which you **only do once** at the start of a project. |
| `git status`  | Reports any changes to the files in your repo. |
| `git add FILE-NAME` or `git add .`  | Adds a file or files (`.`) to the staging area. All changes to those files will be included in the next commit. |
| `git commit -m "Description"`  | Commits all changes to all files currently in the **staging area** to the repository. This takes a snapshot that you can return to and **must include a message** with `-m`.|

So far, the process described all occurs on your local machine. This is a good practice, but does not facilitate collaboration with others, or create a backup of your code. For these purposes, we'll use **GitHub**.

## GitHub
In order to share our code and collaborate with others, we'll need a publicly accessible (cloud) location where we can store our files (and file _history_) -- that's what GitHub is for.

GitHub is the most popular open-source web-based repository hosting service.  In addition to providing a great UI on top of a server that hosts your repositories, GitHub has a number of additional features such as issue tracking, wiki pages, and notifications that make it a great collaboration tool.  

The important thing to keep in mind is that GitHub doesn't just store the a copy of your code files in your repository -- it stores the **entire database of changes** to the files. This allows other developers to view the files at an earlier point in time.  


## To Get Started

1. Register for an account on [github.com](https://github.com/).

3. [Download, install and configure git](https://git-scm.com/). 

    - Windows users please install [Git for Windows](https://gitforwindows.org/).
    - Mac users: [Git for Mac](https://git-scm.com/download/mac) or install it using Homebrew: 

        ```bash
        brew install git
        ```

    
4. Make sure to set Git with your name and email address using the following commands on the command-line with your name and email address:

    ```bash
    # Enter YOUR NAME to set your name
    git config --global user.name "FirstName LastName"
          
    # Enter YOUR EMAIL to set your email. Make sure it is the email associated with your GitHub account!
    git config --global user.email "email@example.com"
    ```
This is important because Git will use this information when you work on a project.

>See [this article](https://help.github.com/articles/set-up-git/) for more information on setting up GitHub.

## Workflow Example
Here is _one_ example of a workflow you may choose when working with a project. Let's imagine that there's a repository online that you want to use as a starting point for a project. First, you may want **your own cloud copy** of a repository on GitHub. In order to start working on the files, you'll need to get them on your computer (they're still only in the cloud). To do so, you will clone **your repository** to your machine. This will create a local copy of the files **as well as their entire history** on your local machine. We'll use the terminal to clone the repository, but we need to get some information about it first. To get the URL location of the repository, click the **Clone or Download** button, then click on the clipboard icon to copy the URL to your clipboard:

<!--
![clone button on GitHub](imgs/clone.png)
-->

Then, on your terminal, you could use the `git clone` command described below.  Here is a diagram of the full process:

![git with github diagram](imgs/full-git-process.png)

<br>

Here are additional `git` commands that allow you to interact easily with GitHub:

| Command  | Function |
| ------------- | ------------- |
| `git clone REPO-URL` | Creates a new copy of a source repository, which typically exists on a remote server. Use this when you want to clone down a GitHub repository. This command will create a new subdirectory with the same name as the source repository. |
| `git push origin master`  | Pushes all commits on the `master` branch made since the last push to another repository (`origin`), typically across the network (e.g., to GitHub)  |
| `git pull`  | Pulls all commits made since the last pull from another repository, and attempts to merge those changes into your current files. |
| `git config` | Configure your GitHub account. You should run `git config --global user.name "Your Full Name" and `git config --global user.email your-github-email` to initially set up. |

