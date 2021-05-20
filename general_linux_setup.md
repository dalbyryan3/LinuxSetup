# Ryan Dalby General Linux Setup

## General programs to Install
* Vim- For general text editing, works well with command line (install vim or related vim package that may contain gvim)
```bash
sudo apt install vim
```
* VSCode- For more in-depth text editing and/or general coding, can install plugins easily using VSCode gui
```bash
sudo snap install --classic code
```
* Parcellite- Clipboard manager, allows for easier copy/paste between different applications (especially if using Ubuntu graphically)
```bash
sudo apt install parcellite
```

## General Themes and Keybindings
### Theme- One Dark
* One Dark Pro plugin for VS Code
* Onedark.vim for Vim https://github.com/joshdick/onedark.vim (Install like vim plugin)
### Keybindings- Vim 
* VSCodeVim plugin for VS Code
* Standard Vim keybindings in Vim

## VIM Setup
### Install Vundle for plugins
```bash
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
### Create ~/.vimrc as follows:
```vim
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" Plugins to install
" Supertab for code-completion
Plugin 'https://github.com/ervandew/supertab.git'
" Commentary to easily comment
Plugin 'https://tpope.io/vim/commentary.git'
" Sleuth for tabs/spaces detection
Plugin 'https://tpope.io/vim/sleuth.git'
" One Dark theme
Plugin 'https://github.com/joshdick/onedark.vim.git'
" Fugitive for git integration
Plugin 'https://tpope.io/vim/fugitive.git'

call vundle#end()
" Turn on file type detection, plugin, and indent
filetype plugin indent on


" General Vim setup:
" Syntax highlighting
syntax on
" Set line numbers
set number
" Set tabs as spaces initially, sleuth will adjust based on file
set ts=4 sw=4
" Allow for switching between edited buffers
set hidden
" Turn off flashing/visual bell
set belloff=all

" Set switching time between modes and cursor modes, may have to do slightly
" different based on os and terminal type
set timeoutlen=1000 ttimeoutlen=50
let &t_ti.="\e[1 q"
let &t_SI.="\e[5 q"
let &t_EI.="\e[1 q"
let &t_te.="\e[0 q"
```

### Open Vim and install plugins
```bash
vim
:PlugInstall
```

