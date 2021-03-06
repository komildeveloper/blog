---
title: Neovim-ni Coc bilan VSCode kabi sozlaymiz
date: 2021/6/30
description: Neovim-ni Coc bilan VSCode kabi sozlaymiz
tag: neovim
author: komildeveloper
---

# Neovim-ni Coc bilan VSCode kabi sozlaymiz 

---

![neovim](https://www.chrisatmachine.com/static/ff1c356d6a7f46604822f50919abcf83/5134e/neovim.png)

---

# Step by step

**ESLATMA:** coc.nvim TypeScript-da yozilgan va Node.js bilan ishlaydi

- Shunday ekan bizda **Node.js** bo'lishi kerak

### Requirements
- nodejs 12.12
- neovim 0.3.2
- vim 8.0.1453

### Install Nodejs 

Nodejs-ni o'rnatish uchun [link](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)

---

### Step 1
**coc.nvim** pluginini o'rnatish uchun quyidagi pluginni **plugins.vim** qo'shib qo'yamiz 

```
" LSP
" Use release branch (recommend)
Plug 'neoclide/coc.nvim', {'branch': 'release'}

" Or build from source code by using yarn: https://yarnpkg.com
Plug 'neoclide/coc.nvim', {'branch': 'master', 'do': 'yarn install --frozen-lockfile'}
```

Yarn orqali o'rnatish uchun
```
Arch Linux
npm i -g yarn

Ubuntu
sudo npm i -g yarn
```

Reload nvim & **:PlugInstall**

### Step 2
coc.nvim uchun config folder va fayl yaratamiz
```
mkdir ~/.config/nvim/plug-config
touch ~/.config/nvim/plug-config/coc.vim
```

coc.nvim config [link](https://github.com/neoclide/coc.nvim) - **coc.vim** fayliga qo'shib qo'yamiz

Va quyidagi manbani **init.vim** fayliga qo'shib qo'yamiz

```
source $HOME/.config/nvim/plug-config/coc.vim
```

### Step 3

Coc.nvim bilan Neovim-ga extension o'rnatamiz
```
:CocInstall coc-json coc-tsserver coc-vimlsp
```
Coc extensions [link](https://github.com/neoclide/coc.nvim/wiki/Using-coc-extensions)

LSP uchun config va boshqalar
Coc LSP [link](https://github.com/neoclide/coc.nvim/wiki/Language-servers)

#### Coc Commands

O'rnatilgan extension commandalari
**:CocList commands**

Extension-ni o'rnatish
**:CocInstall coc-css**

Extension-ni o'chirish
**:CocUninstall coc-css**

O'rnatilgan extension-lar ro'yaxatini olish
**:CocList extensions**

### Step 4
**:CocConfig** sizga coc-settings.json faylini yaratib beradi
Quyidagilarni coc-settings.json fayliga qo'shib qo'yamiz
```
{
  "coc.preferences.formatOnSaveFiletypes": ["css", "markdown", "javascript", "graphql", "html", "yaml",  "json", "python"]
}
```

---

Coc-Nvim Github [Repo](https://github.com/neoclide/coc.nvim)
