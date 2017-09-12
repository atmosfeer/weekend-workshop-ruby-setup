# Setup instructions

The following instructions will help you to get ready for [Le Wagon](http://www.lewagon.com) fullstack bootcamp:

- Grab a text editor, where you'll spend your day and nights
- Install a package manager
- Pimp your Terminal
- Install Ruby

## Command Line Tools -check

Open the Terminal (click the magnifying glass icon in the top right corner of your screen and type `Terminal`):

![](images/open-terminal.png)

Copy-paste the following command in the terminal and hit Enter.

```bash
xcode-select --install
```

If you have get following message, you can just skip this step and go to next step.

` # command line tools are already installed, use "Software Update" to install updates `

Otherwise, it will open a window asking you if you want to install some software. Accept and wait. If it fails, try again the command line above, sometimes the Apple servers are overloaded.

![](images/xcode-select-install.png)

## Homebrew

On Mac, you need to install [Homebrew](http://brew.sh/) which is a Package Manager.
It will be used as soon as we need to install some software.
To do so, open your Terminal and run:

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

This will ask for your confirmation (hit `Enter`) and your laptop session password.

If you already have Homebrew, it will tell you so, that's fine, go on.

Then install some useful software:

```bash
brew update
```

If you get a `/usr/local must be writable` error, just run this:

```bash
sudo chown -R $USER:admin /usr/local
brew update
```

Error message or not, proceed running the following in the terminal. You can copy and paste all these lines at once.

```bash
function install_or_upgrade { brew ls | grep $1 > /dev/null; if (($? == 0)); then brew upgrade $1; else brew install $1; fi }
install_or_upgrade "git"
install_or_upgrade "wget"
install_or_upgrade "imagemagick"
install_or_upgrade "jq"
install_or_upgrade "openssl"
```

## Sublime Text 3 - Your text editor - check

A text editor is one of the most important tools of a developer. Go to [this page](http://www.sublimetext.com/3) and download **Sublime Text 3** for OS X. Install it (double click the downloaded file and drag & drop the app **into** the `Applications` folder, **don't skip this**). If you had Sublime Text 2 installed before, please uninstall it (by dragging/dropping it to the Trash).

Sublime Text is free without any time limitation but a popup will appear every ten saves to remind you there is a license to buy. You can hit `Esc` when this happens, but feel free to buy Sublime Text if you really like this one (there are alternatives).

Again, make sure that Sublime Text is there, not in the disk image you downloaded. To make sure it's correct, once Sublime Text is installed, unmount the "Sublime Text 3" disk in the left panel of Finder. Finder will complain if something went wrong. Ask a teacher.



## Oh-my-zsh - Fancy your Terminal

We will use the shell named `zsh` instead of `bash`, the default one.

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Be careful, at the end of this script, it will prompt for your laptop password again. You have to write it correctly (you will not see it when you type) and hit `Enter`. You should get something like:

```bash
         __                                     __
  ____  / /_     ____ ___  __  __   ____  _____/ /_
 / __ \/ __ \   / __ `__ \/ / / /  /_  / / ___/ __ \
/ /_/ / / / /  / / / / / / /_/ /    / /_(__  ) / / /
\____/_/ /_/  /_/ /_/ /_/\__, /    /___/____/_/ /_/
                        /____/                       ....is now installed!
```

Now quit the Terminal (`⌘` + `Q`), and restart it.

You should see something like this:

![](images/on-my-zsh.png)

If not, **stop right away** and call a teacher.

On Mac, open `Terminal > Preferences` and set the "Pro" theme as default in `Profiles` (*`Réglages`* in French).

![](images/terminal-pro.png)

Quit and relaunch the Terminal. It should now have a nice black background, more easy on the eyes.

## Download the assignments for today's workshop

```bash
cd ~ && mkdir -p code/lewagon-workshop && cd code/lewagon-workshop
git clone https://github.com/atmosfeer/lewagon-challenges.git
```


## Dotfiles (Standard configuration)

Hackers love to refine and polish their shell and tools. We will start with a great default configuration provided by [Le Wagon](http://github.com/atmosfeer/dotfiles-workshop), stored on GitHub. This configuration gives you a number of handy tools that will make your life as a coder easier. Just follow the instructions to get the setup, but down the line you will be able to customize the options and make them your very own.

Now copy/paste this line in your terminal.

```bash
cd ~/code && git clone https://github.com/atmosfeer/dotfiles-workshop.git
```

Run the `dotfiles` installer.

```bash
cd ~/code/dotfiles-workshop
zsh install.sh
```

### Sublime Text auto-configuration

Open a new terminal and type this:

```bash
stt
```

It will **open Sublime Text in the context of your current folder**. That's how we'll use it.

**Wait 1 minute** for additional packages to be automatically installed (New tabs with text will automatically open, containing documentation for each new package installed).

To check if plugins are installed, open the Command Palette (`⌘` + `⇧` + `P` on OSX, `Ctrl` + `⇧` + `P` on Linux), type in `Packlist` and then `Enter`, you should see a couple of packages installed (like [Emmet](http://emmet.io/)).

If you do not, please install all of them manually. The list is referenced [here](https://github.com/lewagon/dotfiles/blob/master/Package%20Control.sublime-settings).


## Installing Ruby (with [rbenv](https://github.com/sstephenson/rbenv))

First we need to clean up any previous Ruby installation you might have:

```bash
rvm implode && sudo rm -rf ~/.rvm
# If you got "zsh: command not found: rvm", carry on. It means `rvm` is not
# on your computer, that's what we want!

sudo rm -rf $HOME/.rbenv /usr/local/rbenv /opt/rbenv /usr/local/opt/rbenv
```

Now get `rbenv` and `ruby-build` packages from Homebrew, they will be useful.

```bash
brew uninstall --force rbenv ruby-build
unset RBENV_ROOT && exec zsh
brew install rbenv ruby-build && exec zsh
```


Now, you are ready to install the latest ruby version, and set it as the default version.

Run this command, it will **take a while (5-10 minutes)**

```bash
rbenv install 2.3.4
```

Once the ruby installation is done, run this command tell the system
to use the 2.3.4 version by default.

```bash
rbenv global 2.3.4
```

Then **restart** your Terminal (close it and reopen it).

```bash
ruby -v
```

You should see something starting with `ruby 2.3.4p`. If not, ask a teacher.

## Installing some gems

Please run the following line:

```bash
gem install bundler
gem install rspec rubocop pry pry-byebug hub colored octokit
```

**Never** install a gem with `sudo gem install`! Even if you stumble upon a Stackoverflow answer
(or the Terminal) telling you to do so.

## Get started with challenges

Copy these two lines in the terminal to get started with the first challenge:

```bash
  cd ~/code/lewagon-workshop/lewagon-challenges/day-1-ruby-basics/01-My-First-Methods
  stt
```
