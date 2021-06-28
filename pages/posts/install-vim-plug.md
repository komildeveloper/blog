---
title: Install vim-plug for Neovim
date: 2021/6/28
description: Install and Setting up vim-plug for Neovim
tag: neovim
author: komildeveloper
output:
  html_document:
    css: main.css
---

---

# Install vim-plug for Neovim

![vim-plug](https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.png)

---

#### What is [vim-plug](https://github.com/junegunn/vim-plug)? 🤔

- Minimalist plugin manager for Vim/Neovim

#### Pros.

- Easy to set up: Single file. No boilerplate code required.
- Easy to use: Concise, intuitive syntax
- [Super-fast](https://raw.githubusercontent.com/junegunn/i/master/vim-plug/40-in-4.gif) parallel installation/update (with any of +job, +python, +python3, +ruby, or [Neovim](http://neovim.org/))
- Creates shallow clones to minimize disk space usage and download time
- On-demand loading for [faster startup time](https://github.com/junegunn/vim-startuptime-benchmark#result)
- Can review and rollback updates
- Branch/tag/commit support
- Post-update hooks
- Support for externally managed plugins

---

### Install vim-plug for Neovim

```
sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
```

Create **vim-plug** folder and **plugins.vim** file

```
mkdir ~/.config/nvim/vim-plug
touch ~/.config/nvim/vim-plug/plugins.vim
```

Following to **plugins.vim**

```
" Automatic installation
if empty(glob(data_dir . '~/.config/nvim/autoload/plugged'))
  silent execute '!curl -fLo '.data_dir.'/autoload/plug.vim --create-dirs  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
  autocmd VimEnter * PlugInstall --sync | source $MYVIMRC
endif

call plug#begin('~/.config/nvim/autoload/plugged')

" NERDTree file system explorer
Plug 'scrooloose/nerdtree'

" Autopairs
Plug 'jiangmiao/auto-pairs'

" Best syntax and indentation support
Plug 'sheerun/vim-polyglot'

call plug#end()
```

Source in init.vim

```
source $HOME/.config/nvim/vim-plug/plugins.vim
```

Reload nvim and **:PlugInstall** to install plugins

**NOTE**: Another vim-plug [tips](https://github.com/junegunn/vim-plug/wiki/tips)

---

### Commands

- **:PlugInstall** - Install plugins
- **:PlugUpdate** - Update plugins
- **:PlugClean** - Remove unlisted plugins (bang version will clean without prompt)
- **:PlugUpgrade** - Upgrade vim-plug itself
- **:PlugStatus** - Check the status of plugins
- **:PlugDiff** - Examine changes from the previous update and the pending changes
- **:PlugSnapshot** - Generate script for restoring the current snapshot of the plugins
