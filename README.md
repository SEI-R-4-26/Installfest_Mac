# Installfest 2020

![](giphy.gif)

_Objectives_

Install core packages and services for SEI.

This includes:

- Homebrew
- nvm, Node.js and npm
- VS Code
- git

## Homebrew

[Homebrew](https://brew.sh/) is an extremely popular and easy to use package manager for macOS. This is the tool we will use to install all of the software we need for this course.

Install homebrew from the command line with the command:

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

This install script will tell you the files it will create and ask for your password. **YOUR PASSWORD WILL NOT DISPLAY**, just keep typing.

After the install, you should see this printed in your terminal:

```shell
==> Installation successful!

==> Homebrew has enabled anonymous aggregate formulae and cask analytics.
Read the analytics documentation (and how to opt-out) here:
  https://docs.brew.sh/Analytics

==> Homebrew is run entirely by unpaid volunteers. Please consider donating:
  https://github.com/Homebrew/brew#donations
==> Next steps:
- Run `brew help` to get started
- Further documentation: 
    https://docs.brew.sh
```

### Zsh Time!
First, we will change the default "shell" or terminal environment to one that is more friendly for developers.

Open the `Terminal` app and type the following two commands (Hit `<Enter>` after each):
```
brew install zsh zsh-completions
```

Verify installation by running `zsh --version`. Expected result: zsh 5.1.1 or more recent.

Install oh-my-zsh 
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
You may see this message:

```shell
Caveats
To activate these completions, add the following to your .zshrc:

  if type brew &>/dev/null; then
    FPATH=$(brew --prefix)/share/zsh-completions:$FPATH

    autoload -Uz compinit
    compinit
  fi

You may also need to force rebuild `zcompdump`:

  rm -f ~/.zcompdump; compinit

Additionally, if you receive "zsh compinit: insecure directories" warnings when attempting
to load these completions, you may need to run this:

  chmod go-w '/usr/local/share'
==> Summary
🍺  /usr/local/Cellar/zsh-completions/0.32.0: 142 files, 1.1MB, built in 2 seconds
```
First we need to close our terminal and reopen it. You may get this message:

```shell
 zsh compinit: insecure directories, run compaudit for list.
Ignore insecure directories and continue [y] or abort compinit [n]?

```
If so, type `y`.

Next type `chmod go-w '/usr/local/share'` to activate the completions.

Close and reopen your terminal app again to use your new default shell.
Test to see if it worked with 
```echo $SHELL```
Expected result: `/bin/zsh` or similar.

### Git
Let's install `git` and a nifty helper for viewing files in the command line, `tree`.

```
brew install git
brew install tree
```

### Node.js

Finally, we will set up a runtime for using javascript from the terminal. For SEI, we will use nvm, a version manager for the Node runtime.

You can install nvm with the following terminal command:
Copying + pasting this is strongly recommended.


```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash
```

Restart terminal. (cmd + Q and re-open)

Ensure that node is installed with the following commands.

```
nvm install 14
```

### VS Code

```
brew cask install visual-studio-code
```

Open VS Code by typing `code` at the terminal.

Type `Command + comma` and click this icon ![](settings.png) on the top right to open the `settings.json` config file.

Copy and paste the options from the following gist and save:

https://gist.git.generalassemb.ly/davidtwhitlatch/7b428260fee52ab113030751731ba97c

### Extras
[ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)
[Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh)
