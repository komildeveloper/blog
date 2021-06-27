---
title: Install Neovim Nightly
date: 2021/6/26
description: Install Neovim Nightly 0.5.0 version | Arch Linux, Ubuntu&Debian and more
tag: neovim
author: komildeveloper
---

# Install Neovim Nightly 0.5.0 version

## Install the Latest version of Neovim

### Build prerequisites

Platform-specific requirements are listed below

**Ubuntu / Debian**

```
sudo apt-get install ninja-build gettext libtool libtool-bin autoconf automake cmake g++ pkg-config unzip
```

**Arch Linux**

```
sudo pacman -S base-devel cmake unzip ninja tree-sitter
```

**Other platforms** [here](https://github.com/neovim/neovim/wiki/Building-Neovim#build-prerequisites)

Download from [Git](https://github.com/neovim/neovim) repo and compile

```
cd $(mktemp -d)
git clone https://github.com/neovim/neovim --depth 1
cd neovim
sudo make CMAKE_BUILD_TYPE=Release install
cd ..
sudo rm -r neovim
```

or if you are on Arch you can get it from the AUR

```
yay -S neovim-git
```

## Uninstall Neovim

```
sudo rm -rf /usr/local/bin/nvim
```

## Uninstall config, plugins and caches

Delete the config folder

```
rm -rf ~/.config/nvim
```

Delete the installed plugins

```
rm -rf ~/.local/share/nvim
```

Delete the logs

```
rm -rf ~/.cache/nvim
```
