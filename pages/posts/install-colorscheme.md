---
title: Neovim uchun Colorscheme o'rnatamiz
date: 2021/6/29
description: Neovim uchun Colorscheme o'rnatamiz
tag: neovim
author: komildeveloper
output:
  html_document:
    css: main.css
---

---

![neovim](https://www.chrisatmachine.com/static/ff1c356d6a7f46604822f50919abcf83/5134e/neovim.png)

---

# Neovim uchun Colorscheme o'rnatamiz

- Neovim uchun o'rnatadigan Colorscheme [OneDark](https://github.com/joshdick/onedark.vim), [GruvboxMaterial](https://github.com/sainnhe/gruvbox-material), [Material](https://github.com/kaicataldo/material.vim) yoki shunga o'xshash colorscheme bo'lishi mumkin
- Men OneDark Colorschemeni Neovimga o'rnataman(_albatta vim-plug orqali_) va uni configuratsiya qilaman

---

# Step by step

### Step 1

**plugins.vim** fayliga quyidagi plugin nomini qo'shib qo'ying

```
Plug 'joshdick/onedark.vim'
```

Reload nvim & **:PlugInstall**

### Step 2

**theme** nomli folder va uni ichida **onedark.vim** nomli fayl yaratamiz

```
mkdir ~/.config/nvim/themes
touch ~/.config/nvim/themes/onedark.vim
```

### Step 3

Quyidagilarni **onedark.vim** fayliga qo'shib qo'yishimiz kerak

```
" onedark.vim override: Don't set a background color when running in a terminal;
if (has("autocmd") && !has("gui_running"))
  augroup colorset
    autocmd!
    let s:white = { "gui": "#ABB2BF", "cterm": "145", "cterm16" : "7" }
    autocmd ColorScheme * call onedark#set_highlight("Normal", { "fg": s:white }) " `bg` will not be styled since there is no `bg` setting
  augroup END
endif

hi Comment cterm=italic
let g:onedark_hide_endofbuffer=1
let g:onedark_terminal_italics=1
let g:onedark_termcolors=256

colorscheme onedark
syntax on

" checks if your terminal has 24-bit color support
if (has("termguicolors"))
    set termguicolors
    hi LineNr ctermbg=NONE guibg=NONE
endif
```

Va quyidagi manbani **init.vim** fayliga qo'shib qo'yamiz

```
source $HOME/.config/nvim/themes/onedark.vim
```

---

OneDark yoki boshqa colorschemes haqida yanada ko'proq ma'lumot

- [OneDark](https://github.com/joshdick/onedark.vim) Github Repo
- [Awesome Vim Colorschemes](https://github.com/rafi/awesome-vim-colorschemes) Awesome Vim Colorschemes
