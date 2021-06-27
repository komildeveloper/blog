---
title: Basic Neovim config w/ options and keymappings
date: 2021/6/27
description: Neovim basic options and keymappings
tag: neovim
author: komildeveloper
---

# Options and Keymappings

---

### Neovim config folder

Where is my Neovim config? 🤔

**Create nvim config folder**

```
mkdir ~/.config/nvim
```

**init.vim file for nvim config**

```
touch ~/.config/nvim/init.vim
```

### Basic options

Where is my Neovim config options file and folder? 🤔

**Create general folder and setting.vim file for basic options**

```
mkdir ~/.config/nvim/general
touch ~/.config/nvim/general/settings.vim
```

Following to settings.vim

```
set iskeyword+=-                        " treat dash separated words as a word text object"
set formatoptions-=cro                  " Stop newline continution of comments

syntax enable                           " Enables syntax highlighing
set hidden                              " Required to keep multiple buffers open multiple buffers
set nowrap                              " Display long lines as just one line
set whichwrap+=<,>,[,],h,l
set encoding=utf-8                      " The encoding displayed
set pumheight=10                        " Makes popup menu smaller
set fileencoding=utf-8                   " The encoding written to file
set ruler                               " Show the cursor position all the time
set cmdheight=2                         " More space for displaying messages
set mouse=a                             " Enable your mouse
set splitbelow                          " Horizontal splits will automatically be below
set splitright                          " Vertical splits will automatically be to the right
set t_Co=256                            " Support 256 colors
set conceallevel=0                      " So that I can see `` in markdown files
set tabstop=2                           " Insert 2 spaces for a tab
set shiftwidth=2                        " Change the number of space characters inserted for indentation
set smarttab                            " Makes tabbing smarter will realize you have 2 vs 4
set expandtab                           " Converts tabs to spaces
set smartindent                         " Makes indenting smart
set autoindent                          " Good auto indent
set laststatus=2                        " Always display the status line
set number                              " Line numbers
set cursorline                          " Enable highlighting of the current line
set background=dark                     " tell vim what the background color looks like
set showtabline=2                       " Always show tabs
set noshowmode                          " We don't need to see things like -- INSERT -- anymore
set nobackup                            " This is recommended by coc
set nowritebackup                       " This is recommended by coc
set shortmess+=c                        " Don't pass messages to |ins-completion-menu|.
set signcolumn=yes                      " Always show the signcolumn, otherwise it would shift the text each time
set updatetime=300                      " Faster completion
set timeoutlen=100                      " By default timeoutlen is 1000 ms
set clipboard=unnamedplus               " Copy paste between vim and everything else
set incsearch
```

Source in init.vim

```
source $HOME/.config/nvim/general/settings.vim
```

### Basic keymappings

Create keys folder and mappings.vim file for keymappings

```
mkdir ~/.config/nvim/keys
touch ~/.config/nvim/keys/mappings.vim
```

Following to mappings.vim

```
" Use alt + hjkl to resize windows
nnoremap <M-j>    :resize -2<CR>
nnoremap <M-k>    :resize +2<CR>
nnoremap <M-h>    :vertical resize -2<CR>
nnoremap <M-l>    :vertical resize +2<CR>

" I hate escape more than anything else
inoremap jk <Esc>
inoremap kj <Esc>

" TAB in general mode will move to text buffer
nnoremap <TAB> :bnext<CR>
" SHIFT-TAB will go back
nnoremap <S-TAB> :bprevious<CR>

" Better tabbing
vnoremap < <gv
vnoremap > >gv

" Better window navigation
nnoremap <C-h> <C-w>h
nnoremap <C-j> <C-w>j
nnoremap <C-k> <C-w>k
nnoremap <C-l> <C-w>l
```

Source in init.vim

```
source $HOME/.config/nvim/keys/mappings.vim
```

### Run all healthchecks

Open nvim and enter the following command

```
:checkhealth
```

What is **checkhealt** in Neovim 🤔 [here](http://vimcasts.org/episodes/neovim-checkhealth/#:~:text=The%20%3Acheckhealth%20command%20runs%20a,to%20go%20to%20learn%20more.)

Install **pynvim** for python support

```
pip install pynvim
```

Install **neovim** for nodejs support

```
npm i -g neovim
```
