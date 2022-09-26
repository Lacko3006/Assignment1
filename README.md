# Assignment1

First Assignment

# git

There are multiple ways of installing `git`. The [package manager](package.manager.md) way is recommended:

## Installation

The below commands will also install `gitk`, a basic GUI. You can run this from the command line from any repository. `gitk --all` will give you a graph of all git branches on that repository. `gitk &` will run `gitk` 'in the background' (so that the terminal won't wait until it's finished running).

### Windows

From Powershell with Administrator rights, run

```bash
choco install git
```

### macos

```bash
brew install git
brew install git-gui
```

## Setup SSH key

You will also need to set up an SSH key. Running

```bash
ssh-keygen
```

will set one up in the standard location: your public key will be at `~/.ssh/id_rsa.pub`. This is the key that you can safely share with Github and Gitlab. Do not share your private key (`~/.ssh/id_rsa`) with anyone.

## Setup Github

### Share SSH key with Github

- Open your public key using VS Code

```
code ~/.ssh/id_rsa.pub
```

- Copy the contents of the public key to your clipboard
- Open [Github](https://github.com/)
  - Set up an account if you have not done so already
  - Click on your avatar at the top left
  - Navigate to settings
  - Click on SSH and GPG keys on the left
  - Add new SSH key

### Set up SSH when SSH port is blocked

In (physical) environments where SSH is blocked, you will need to edit your config file `code ~/.ssh/config` and add the following block to the bottom. Don't delete other stuff in there.

```config
Host github.com
  Hostname ssh.github.com
  Port 443
```

## Set up a more user-friendly text editor

By default, `git` uses a text editor called `vim`. `vim` is a very powerful text editor (in fact, I use it as my favourite text editor), but it isn't really suitable for the beginner.

To start with, configure `git` to use [VS Code](./vs.code.md) as its text editor:

```
git config --global core.editor "code --wait"
```
