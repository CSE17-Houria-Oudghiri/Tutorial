# Tutorial to get started on Github - CSE17

Git is a free and open-source version control system that will help you keep your code organized and centralized in one place. We will be using this tool for each assignment throughout the semester, so it is important to get set up as soon as possible.

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
                  // You can use "git commit -m 'a-comment-on-what-you-changed-here'


$ git remote add
