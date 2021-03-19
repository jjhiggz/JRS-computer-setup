[Watch Some Videos To Walk You Through](https://youtu.be/IgQbOZ1i6yM)

Welcome student! Before we embark, let's turn your computer from a software _consumer_ computer to a software _developer_ computer. Follow each of these instructions _in order_. If something doesn't work, *stop* and try the step again. If it's still not working, ask an instructor for help before you move on!

Note: When you copy/paste a command from this page to your terminal, you *may need to hit enter after everything looks like its run!*. You might still have commands that need to run!

## Setup your terminal

Your terminal (which sometimes you'll hear referred to as a "shell" or "the command line" or a "CLI") will be your primary means of interacting with your computer in the program. This will take the place of navigating through file folders, downloading installers, and running programs by clicking on icons.

## Enable WSL

WSL stands for Windows Subsystem for linux. It is our way of running linux as a virtual machine inside of Windows. The very first thing that we have to do is enable this. In order to do so first we type in. 

To do this we will follow the MANUAL instructions found [Here](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

## Install Ubuntu

- Head to the Microsoft Store
- Install Ubuntu

The default terminal for Ubuntu (GNOME Terminal) will work for this program. Make sure the following option is *checked*:

☰ -> Preferences -> Profiles -> Your Name -> Command -> Run command as a login shell

### Ubuntu

You already have a package manager installed called `apt`! We can install many Ubuntu packages using a command like:

```bash
sudo apt update # This updates the apt software to make sure you get the latest version
sudo apt install <package name one> <package name two> <etc....> # This line of code installs the package
```
***note: please do not run the commands above, that is only on explanation of how sudo apt works, the commands that you will want to run can be found below***

## Install some packages

Now, we'll use our package manager to download some helpful software we'll use in the program.

Run:

```bash
sudo apt update
sudo apt install git zsh gnupg sqlite postgresql postgresql-contrib
```


## Refresh with all the packages you just installed

The following command will make your Ubuntu terminal now have access to all of those things that you just installed.

``` zsh 
    source ~/.zshrc
```

## Install `nvm` and Node

nvm or "Node Version Manager" is a package that we install on our computers that allows us to select between different versions of node. Although you won't really need to understand what is going on here right now. If you are ever curious that is it's purpose.

Because nvm is not a package that `apt` knows about we have to do a bit more complex of an install is necessary. We use a command called `curl` to hit a specific website with specific information. We are going to make a request to "https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh" which is a website that contains all of the information for this package.

To install nvm, run the following command in your terminal:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | zsh
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

Hit enter when you're done!

If this worked, the following command should print `nvm`:

```bash
command -v nvm
```

If that worked, run the following command in your terminal:

```bash
nvm install node
nvm use node
nvm alias default node
```

Hit enter when you're done!

## Install Node Packages

Another package manager? Yep! Gem is for installing packages written in Ruby, and npm is is for installing packages written in JavaScript.

Run the following command in your terminal:

```bash
npm install -g yarn lite-server create-react-app
```

If running:

```bash
which lite-server
```

prints something to the screen, you're probably in good shape!
## Set up zsh

Run:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

When it asks you if you want to switch your shell over to zsh, type "y" and hit enter.

Then *close all open instances of your terminal*. When you reopen your terminal, your command prompt should have a colored `~` on it.

## Set up your text editor

You'll spend most of your time in the program in your text editor. If you already have a preference, keep using it! Switching text editors, even with the same file, is not a big deal. If you're looking for a suggestion, VS Code is a good place to start.

Download and install [VS Code](https://code.visualstudio.com/)

## Set up NVM and Node to work every time

### MacOS and Ubuntu

Run:

```zsh
code ~/.zshrc
```

* Scroll down to the bottom of the file.
* **Paste** *all 3* of these lines at the bottom of the file:

```zsh
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```


## Set up your github account
<!-- ! Insert Video Link Here -->


<!-- Run the following commands:

```bash
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt update
sudo apt install code
``` -->

## Set up git
<!-- ! Insert Video Here -->

Run these commands, **swapping** you `you@example.com` and `Your Name` for **your actual email and name**.

    ```bash
    git config --global user.email "you@example.com"
    git config --global user.name "Your Name"
    ```

Follow [these steps](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh) to connect your computer to Github:

1. Check if you have an SSH key for your computer: [how to check for ssh key](https://docs.github.com/en/github/authenticating-to-github/checking-for-existing-ssh-keys)
2. **If you do not** add one by following *all* of these steps: [How to add an SSH Key](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)


### Congratulations

Yay! You're done!! 🙌 💃
Take a break, get a drink of water, and happy coding!!

<!-- ## Install `rvm` and Ruby

We'll use a tool called [`rvm`](https://rvm.io/) to have greater control over which version of ruby we're using.

### MacOs and Ubuntu

Run this command:

```bash
gpgconf --kill all
gpg --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash -s stable --auto-dotfiles
export PATH="$PATH:$HOME/.rvm/bin"
[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
``` -->