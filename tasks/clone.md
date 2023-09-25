For this task, the goal is to learn the following commands:
- git clone
- git status
- git add
- git commit
- git push
- git status
- git diff

We will do this using a task of adding your name to a text file (names.txt).

//TODO
- [x] Write out instructions on what to do
- [] Take screenshots as you go through the steps and add to this file
- [] Explain what happens in each command


--------

# Cloning a repository

The first step in using git and GitHub is to create or copy a repository. To
create a repository, you have two options. First, you can create a local git
repository on your computer using the command `git init`. This sets up a .git
subdirectory in your current directory, creates a new version branch, and
allows you to use version control in your code; however, this does not do
anything related to GitHub. Second, you can create a GitHub repository by
clicking the '+' button on the top bar, then "New Repository". From there, you
can customize your inital setup of the repository and create it. This does not
create a repository on your local computer, however.

To get a repository on both GitHub and your computer using git, you typically
first create the repository on GitHub. Next, you clone the repository using the
command `git clone`. Your first task is to clone this repository, adding a
copy of it to your machine/laptop. You will then make an edit to one of the
files in the repository and "commit" this edit, updating the repository for
everyone who has it to include your edit

## Cloning learn-git

To clone this repository, first go to the main page (bualpha/learn-git). At the
top of the page, you will see several buttons, one of which is green and says
'<> Code'.

![Code button](/img/code_button.png)

Click this button, then go to the 'SSH' tab and copy the address you find there.

![SSH button](/img/ssh_button.png)

Open your git bash (Windows) or command line (Mac) and navigate to a directory
where you would like to add this directory. I have mine in a directory called
"Git Repos". To navigate to this using the command line, use the command `cd`
(change directory) followed by the name of the directory you'd like to enter.
To see the directories that you can go to, use `ls`. To make a new directory
(if you want one for this repository), use the command `mkdir <your new name>`.
These are all commands using Bash syntax, so if you get confused here, look up
how to create a new directory, how to change directories, use ChatGPT, etc.

Now, you should be in a location in your file tree where you want to add this
directory (learn-git). To do so, type the following command:

    git clone git@github.com:bualpha/learn-git.git

You should see the following pop up:

![cloning repository](/img/git_clone.png)

You now have a copy of the learn-git repository (this one) on your machine.

## Editing a file

Next, you will edit the file `names.txt`, located under the "src" directory in
the repository. You can use any text editor you'd like to edit this file: your
basic notepad, VSCode, vi(m), emacs, Sublime, Coda, etc. Add your name to a new
line of the file and save your changes to the file in the editor you're using.

![adding name](/img/adding_name.png)

Next, we'll see how this edit changed our local repository. Go back to your
bash command line and run `git diff`. This will highlight the differences
between the files on your computer and the ones in the repository on GitHub.

// TODO: add image of using git diff

Note that `git diff` does not show information for files that you've just
created, but haven't included in your local repository yet. You can also use
the diff command more generally (`git diff <commit-id-1> <commit-id-2>`) to
track the differences between individual commits

## Committing your changes

Now that you've added your name to names.txt, let's commit your change to your
local repository. This allows your computer to store a version of the learn-git
repository that you've cloned that includes your changes. Think of this as
a system storing v0.11.5 of this repository's history on your device. Most of
the versions were edits not made by you, but your history now includes your
name update.

First, let's go back to the diagram of basic git commands:

// TODO: insert git diagram

We can check where we are in this chart by running the command `git status`:

// TODO: insert git status image

From the diagram, you can see the order of the commands we need, as shown by 
the arrows. Furthermore, from running `git status`, it is clear that we have
changes that aren't staged yet. This means that if we were to lose this file
for some reason (our text editor crashes, we spill coffee on our laptop, etc),
we'd lose the changes we've just made. We must use version control to prevent
this!

To create a new commit, we will first run the command `git add names.txt`. 
This stages the changes you've made, meaning that they are now in the "staging
area" of your repository, ready to be committed.

Next, let's commit your changes. The command for this is `git commit`. This
is not the only thing you should type, however. Every commit requires some
message to describe the change that you're making to the repository. This log
makes it easier to go back and determine what you were doing during that
commit. The command to run is:

    git commit -m "adding <insert name> to names.txt"

Now that you've committed your changes to your local repository, running `git
status` should show that you have no untracked changes (you just committed
them).

## Pushing to GitHub

Your local repository is now updated to reflect your changes. However, the
repository on your computer is different than the one on GitHub's servers. To
fix this, we need to run one final command:

    git push

Congratulations! You've make your first (of hopefully many) commits using the
git version control software. Next, let's learn how to create a branch in git.