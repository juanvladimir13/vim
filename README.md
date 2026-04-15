# Instalacion y configuracion de vim

## Instalacion de plugin Plug

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

## Archivo de configuracion basica

Eliminar el archivo del directorio del usuario

```bash
cd
rm -v .vimrc
```

Crear el archivo de configuracion

```bash
touch .vimrc
```

Editar el archivo `.vimrc`

```bash
vim .vimrc
```

Agregar el contenido

```vim
syntax on
set number
set ruler
set tabstop=2
set shiftwidth=2
set expandtab
set autoindent
filetype plugin indent on
set noswapfile
set lazyredraw
set showcmd
colorscheme sorbet
set clipboard=unnamedplus
set background=dark

call plug#begin('~/.vim/plugged')
Plug 'wuelnerdotexe/vim-astro'
Plug 'alvan/vim-closetag'
Plug 'pangloss/vim-javascript'
Plug 'mxw/vim-jsx'
call plug#end()

let g:closetag_filenames = '*.html,*.xhtml,*.phtml,*.astro'
let g:closetag_xhtml_filenames = '*.xhtml,*.jsx'
let g:closetag_filetypes = 'html,xhtml,phtml,astro'
let g:jsx_ext_required = 0
au BufRead,BufNewFile *.astro set filetype=jsx
```

Ejecutar el comando `:PlugInstall`