set nocompatible    "http://stackoverflow.com/questions/5845557/in-a-vimrc-is-set-nocompatible-completely-useless

" https://github.com/gmarik/Vundle.vim
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/plugin/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'gmarik/Vundle.vim'

Plugin 'kien/ctrlp.vim'
" Plugin 'tpope/vim-fugitive'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
" plugin from http://vim-scripts.org/vim/scripts.html
""Plugin 'L9'
" Git plugin not hosted on GitHub
" Plugin 'git://git.wincent.com/command-t.git'

" git repos on your local machine (i.e. when working on your own plugin)
""Plugin 'file:///home/gmarik/path/to/plugin'
" The sparkup vim script is in a subdirectory of this repo called vim.
" Pass the path to set the runtimepath properly.
""Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
" Avoid a name conflict with L9
""Plugin 'user/L9', {'name': 'newL9'}

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required

highlight DiffAdd ctermbg=LightGray ctermfg=black
highlight DiffChange ctermbg=LightCyan ctermfg=black
highlight DiffDelete ctermbg=LightBlue ctermfg=White
highlight DiffText ctermbg=LightGray ctermfg=black
highlight MyColLimit ctermbg=Yellow

" http://dailyvim.blogspot.com/2008/11/using-mapleader.html
let mapleader = ","
map <leader>n :E<cr>

" http://vim.wikia.com/wiki/Select_tab_page_with_a_key
nmap <Leader>1 : <ESC>1gt
nmap <Leader>2 : <ESC>2gt
nmap <Leader>3 : <ESC>3gt
nmap <Leader>4 : <ESC>4gt
nmap <Leader>5 : <ESC>5gt
nmap <Leader>6 : <ESC>6gt
nmap <Leader>7 : <ESC>7gt
nmap <Leader>8 : <ESC>8gt
nmap <Leader>9 : <ESC>9gt

"ctrlp plugin
set runtimepath^=~/.vim/plugin/ctrlp.vim
let g:ctrlp_map = '<c-p>'
let g:ctrlp_cmd = 'CtrlP'
let g:ctrlp_lazy_update = 0
let g:ctrlp_working_path_mode = 'ra'
let g:ctrlp_use_caching = 5000
let g:ctrlp_cache_dir = $HOME . '/.cache/ctrlp'
let g:ctrlp_clear_cache_on_exit = 0
let g:ctrlp_max_files = 50000
let g:ctrlp_max_height = 20

" https://medium.com/@mozhuuuuu/vimmers-you-dont-need-nerdtree-18f627b561c3
let g:netrw_liststyle=3

" Insert newline without entering insert mode
nmap <S-CR> O<Esc>
nmap <CR> o<Esc>

" Easier way to save and quit. don't have to hold Shift everytime
nnoremap ; :

" But ; is useful to quick navigate to a specific position after using f,F,t,T
nnoremap ' ;

" Paste yanked test multiple times
" Either use http://stackoverflow.com/questions/290465/vim-how-to-paste-over-without-overwriting-register 
" or remap p as follows.
" 'p' to paste, 'gv' to re-select the newly pasted content. 'y' to copy it again
xnoremap p pgvy
xnoremap P Pgvy

"These are to cancel the default behavior of d, D, c, C
"  to put the text they delete in the default register.
"  Note that this means e.g. "ad won't copy the text into
"  register a anymore.  You have to explicitly yank it.
" nnoremap d "_d
" vnoremap d "_d
nnoremap D "_D
vnoremap D "_D
nnoremap c "_c
vnoremap c "_c
nnoremap C "_C
vnoremap C "_C
nnoremap x "_x
vnoremap x "_x

" Disabling arrow keys
nnoremap <up> <nop>
nnoremap <down> <nop>
nnoremap <left> <nop>
nnoremap <right> <nop>
inoremap <up> <nop>
inoremap <down> <nop>
inoremap <left> <nop>
inoremap <right> <nop>
nnoremap j gj
nnoremap k gk

map bo :browse old<cr>

" Easy window navigation when using split windows
map <C-h> <C-w>h
map <C-j> <C-w>j
map <C-k> <C-w>k
map <C-l> <C-w>l

" clearing highlighted searches
nmap <silent> ,/ :nohlsearch<CR>

