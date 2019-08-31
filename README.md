# Installfest 2019

![](giphy.gif)

Photo Credit: Erinn Nelson

_Objectives_

Install core packages and services for SEI.

This includes:

- Homebrew
- nvm and Node.js 12.9.1 and npm 6.10.2
- rbenv and Ruby 2.6.4
- Postgresql 11.5
- VS Code 1.37
- git

## Homebrew

[Homebrew](https://brew.sh/) is an extremely popular and easy to use package manager for macOS. This is the tool we will use to install all of the software we need for this course.

Install homebrew from the command line with the command:

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
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

### Oh-My-Zsh!
First, we will change the default "shell" or terminal environment to use one that is more friendly for developers.

Open the `Terminal` app and type the following two commands (Hit `<Enter>` after each):
```
brew install zsh zsh-completions
```

Verify installation by running `zsh --version`. Expected result: zsh 5.1.1 or more recent.

Install oh-my-zsh 
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Close and reopen your terminal app again to use your new default shell.
Test that it worked with 
```echo $SHELL```
Expected result: /bin/zsh or similar.

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
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

Ensure that node is installed with the following commands.

```
nvm install 12.9.1
```

### VS Code

```
brew cask install visual-studio-code
```

Open VS Code by typing `code` at the terminal.

Type `Command + comma` and click this icon ![](settings.png) on the top right to open the `settings.json` config file.

Copy and paste the options from the following gist and save:

https://gist.git.generalassemb.ly/davidtwhitlatch/7b428260fee52ab113030751731ba97c

On line 9 of the `settings.json`, replace `<YourUsernameHere>` (including the angle brackets) with your username.
If you need help finding your username, type these commands into terminal:

```bash
cd ~/
pwd
```

If you have a user of "David Whitlatch", you would return something like `/Users/davidwhitlatch`. That means that line 9 of `settings.json` will look like:
```
"eslint.nodePath": "/Users/davidwhitlatch/.nvm/versions/node/v12.9.1/lib/node_modules",
```

Finally, install the required linter packages with the following line in the terminal:
```
npm install -g eslint-config-airbnb-base eslint eslint-plugin-jsx-a11y eslint-plugin-import eslint-plugin-react
```
