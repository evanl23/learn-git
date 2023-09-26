For this task, the goal is to learn the following commands:
- git branch DONE
- git checkout
- git switch DONE
- git merge DONE
- git rebase
- git log
- git restore

checkout - like checking a book out from the library
creating a branch
renaming a branch
switching branches
push branch to remote repository
merging
rebasing
delete a branch after merging

For this activity, the task is to create three different branches with three
versions of one python file. We will have a separate example from what they
will be working on. Ours will be a script to print prime numbers. Theirs will
be scripts for three project euler problems (1, 4, 7)

TODO

- [x] overview of branching in git
- [x] create a branch called newbranch
- [x] rename this branch to multiples
- [x] write code for multiples (problem 1)
- [x] create new branch called pallindrome
- [x] switch to this branch
- [x] write pallindrome.py (problem 4)
- [x] merge with main branch
- [x] merge pallindrome with main branch
- [ ] delete branches after merging to main
- [ ] use rebase to deal with merge conflict
- [ ] give them third problem to do on their own
- [ ] with third problem, do NOT delete branch after merging - will use for
next task (undo)
- [ ] explaining checkout command vs. switch and restore

--------------
# Branches in git

Branches are a key part of git. Branching allows you to take your repository
from a certain moment in time and "branch" into other states, depending on
what you're trying to do. Below are a few diagrams that shows repositories with 
different branches, where the x-axis is time, or commit history:

![git branch, git version](/img/branch/git_branch_git.png)

![git branch, simple version](/img/branch/git_branch_simple.png)

![git branch, less simple version](/img/branch/git_branch_complex.png)

To list the current branches in our repository, we can run the command `git
branch`:

![one branch](/img/branch/one_lonely_branch.png)

As you can see, we only have one branch in our repository right now, `main`. You
will soon add more as you begin your task.

Here is a brief overview of the tasks you will do here:
- Create a branch
- Write code for your first problem, `multiples.py`
- Create a second branch
- Modify this branch and write code for your second problem, `pallindrome.py`
- Merge your first and second branches to your `main` branch, deal with merge
conflicts
- Delete your first two branches and create a third branch to solve your
third problem, `prime10001.py`


## Solving the first problem

Your first problem to solve (in Python) is the following:

    Find the sum of all the multiples of 3 or 5 below 1000.

In order to write code on our future branches, we must first create a new
branch. To do so, run the command

    git branch newbranch

This will create a new branch in your local repository called `newbranch`,
where you will write your code for the first problem. However, `newbranch` is
not a good name for this branch. It gives us no information about what the
branch is for. To rename your new branch, run

    git branch -m newbranch multiples

This renames the branch you've just created from `newbranch` to `multiples`. The
`-m` flag stands for "move", which is similar to the bash command `mv`. This
command can also be used to rename files; likewise, the `-m` flag can be used
to rename our branch.

To change our branch from `main` to `multiples`, use the command `git switch`,
and append the branch name you're switching to. This command allows us to
change which branch we're on in our local machine (laptop, computer, etc.).

