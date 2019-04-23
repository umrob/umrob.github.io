---
date: 2019-04-20
title: Linux environment setup
categories:
  - linux
description: "How to configure your Linux environment for the robotics classes"
type: Document
set: getting-started
set_order: 1
highlighter: rouge
---

## Operating system

We will use Linux as our primary operating system because it is free and widely used in robotics, for both classical and embedded computers.

As for the [distribution](https://en.wikipedia.org/wiki/Linux_distribution), we will focus on [Ubuntu](https://www.ubuntu.com/) (or one of its derivatives) because it is the only one where [ROS](http://www.ros.org/) is officially supported.

If you're installing Linux directly on a descent computer, you can go with Ubuntu.
But if you plan to use an older/low-end computer or a virtual machine, it is better to choose a more lightweight derivative such as [Xubuntu](https://xubuntu.org/), [Lubuntu](https://lubuntu.net/) or [Linux Lite](https://www.linuxliteos.com/) (installed in the provided VM (coming soon)).

The latest version of Ubuntu supporting ROS is the 18.04 LTS, so please choose this one.

Installation instructions can be found [here](https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#0), or [here](https://www.tecmint.com/install-ubuntu-alongside-with-windows/) if a dual boot with Windows is required.

## C/C++ Tools

We first have to install all the tools required for C and C++ development. This includes:
 * Compilers: [GCC/G++](https://www.gnu.org/software/gcc/)
 * Debugger: [GDB](https://www.gnu.org/software/gdb/)
 * Build tool: [CMake](https://cmake.org/)
 * Versioning system: [Git](https://git-scm.com/)
 * Documentation generation: [Doxygen](http://www.doxygen.nl/)

Let's start by updating the list of available packages and upgrade the ones installed to the latest version. Open your terminal and enter (the `$` sign denotes an instruction to be typed in the terminal and must not be included):

~~~bash
$ sudo apt update
$ sudo apt upgrade
~~~

Now that the system is up to date, we can install everything:

~~~ bash
$ sudo apt install build-essential gdb cmake cmake-curses-gui git git-lfs doxygen
~~~

## Code editor

There are plenty of code editors available, most of them being free.
It is up to you to choose one that you like but, to help you choose, here are a few things to keep in mind:
 * C and C++ support: our main programming languages
 * CMake support: our main build tool
 * Cross-platform: you may have to use a different OS at some point so it is better if your editor works everywhere

If you prefer to have one editor for everything, [Atom](https://atom.io/) and [Visual Studio Code](https://code.visualstudio.com/) are both very good candidates. [Vim](https://www.vim.org/)/[Neovim](https://neovim.io/) are great if you never want to leave your terminal, but have a steeper learning curve. These editors are basically just advanced text editors by default and thus require you to install plugins to support new languages, auto-completions, etc. This process is very easy but can take some time to find everything you need.

On the other hand, if you prefer full-featured IDEs that pack everything needed for a specific language, [Qt Creator](https://www.qt.io/download), [Eclipse](https://www.eclipse.org/) or [Clode::Blocks](http://www.codeblocks.org/) can do a good job.

If you have no idea on which one to choose, you can consult [this page](https://www.tecmint.com/best-linux-ide-editors-source-code-editors/) to have an overview of the most commonly used editors for C/C++. But beware, not all of them fit the three points listed above.

## (Optional) A better terminal emulator

You may want to install [Terminator](https://launchpad.net/terminator) if you wan to enjoy full customization of your terminal and splitting windows in multiple sub-terminals. If you are interested, just run:

~~~ bash
$ sudo apt install terminator
~~~

And if you want to set it as your default terminal, search for **Preferred Applications** in the applications menu, open it, and change the terminal field to **Terminator** (can be in a **Utility** tab). If you use Xfce (like with **Xubuntu** or **Linux Lite**) and want the **ctrl-alt-t** shortcut to open **Terminator**, follow [these instructions](https://askubuntu.com/questions/499563/cant-set-altctrlt-to-launch-terminal-in-xfce4).

## (Optional) A better shell

Since you will spend quite some time in a terminal using the shell, it can be a good idea to install something better than the default one (**Bash**) and customize it to your liking.

We recommend to install [ZSH](https://sourceforge.net/projects/zsh/) + [Oh My ZSH](https://ohmyz.sh/) to get the best shell experience possible:

~~~ bash
$ sudo apt install zsh
$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
~~~

The second instruction will install **Oh My ZSH** and ask for your password in order to set **ZSH** to be your default terminal.

Now you can browse the [available themes](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes) and pick the one you like ([Agnoster](https://github.com/agnoster/agnoster-zsh-theme) is a great starter). You will most likely have to install patched fonts to display the theme correctly so please read your theme installation instructions carefully.

### Important notice
if you switch to **ZSH**, your configuration script is now `~/.zshrc` instead of `~/.bashrc`.
So if your read a tutorial telling you to put something in your `~/.bashrc` file, do it in your `~/.zshrc` instead.
