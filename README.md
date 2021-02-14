# Tutorial to get started on Github - CSE17

Git is a free and open-source version control system that will help you keep your code organized and centralized in one place. We will be using this tool for each assignment throughout the semester, so it is important to get set up as soon as possible. This tutorial should get you started on Github including git installation, basic git commands, and step-by-step guide to using Github. You can also find more in-depth documentation and video guide from these links: 

### I made a quick video for using Github directly from Eclipse: https://drive.google.com/file/d/1t8UWlHSygKYDKDGYmhtUl0m_IhN_1swj/view?usp=sharing
### Documentation: https://training.github.com/downloads/github-git-cheat-sheet/
### Video and article guides: https://www.youtube.com/watch?v=SWYqp7iY_Tc https://towardsdatascience.com/learn-basic-git-commands-for-your-data-science-works-2a75396d530d

<br />

# Git and Github Introduction
Git is a version control system, but what is a version control system? Developers who create software are constantly changing their code; they build new code, release new versions of software, and maintain old versions for compatibility. Version control systems like git help organize these constant revisions in a single centralized area. For us, this centralized area is within Github repositories.

Although Github is sometimes summarized as a website for online storage and sharing of code, it is so much more than that! Github integrates and adds many tools to Git; these tools help collaboration between teams of developers, sharing of open-source software where people can access and download, and last but definitely not least, the secondary function as a social network. By keeping your code organized on your own Github account, interested parties like interviewers, researchers, and software developers can easily see your contributions and skills.

Git and Github are some of the most powerful tools you can use as a professional, not limited to software development. I will explain multiple concepts of git and Github, and show different ways to upload to Github.

<br />

# Key Terms
- Repository - Analogous to a folder in Google Drive or dropbox. This is a space where you can upload files to and download files from using git commands. A repository on Github is a site. A repository on your local machine is a directory where git commands will work.

- Commit and Add - Commit is a record of what changes have been made since your last commit. Commits will package the changed files and get it ready to be uploaded. Before this, however, you need to tell git what files to commit first. It will not automatically commit EVERY change. In order to do this, you simply add files to a "stage", and these files can then be committed.

- Branch - Let's say you want to add a whole new feature to your code, but you're worried the features might break everything. You can create a branch separate from a main branch so you can maintain a "copy" of your code in main while working in another branch. You can easily switch between these branches or
    - Merge - Merging the branches will combine your changes from both branches into one (note: you might come across conflicts when merging branches)

- Push - Push will upload your commits to a Github repository.

- Pull - A pull request is one of the strongest features for code collaboration. When you pull someone else's repository, you tell the repository's owner that you want to make changes to their code. If you commit these changes, the owner can review your code before "merging" your changes to their code.

Now that we have some terminology, let's look at different ways to upload.

# Method 1: Easiest but most limited in capability
This one is the most straightforward! You will not be able to see what files you have added to the stage, nor what you are committing. I also personally don't see an intuitive way to merge or pull, however uploading and downloading with this method is as easy as using Google Drive.

If you want to download files from a Github repository, navigate to the repository and click "Code". A dropdown menu will allow you to "download ZIP". You can unpackage this ZIP file and use the files.

To upload files to a repository, simply click "Add file" and it will give you the option to upload files. This works with drag-and-drop!

# Method 2: Github GUI
I don't have any personal experience with this method, but have heard that most of the git functionally are easily accessible here. The biggest issue is that you will not always have a GUI to work with, such as if you are uploading files from the Sunlab or other server.

# Method 3: My recommendation - Mildly harder to learn
I say this method is mildly harder to learn because it requires knowing basic UNIX commands to navigate terminal/command line, and memorizing ~10 git commands to have all basic functionality offered by the other methods. This method is the most powerful, however, offering many more additional commands for complete control over git as well as rigorous documentation.

<br />

## Installing Git
For Linux - You can install Linux from the terminal by using the following scripts:

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install git
```
You can find the download here: https://git-scm.com/downloads

<br />

## Setting up Git
You can use your native terminal or Git Bash. I would suggest using the terminal or git bash.
Open you have your preferred terminal open, first make sure git is correctly installed with

```
git --version
```

You want to first provide a username and email using the following lines. This is important because each time you download/upload code to Github, this information will be attached.

```
git config --global user.name "your-username-here"
git config --global user.email "your-email-here"
```
Make sure this email is the same as your Github account email.

<br />

## A few basic commands to start using git
```
$ git init        // Initialize a local folder in your computer as a git repository. 
                  // It initializes in your current working directory, 
                  //  and you will not need to access the ".git" folder that is automatically created.
                  
$ git add <file>  // This adds a file to a list of files to be "committed" (commit means to declare changes to Github).
                  // "git add ." will add all files in the folder to the index, instead of only one.
                  
$ git status      // Check status of working tree. This will show whether files in your local repo have been added or not.

$ git commit      // This commits your changes
                  // Alternatively, you can use "git commit -m 'a-comment-on-what-you-changed-here'

$ git branch      // Lists all branches that are accessible.
                  // "$ git branch <branch-name>" will create a new branch
                  // "$ git checkout <branch-name>" will switch you over to another branch

$ git remote add <remote-name> <url to github remote repository> 
                  // Creates a connection to the remote repository under the name <remote-name>. 
                  // You will be able to access this remote connection at anytime even after closing terminal.
                  // "$ git remote" will show you all remote connections that have been made already
                  
$ git push <remote-name from above> <branch-name>
                  // Uploads your local repository to the remote repository.
```

There are plenty of other git commands that can do things like view entire version history and changes, revert back to a previous version, easy re-download from github when collaborating, or exclude specific files from being tracked by git. You can find many of these in the cheat sheet (https://training.github.com/downloads/github-git-cheat-sheet/) as well as the full git command list (https://git-scm.com/docs/git#_git_commands).

## Typical work flow

Below is an example of how you would typically upload an assignment.

```
// First either clone a template repository when starting a new assignment or 
// pull the most current version of the repository if you're continuing to work from a previous commit.

// Since we provide all the repositories that you work in, you can simply just clone the repo each time.
$ cd <directory-to-work-in>
$ git clone https://github.com/CSE17-Houria-Oudghiri/Tutorial.git     
                  // This will be the URL of the repository you want.
                  // Note that this repository is already initialized so you don't need git init.

$ git remote add Origin https://github.com/CSE17-Houria-Oudghiri/Tutorial.git

// Now you cloned all the files to your current working directory. Work on your code as normal. 
// Your remote connection will still be there if you close your terminal. Once you have code you want to add to Github:
$ git add .
$ git commit -m "1st Commit"
// Let's say you don't want to add this commit. You can use "$ git reset" to unstage your commit.

// Finally add file to the Github repository. It should be uploaded after this. 
$ git push

// When you pick the code back up later, you can just start from $ git add .
```