Next, write your code for the first problem. Create a file named `multiples.py`
using your text editor of choice, and write code that comes up with a solution.
Add `multiples.py` to the `src` directory (the one that has `names.txt`). If
you want to check your solution, go to
[this page](https://projecteuler.net/problem=1), create an account, and submit
your answer. Come back here once you've solved the problem.

Now that your file is all good to go, commit your changes to the `multiples`
branch (don't push them). Note that you are committing to a branch. If you
switch back into your `main` branch, you'll notice that the file 
`multiples.py` doesn't appear in your `src` directory (or wherever in the
repository you put it). Before we fix this, let's solve our second problem.

## Solving the second problem

Switch back to your main branch, and create a second (or third, depending on
your perspective) branch named `pallindrome`. In this branch, create a file
`pallindrome.py` that solves the following problem:

    Find the largest palindrome made from the product of two 3-digit numbers.

Again, you can check your answer using
[this page](https://projecteuler.net/problem=4) after setting up your account.
Come back here once you've solved the problem.

## Merging solutions

Now, your git repository on your local machine should look something like this:

//TODO: Create fancy diagram using some drawing or sofware tools

At this point, you should have three branches: `main`, `multiples`, and
`pallindrome`. `multiples` should have a file called `multiples.py`, and
`pallindrome` should have a file called `pallindrome.py`. Now that we've
made our changes in each of our branches, it's time to merge them together!

### Merge `multiples`

To merge your `multiples` and `main` branches, make sure you are on the `main`
branch of your repository. Run the command

    git merge multiples

This will merge your branch into the repository, assuming that no conflicts
exist. For this problem, there should be no conflicts, as the only difference
between your `main` and `multiples` branches should be the solution file you
created.

### Merge `pallindrome`

Peform the same commands to merge your `pallindrome` branch. Again, make sure
you are on your main branch before merging. There should be no merge conflicts
here, as you are adding a different file (`pallindrome.py`) that is not in
your `main` branch already.

## Deleting your branches

Now that both branches have been merged with our `main` branch, we don't have
a need for them in our repository. We can delete the `multiples` branch of the
repository with the `-d` option of `git branch`:

    git branch -d multiples

Do the same now for the `pallindrome` branch of the repository. Now, when you
run the command `git branch`, you should only see the `main` branch of your
repository.

## Surprise assignment: merge conflicts

To this point, you haven't had to deal with any merge conflicts in your
repository yet. What happens if we have such a conflict? Let's create one
and find out.

Create a third new branch (fourth total) and name it `hello`. In both your
`main` and `hello` branches, create a file. Name the file `hello.txt`. In the
`hello` branch, write `hello` in the file, and in your `main` branch, write 
`goodbye`. Commit `hello.txt` twice, once in each branch.

At this point, we now have two branches with different copies of a file with
the same name. What happens if we attempt to run `git merge hello`?

![merge conflict](/img/branch/merge_fail.png)

It appears we have a conflict! On our `hello` branch, `hello.txt` is

    hello

However, on our `main` branch, `hello.txt` is

    goodbye

To move forward with our repository, we need to merge this conflict. Since we
want to make a compromise here, we want our file `hello.txt` to look like:

    hello
    goodbye

//TODO: can insert screenshots here if needed; this part below can get a bit
confusing

Note: if we were dealing with path and filename conflicts, we could do this
using `git add` and `git rm`. However, we are dealing with the contents of a
file, so we need to tackle that head-on.

There are several ways to deal with merge conflicts; one common way is to
use the command `git mergetool`. This will lead you to a window with three
screens: the two files that are in conflict (up top), and the result of the
merge (below). In the window below, try to make the text file look like the
output above. The default text editor used by git is `vim`. The key bindings
and functionality can be confusing at first, but it is a very powerful editor
(except for those who know emacs). You can either learn enough `vim` commands to
make these edits, or change your mergetool config file to add a new text editor
to handle merge conflicts. 

Once you're done, commit again. Congratulations, you've handled your first
merge conflict! Celebrate by getting rid of the `hello` branch (and your
`hello.txt` file if you'd like). Now, let's move on to the third problem
assigned.

## Brief interlude: git checkout

The `git checkout` command has a long history in Git. Originally, it served
three primary functions:

- Switching branches
- Checking out file contents from different commits
- Discarding changes in the working directory

As Git evolved, the `checkout` command ended up doing too many different things.
This made it confusing for new users to learn. 

So in recent versions of Git, the `checkout` command was split into two
separate commands:

- `git switch` - for changing branches
- `git restore` - handles undoing changes to files

The `git restore` command is used for undoing changes in your working
directory. It lets you restore files back to how they looked in an older commit.

If you'd like more information about this, see either
- [Stack Overflow](https://stackoverflow.com/questions/57265785/whats-the-difference-between-git-switch-and-git-checkout-branch)
- [git v2.23 release 
notes](https://github.com/git/git/blob/master/Documentation/RelNotes/2.23.0.txt)

## Solving the third problem

By this point, you should have enough knowledge to handle your third task.
Create a branch called `primes`, and in this branch (under the `src` directory
create a file named `primes.py` that solves the following problem:

    What is the 10001st prime number?

Again, you can [check your answer here](https://projecteuler.net/problem=7).
Now, merge your solution branch to your `main` branch. Don't delete your 
`primes` branch, however; you'll need this for your next task.

Once you've solved this third problem, [learn about undoing a 
change](/tasks/undo.md) in your next task.