set background=dark
set ignorecase            "Ignore case when searching
set smartcase       " When 'ignorecase' and 'smartcase' are both on, if a pattern contains an uppercase letter, it is case sensitive, otherwise, it is not
set hlsearch                "Also switch on highlighting the last used search pattern.
set incsearch              "Make search act like search in modern browsers
set nu
set bs=2                     "allow backspacing over everything in insert mode
set ruler                      "Show the line and column number of the cursor position
"set foldminlines=150
set history=100           "keep 50 lines of command line history
set viminfo='20,\"50     "read/write a .viminfo file, don't store more than 50 lines of registers
set autoindent             "always set autoindenting on
set cindent                 "Automatically inserts indentation but stricter and more customisable
set backup
set backupdir=~/.vim/backup
set directory=~/.vim/tmp
set showcmd	             "little useful bits about actual state of keyboard input in normal are displayed.
set showmode            "display the current editing mode in the lower right corner of the editing screen.
set splitright  " cscope results window on right on a vertical split

syntax on
match MyColLimit /\%101v/

if has("autocmd")
	augroup cprog
		" Remove all cprog autocommands
		au!
		
		" When starting to edit a file:
		"   For C and C++ files set formatting of comments and set C-indenting on.
		autocmd FileType *      set formatoptions=tcql nocindent comments&
		autocmd FileType cc,h,c,cpp,wiki,x  set formatoptions=croql cindent comments=sr:/*,mb:*,el:*/,://
	augroup END

	" When editing a file, always jump to the last cursor position
	autocmd BufReadPost *
	\ if line("'\"") > 0 && line ("'\"") <= line("$") |
	\   exe "normal g'\"" |
	\ endif
endif

" http://stackoverflow.com/questions/234564/tab-key-4-spaces-and-auto-indent-after-curly-braces-in-vim
filetype plugin indent on
set tabstop=4
set shiftwidth=4
set expandtab

"func SetTabSettings()
"    if g:tab_mode == 4
"        set tabstop=4
"        set shiftwidth=4
"        set expandtab
"        match MyColLimit /\%101v/
"    else
"        set tabstop=8
"        set shiftwidth=8
"        set noexpandtab
"        match MyColLimit /\%81v/
"    endif
"endfunc
"
"" Toggle tab mode between 4 and 8 spaces. Expand tab only in 4 tab mode
"func ToggleTabMode()
"    if g:tab_mode == 8
"        let g:tab_mode = 4
"        echo "4 space tabs"
"    else
"        let g:tab_mode = 8
"        echo "8 space tabs"
"    endif
"    call SetTabSettings()
"endfunc
"
"func SetDiffMode()
"    if g:diff_mode == 1
"        set diffopt+=iwhite
"        set diffopt+=icase
"        syntax off
"    else
"        set diffopt-=iwhite
"        set diffopt-=icase
"        syntax on
"    endif
"endfunc
"let g:diff_mode = 2 
"call SetDiffMode()
"
"" Toggle between diff modes. Simple diff ignores case and whitespace changes
"func ToggleDiffMode()
"    if g:diff_mode == 1
"        let g:diff_mode = 2
"        echo "Normal diff"
"    else
"        let g:diff_mode = 1
"        echo "Ignoring case and whitespace changes"
"    endif
"    call SetDiffMode()
"endfunc
"
"
"function IsUnderPerforce()
"    if exists("$MYTREE")
"        if expand("%:p") =~ ("^" . $MYTREE)
"            " let b:p4path = substitute(expand("%:p"), $PDS_TOPDIR, "//depot", "")
"            let b:p4path = expand("%:p")
"        endif
"    endif
"endfunction
"
"" Confirm with the user, then checkout a file from perforce.
"function P4Checkout()
"   echo "Hit me! $p4path" 
"   if exists("b:p4path")
"        if (confirm("Checkout" . b:p4path . " from Perforce?", "&Yes\n&No", 1) == 1)
"            call system("p4 edit " . b:p4path . " >> $HOME/tmp")
"            echo "Checked out"
"            if v:shell_error == 0
"                set noreadonly
"            endif
"        endif
"    endif
"endfunction
"
"if !exists("au_p4_cmd")
"    let au_p4_cmd=1
"
"    au BufEnter * call IsUnderPerforce()
"    au FileChangedRO * call P4Checkout()
"endif
"
"" Mapping keys
"nmap <C-E>t :call ToggleTabMode()<CR>
"nmap <C-E>d :call ToggleDiffMode()<CR>
"nmap <C-E>l :set list <CR>
"
"" Disabled stuff
"" In text files, always limit the width of text to 90 characters
"" autocmd BufRead *.txt set tw=90
"let g:tab_mode = 4
"call SetTabSettings()
