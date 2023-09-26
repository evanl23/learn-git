# Adding your name

Open your git bash (Windows) or command line (Mac, Linux) and navigate to a 
directory where you would like to add this directory. I have mine in a directory
called "Git Repos". To navigate to this using the command line, use the command
`cd` (change directory) followed by the name of the directory you'd like to
enter. To see the directories that you can go to, use `ls`. To make a new
directory (if you want one for this repository), use the command `mkdir <your
new name>`. These are all commands using Bash syntax, so if you get confused
here: look up how to create a new directory, how to change directories, use
ChatGPT, etc.

Now, you should be in a location in your file tree where you want to add this
directory (learn-git). To do so, type the following command (insert your
username, as it is your fork):

    git clone git@github.com:<your-username>/learn-git.git

You now have a copy of the learn-git repository (this one) on your machine.

## Sync your fork

Next, sync your fork to the original learn-git repository hosted by bu-alpha.

Run these commands in your terminal (in this order).

    git remote add upstream git@github.com:bualpha/learn-git.git
    git pull

## Editing a file

Next, you will edit the file `names.txt`, located under the "src" directory in
the repository. You can use any text editor you'd like to edit this file: your
basic notepad, VSCode, vi(m), emacs, Sublime, Coda, etc. Add your name to a new
line of the file and save your changes to the file in the editor you're using.

## Committing your changes

Now that you've added your name to names.txt, commit your change to your
local repository.

We can check where we are in this chart by running the command `git status`:

![git status for names.txt](/img/clone/git_status_names.png)

Run these commands in order:
    git add .
    git commit -m "adding <insert name> to names.txt"
    git push

## Next step

Next, go to `pr.md` to learn how to submit a pull request.