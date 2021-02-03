# Tutorial to get started on Github - CSE17

Git is a free and open-source version control system that will help you keep your code organized and centralized in one place. We will be using this tool for each assignment throughout the semester, so it is important to get set up as soon as possible. This tutorial should get you started on Github including git installation, basic git commands, and step-by-step guide to using Github. You can also find more in-depth documentation and video guide from these links: 

### I made a quick video if you want a visual guide: https://drive.google.com/file/d/1t8UWlHSygKYDKDGYmhtUl0m_IhN_1swj/view?usp=sharing
### Documentation: https://training.github.com/downloads/github-git-cheat-sheet/
### Video and article guides: https://www.youtube.com/watch?v=SWYqp7iY_Tc https://towardsdatascience.com/learn-basic-git-commands-for-your-data-science-works-2a75396d530d

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
You can use your native terminal, Git Bash, or download the Git GUI. I would suggest using the terminal or git bash.
Open your preferred terminal and first make sure git is correctly installed with

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
                  //  and you will rarely need to access this ".git" folder.
                  
$ git add <file>  // This adds a file to a list of files to be "committed" (commit means to declare changes to Github).
                  // "git add ." will add all files in the folder to the index, instead of only one.
                  
$ git status      // Check status of working tree. This will show whether files in your local repo have been added or not.

$ git commit      // This commits your changes
                  // Alternatively, you can use "git commit -m 'a-comment-on-what-you-changed-here'


$ git remote add <remote-name> <url to github remote repository> 
                  // Creates a connection to the remote repository
                  
$ git push <remote-name from above> <branch-name>
                  // Uploads your local repository to the remote repository.
```

There are plenty of other git commands that can do things like view entire version history and changes, revert back to a previous version, easy re-download from github when collaborating, or exclude specific files from being tracked by git. You can find many of these in the cheat sheet (https://training.github.com/downloads/github-git-cheat-sheet/) as well as the full git command list (https://git-scm.com/docs/git#_git_commands).

## Typical work flow

Below is an example of how you would typically upload an assignment.

```
// First either clone a template repository when starting a new assignment or 
// pull the most current version of the repository if you're continuing to work from a previous commit.
$ cd C:\Users\Justin\I-want-the-folder-here
$ git init
$ git remote add Origin https://github.com/CSE17-Houria-Oudghiri/Tutorial.git
$ git clone https://github.com/CSE17-Houria-Oudghiri/Tutorial.git

// Now you cloned all the files to your current working directory. Work on your code as normal. 
// Your remote connection will still be there if you close your terminal. Once you have code you want to add to Github:
$ git add .
$ git commit -m "1st Commit"
// Let's say you don't want to add this commit. You can use "$ git reset" to unstage your commit.

// Finally add file to the Github repository. It should be uploaded after this. 
$ git push

// When you pick the code back up later, you can just start from $ git add .
```

