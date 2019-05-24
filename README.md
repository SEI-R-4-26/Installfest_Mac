# Installfest

_Objectives_

Install core packages and services for SEI.

This includes:

- Homebrew
- nvm and Node.js 12.2 and npm 6.9
- rbenv and Ruby 2.6.3
- Postgresql 11.3
- VS Code 1.34
- git
- Google Chrome 74

## Homebrew

[Homebrew](https://brew.sh/) is an extremely popular and easy to use package manager for macOS. This is the tool we will use to install all of the software we need for this course.

Install homebrew from the command line with the command:

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

This install script will tell you the files it will create and ask for your password. **YOUR PASSWORD WILL NOT DISPLAY**, just keep typing.

After the install, brew will print an output describing where to find more information on how to use it.

### Oh-My-Zsh!
First, we will change the default "shell" or terminal environment to use one that is more friendly for developers.

Open the `Terminal` app and type the following two commands (Hit `<Enter>` after each):
```
brew install zsh zsh-completions
```

Verify installation by running `zsh --version`. Expected result: zsh 5.1.1 or more recent.

Make it your default shell: 
```
chsh -s $(which zsh)
```

Log out and login back again to use your new default shell.
Test that it worked with 
```echo $SHELL```

Expected result: /bin/zsh or similar.

Install oh-my-zsh 
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```


### Git
Let's install `git` and a nifty helper for viewing files in the command line, `tree`.


```
brew install git
brew install tree
```

### VS Code

```
brew cask install visual-studio-code
```

Open VS Code by typing `code` at the terminal.

Type `Ctrl P` and type `settings.json` to open the settings.json config file.

Copy and paste the options from the following gist and save:

https://gist.git.generalassemb.ly/axylos/01807df8810b8e7e0cb8005d3641fd41

Finally, install the required linter packages with the following line in the terminal:
```
npm install -g eslint-config-airbnb eslint eslint-plugin-jsx-a11y eslint-plugin-import eslint-plugin-react
```
### Node.js

Finally, we will set up a runtime for using javascript from the terminal. For SEI, we will use nvm, a version manager for the Node runtime.

You can install nvm with the following terminal command:
Copying + pasting this is strongly recommended.


```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

Ensure that node is installed with the following commands.

```
nvm install 12.2
nvm use 12.2
nvm alias default 12.2
```
