# About my dotfiles

My .dotfiles **ViM, DWM, zsh, st** and I use **ArchLinux** as my linux distribution
Mainly inspired by [ornicar](https://github.com/ornicar/dotfiles). For all my programs and shell I use [solarized
colors](http://ethanschoonover.com/solarized) and mainly **Inconsolata** font.

## Requirements

- You will need latest **ViM** with a support of **ruby** interpreter
- **git**
- **zsh**
- **wget**
- **256** color terminal client

To use tmuxinator:

    gem install tmuxinator

To install dmenu:

    git clone https://github.com/l3pp4rd/dmenu.git ~/.dmenu && cd ~/.dmenu

You most probably need to change the **X11** lib header file location if you are not using arch linux:

    vim config.mk
    make
    sudo make install # will install it in /usr/local/bin

Dmenu shortcut to list all path executables is available at **~/.dotfiles/scripts/path_dmenu**
It will cache all recently used applications, that way it will show up first in search results.

## Screen

![Screenshot](https://raw.github.com/l3pp4rd/dotfiles/master/screen.png)

## Installation

Clone the repository:

    clone git://github.com/l3pp4rd/dotfiles.git ~/.dotfiles

### ViM

If you do not have latest **ViM** with ruby support and all patches. You can use a shell script to install it.
**Note:** you will need GCC and all that build stuff to compile it.

    ./.dotfiles/compile/vim/build.sh

### Terminal client

If you want nice colors with **vim** you must have a terminal client, which supports **256** colors. You may try:

- **st** does not require weird patches, it is small and works perfectly well. You can just grab my version of
[st](https://github.com/l3pp4rd/st) and compile it. If you need transparency, use **xcompmgr** and **transset-df**.
- **rxvt-unicode** you would need to compile it yourself with an option for 256 colors, may add some xft support as well.
it takes time to configure urxvt, I would prefer **st**.

### Tmux

You should consider reading about **tmux** and install it. **Tmuxinator** is also a handy tool to be used with tmux.
If you use **st** tmux will provide tabs and history scrolling support. Mouse scroll in urxvt sucks. Tmux will provide
history scrolling and tabs.

### Zsh

If you do not use **zsh** ignore the .zshrc installation, otherwise you could try to use it instead
of bash - install **zsh** first and use it as your default shell by running:

    chsh -s $(which zsh)

### Install dotfiles

Execute the setup script, follow the configuration options, you may not need to replace all configs:

    ./.dotfiles/setup.sh

Load vim bundles:

    vim +BundleInstall +qall

**NOTE:** most configurations use **Inconsolata** fonts, you should install or change it.

### Command-T

After that, for [command-t](http://github.com/wincent/Command-T) bundle you will need
to compile a **C** extension.

    cd ~/.vim/bundle/Command-T/ruby/command-t
    ruby extconf.rb
    make

## Window Manager

If you are tired of bloated desktops like gnome, kde.. whatever, would recommend to try [dwm](http://dwm.suckless.org/)

**NOTE:** look how to manage it as an xsession in order to provide a possibility to be used inline
with a login manager like **slim**. You can find an example in my dotfiles.

## changelog

- **2013-12-20** - switched from pathogen to vundle
- **2013-12-20** - switched powerline to airline, does not require big python setup

