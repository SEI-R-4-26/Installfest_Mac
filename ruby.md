# Ruby

## Installing RBENV for ruby version control

1. First install `rbenv`, a Ruby version manager with:

```
brew install rbenv ruby-build
```

2. Now we need to setup rbenv to load into terminal everytime we open terminal. Run the command:
```shell
code ~/.zshrc
```

at the very bottom of this file, add the following lines:

```
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

3. Close your terminal window and open a new one.

4. we can test to see if we're using rbenv by typing the command in terminal:

```shell
which ruby
```

whit should return a line that looks something like this:

```shell

/Users/<YourUsernameHere>/.rbenv/shims/ruby

```

## Installing Ruby

1. Now install the current version of Ruby with

```
rbenv install 2.7.1
```

2. We will also need to set this new ruby version as our default version. We can do this with: 

```shell
rbenv global 2.7.1
```

we can check this with:
```shell
rbenv versions
```

we should see an asterisk next to `2.7.1`
