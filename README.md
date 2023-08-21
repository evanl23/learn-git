# Learning Git

This project is intended to get you up to speed with the software tools Git
and GitHub, which you will be using both during Quant and in your classes,
projects, and careers afterwards. This is not meant to be comprehensive. After
following the instructions [here](INSTRUCTIONS.md), you'll be able to use basic
Git commands such as clone, pull, add, commit, push, and others.

The purpose of this is to allow you to work on projects in groups. [Version
control software](https://en.wikipedia.org/wiki/Version_control) allows people
to a) maintain all previous versions of their files and directories for when
something goes wrong or changes, and b) give multiple users the ability to
work on the same project. From [large companies](https://github.com/google), 
to [startups](https://github.com/midjourney), to [open source 
projects](https://github.com/torvalds/linux), the world of software relies on 
version control. While it can be used for other things, we will focus primarily
on learning to add code, directories and documents to a small repository,
similar to what you will do this semester.

# About us

Learning Git is a project from the [BU Quantitiative Finance
Club](https://bufcinvest.com/programs-quant-finance/). Feel free to check out
other resources on our GitHub page [(BU Alpha)](https://github.com/bualpha).

# About Git and GitHub

[Git](https://git-scm.com/) was created by Linus Torvalds in 2005 to manage 
the Linux kernel. It is "a free and open source distributed version control
system designed to handle everything from small to very large projects with
speed and efficiency."
* free and open source - we don't have to pay to use it
* distributed - everyone has a copy of the code (not centralized)
* version control system - what we talked about above; a system that helps us
manage changes with our sofware projects

[GitHub](https://github.com/) is a platform (a company) started in 2007 by
Tom Preston-Werner, Chris Wanstrath, and P.J. Hyett. It was bought by
Microsoft in 2018, and is still owned by them today. GitHub allows users to
track, store, and manage their code through the Internet. It provides
additional features such as forking, pull requests, repositories, and other
features that make managing projects (especially open source ones) easier.

What are the differences between the two?
* Git is the software we use to manage our projects. GitHub is a platform
that hosts our projects and allows us to use Git better.
* Git is an open-source project. GitHub is a company.
* Git operates on the command line (your terminal), while you use GitHub on
the Internet.
* Git is a local program downloaded onto your computer that stores
repositories and code on your device. GitHub hosts repositories on its servers
("in the cloud").

For more on the differences between the two, see:
* [Stack Overflow](https://stackoverflow.com/questions/13321556/difference-between-git-and-github)
* [Hacker News](https://news.ycombinator.com/item?id=35787102)
* [Reddit](https://www.reddit.com/r/learnprogramming/comments/nh448l/github_or_stack_overflow/)

# Setting up Git

Now that we know what Git and GitHub are, let's set them up before we
learn how to use them.

## Creating a GitHub account

To create a GitHub account, go to [their website](https://github.com/) and
follow the steps to sign up.  We recommend using a personal email to set up
your account rather than your school one, but you can change that field after
you create your account.

For a step-by-step guide, [follow the steps
here](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account).

## Downloading Git

This is a bit more tricky, and will depend on the type of operating system you
have.

### Apple

If you are using MacOS, there are several guides that will help you here:
* [GitHub](https://github.com/git-guides/install-git) - two options, depending
on if you already have homebrew or not
* [PhoenixNAP](https://phoenixnap.com/kb/install-git-on-mac) - step-by-step
guide for using the installer, Xcode, homebrew, or MacPorts

If you are not familiar with your command line, try using the installer first
before moving to the command line to link your GitHub account.

### Windows

Again, here are two guides that can help:
* [GitHub](https://github.com/git-guides/install-git) - follow the instructions
for downloading Git (or Git Bash) onto your computer
* [How-To 
Geek](https://www.howtogeek.com/832083/how-to-install-git-on-windows/) - if 
you're feeling a bit lost, this offers more of a step-by-step guide on how
to install Git

## Configuring Git and GitHub

Now that you have downloaded Git and GitHub, it's time to configure the two.
The goal here is to link your GitHub account to the Git software that you just
downloaded onto your computer. Once you do this, your commits, repositories,
and other things you do on your computer will appear when you go online and
look at your GitHub account.

There are two parts to this step: setting your Git username and email, and
authenticating yourself.

### Setting username and email

To set your username and email, follow the instructions for steps 2 and 3
on [this webpage](https://docs.github.com/en/get-started/quickstart/set-up-git).
For your username, follow the instructions for setting your Git username for
every repository on your computer (unless you have a reason not to). For
your email, associate the email address you signed up with (your school or
personal email) with your Git, and set this for every repository again.

NOTE: If you are an Apple user, you should be executing these command-line
commands on your normal terminal. If you are a Windows user, you should be
executing these commands in your Git or Bash terminal that you downloaded
earlier, NOT your Windows command line.

### Authenticating yourself

For this part, I recommend [adding an SSH 
key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
Personally, I've found this easier to set up and deal with. You can also [set 
up with 
HTTPS](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git).

For all of these steps, ChatGPT and other AI tools are your friend. If you do
not want to read the error messages your computer throws at you, ask your
questions to an AI assistant and let the struggles of other users in its
training set help you with your own.

# Next steps

Congratulations! You're ready to use Git. Next, [learn how to use your new 
tools](INSTRUCTIONS.md).