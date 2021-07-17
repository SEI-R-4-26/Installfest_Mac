# Installfest: Mac Users

![](giphy.gif)

## Overview

We'll be installing most of the necessary tools for software engineering in this lesson. These tools are what we'll be utilizing during the course. 

***It is so important that you follow all of these instructions to a T, without skipping ahead.  It is also very important, when working in the terminal, to ensure that you type everything exactly correctly before running the command. You are interacting with your computer's inner configurations, and each command should be treated with care and intention.***

## Objectives

- Install Slack App
- Install Homebrew
- Install Zsh and Oh-My-Zsh
- Install Node
- Install VSCode
- Install Git
- Install Python
- Install Heroku
- Install MongoDB
- Install Postgres

## Installing Slack

Slack will be our ***primary*** mode of communication throughout this course.  In order to get the most out of it you'll want to download the desktop application [HERE](https://slack.com/downloads/).

*It is not recommended to use the browser app during this course.*

## Installing Homebrew

Homebrew is a package manager for Mac OS. It makes installing programs fast and easy.

To install Homebrew, paste the following command into your terminal and hit the <kbd>return</kbd> key:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

The above command will perform the installation for you.

## Installing Zsh and Oh-My-Zsh

### Zsh Installation

What is Zsh? Zsh is a shell designed for interactive use. It provides us with useful shortcuts to execute terminal commands faster and also enables auto completion for those commands.

To install Zsh, execute the following command in your terminal:

```sh
brew install zsh
```

### Oh-My-Zsh Installation

What is Oh-My-Zsh?

> Oh My Zsh is an open source, community-driven framework for managing your Zsh configuration. It comes with a bunch of features out of the box and improves your terminal experience.

It also provides us with preset themes to make reading your terminal *much* easier.

#### To Install Oh-My-Zsh:

Execute the following commands in your terminal:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

```sh
chsh -s $(which zsh)
```

## Installing NodeJS

What is NodeJS? NodeJS is a JavaScript runtime that allows us to execute JavaScript outside of a browser.

To intall NodeJS, execute the following command in your terminal:

```sh
brew install node
```

To confirm your installation, execute the following in your terminal:

```sh
node -v
```

You should see a node version listed.

## Installing VSCode

VSCode is going to be our text editor of choice throughout the course. It provides us with a wonderful environment to run and test our code.

To install VSCode, execute the following command in your terminal:

```sh
brew install --cask visual-studio-code
```

Verify your installation by running:

```sh
code .
```

This should open a new VSCode window.

If the above does not work, open VSCode manually from your Applications folder.

Once a VSCode window opens, press and hold <kbd>cmd</kbd> + <kbd>shift</kbd> + <kbd>P</kbd> to open the *command palette*. In the command palette, type in `path` and choose the option:

> Shell Command: Install `code` command in PATH.

This should enable the ability to open VSCode from terminal with the `code .` command. Try it out.

## Installing Git

Git is a version control manager that we'll be using in conjunction with GitHub to manage code updates during this course.

To install Git, execute the following command in your terminal:

```sh
brew install git
```

Once the installation completes, execute the following commands in your terminal, ***one by one***, with your information inserted:

```sh
git config --global user.name "Your Actual Name Here"
```

```sh
git config --global user.email "your_email@example.com"
```

The name and email should be the name and email you use on GitHub.

### Setting Up GitHub Authentication

In order for GitHub to deem our machines as "safe" to push code, we need to setup an identification key known as an `ssh key`.

Enter the following commands in your terminal, with your information inserted:

```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

The above email should be your GitHub email!

You should see the following prompt:

```sh
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519): [Press enter]
```

Hit <kbd>return</kbd> to save it in a default file.

You'll now be prompted to password protect the ssh key, but we can skip this portion. When prompted with the following, **hit** <kbd>return</kbd> **to leave the password as blank, both times**:

```sh
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

Let's start the Mac OS ssh-agent. Enter the following command into your terminal:

```sh
eval "$(ssh-agent -s)"
```

Now copy the ssh key to your clipboard:

```sh
pbcopy < ~/.ssh/id_rsa.pub
```

To complete this setup, follow the instructions starting from Step 2 at this link **[HERE](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)**.

## Installing Python

Python is a popular language that we'll be learning in Unit 4 of this course.
Today, we'll be installing Python3.

To install Python3, execute the following command in your terminal:

```sh
brew install python
```

To confirm your installation, execute the following command in your terminal:

```sh
python3 --version
```

You should see a Python version listed.

## Installing Heroku

Heroku is a hosting site that we'll be using to deploy projects throughout this course.

Execute the following command in your terminal:

```sh
brew install heroku/brew/heroku
```

The formulae may not be latest, so we'll execute the next command to ensure the latest Heroku version is installed:

```sh
heroku update
```

## Installing MongoDB

MongoDB is a document-based database that we'll be using in this course.

To install MongoDB, execute the following commands in your terminal, ***one by one***:

```sh
xcode-select --install
```

```sh
brew tap mongodb/brew
```

```sh
brew tap | grep mongodb
```

```sh
brew install mongodb-community@4.4
```

To start the mongo service:

```sh
brew services start mongodb-community@4.4
```

**NOTE**: The above command will keep MongoDB running in the backround on your machine even after shutdown.

To confirm your installation, enter the following command in your terminal:

```sh
mongo
```

An interactive shell should appear. To exit this shell, enter the following command:

```sh
exit
```

## Installing PostgreSQL

PostreSQL is going to be our column-based database of choice for this course. PostgreSQL is an open source relational database management system (RDBMS).

To install PostgreSQL, execute the following command in your terminal:

```sh
brew install postgres
```

To confirm the installation, run the following command in your terminal:

```sh
postgres --version
```

Next, enter the following command in your terminal:

```sh
brew services start postgresql
```

This will ensure postgres remains running on our machines.

Now, create a database with your username:

```sh
createdb `whoami`
```

Confirm that you can enter the postgres shell with the following command:

```sh
psql
```

To exit the shell:

```sh
\q
```

## Recap

At this point, we've successfully installed all of the tools we'll be utilizing throughout this course!

## Resources

- [Github SSH Keys](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- [Mac Setup Guide](https://sourabhbajaj.com/mac-setup/)
