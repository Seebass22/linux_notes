# GENERAL
# removes trailing whitespaces
:%s/\s\+$//e

# convert tab indents to spaces
:set expandtab // or set et
:retab!

# convert space indents to tabs
:set noexpandtab // or set noet
:retab!

# " to select register
"0p     // paste from yank register
"+y     // yank to clipboard

# yank line 12 to pointer
:12t.
# yank current line -12 to pointer
:-12t.

# select text in brackets
vi}

# search for word under cursor
*

# go to local declaration of variable under cursor (C)
gd

# paste in insert mode
<C-r> {reg}      // <c-r>0 for yank register

# clear search highlighting until next search
:noh

# completetion (insert mode)
<C-x><C-p> previous (context aware)
<C-x><C-l> line (context aware)

# forward, back
<C-n>
<C-p>
# accept suggestion
<C-y>
# cancel
<C-e>

# remove indentation
:%left

# relace word with yanked word
viwp

# go to next bracket on line (or matching bracket)
%

# go to next " on line and change inside quotes
ci"

# split long lines into multiple lines
gq

# go to last edited line
g;

# jump to middle of buffer
50%

# VISUAL MODE
# start visual mode with the last selection
gv
# start visual mode on next search result
gn
# -> change next search result (repeatable with .)
cgn
# move to other end of visual selection
o

# change 0 to 1 (while visually selected)
#        0    2
#        0    3
g_CTRL-a


# invert case of letter
~

# increment or decrement a number
<C-a>  or <C-x>

# insert mode math (one number must be float for float arithmetic)
<C-r> =

# search for blank line
/^$

# WINDOWS
# split into 2 windows
:split
<C-w> s
# vertically
<C-w> <C-v>
:vsplit
# split and edit empty file
<C-w> N
# split and view tag
<C-w> ]
# resize windows
# vertical size
:resize +5
# horizontal size
:vertical reize +5
# close all windows but current one
<C-w>o
    or
:only
# increase current window by one line
<C-w>+
# move current window to far left (do this for debugging!)
<C-w> H


# jump to definition or to help file
<C-]>

# move back and forward in jumplist
<C-o>
<C-i>

# special characters :h digraphs
<C-k> :o   //ö
<C-k> :a   //ä
<C-k> ss   //ß
<C-k> `a   //à

# center screen around cursor
zz
# keep cursor position, top of screen
zt
# keep cursor position, bottom of screen
zb

# move to next paragraph/code block (separated by empty line)
}

# clone paragraph (copy block of code [sep. by empty line] and paste below)
yap}p

# save as (save as <FILE> and switch current buffer to <FILE>)
:sav[eas]

# edit file remotely
vim scp://remoteuser@server.tld//absolute/path/to/document
:e scp://remoteuser@server.tld//absolute/path/to/document

# VIM FUGITIVE
# open git status window
:Git
# open inline diff for file under curor
=
# stage file under cursor
s
# unstage file under cursor
u

# vimdiff with index version
:Gdiff

# show previous versions (git repo)
:0Glog
# go back one commit
:cn[ext]
# forward (newer)
:cp[revious]
# earliest commit
:clast
# newest commmit
:cfirst
# return to current version
:Gedit

# vim diffs
# take change to current buffer
:diffget
    or
do
# put change in other buffer
:diffput
    or
dp
# update diff colours
:diffupdate
# to stage index (on index buffer)
:w


# search files and populate quickfix list with results
:vim[grep] /pattern/ FILES...
# example
:vim /print\S/ *.cpp *.h
# use external grep
:grep -E -w '\<int\S' *.cpp

# open quickfix window if available
:cwin
# go to error [nr] or first error if [nr] is omitted
:cc [nr]
# show all errors in quickfix list
:clist
# show all quickfix lists
:chi[story]
# prev, next list
:colder
:cnewer
# do not overwrite newer list
:cnewer 99

# ex command on every buffer
:bufdo
# "" every file in arglist
:argdo
# populate arglist
:args *.cpp

# open file under cursor
gf

# show manpage for word under cursor
K

# send lines to external program and echo result
:[range]w !wc
# filter lines through external program (replace them with result)
:[range] !sort

# show word count for paragraph
vip:w !wc -w

# rounding
round()  // to nearest integer
ceil()   // up
float()  // down

# change dir, pwd
:cd
:pwd

# show tabs
set list

# spellcheck
:set spell
:set spelllang=de
# next mistake
]s
# fix last mistake (insert mode)
<C-x>s

# FOLDS
# create folds by syntax
:set foldmethod=syntax

zM  // max fold level
zR  // min fold level (open all)
zc  // close fold
zo  // open fold
zC  // close all folds under cursor
zO  // open all folds under cursor
zn  // disable folding
zx  // update folds

# BUFFERS
# switch to buffer 5
5<C-^>

# interactive bufferlist
:b <tab>


# TAGS
# make tags for vim (all c files, tag file in .git folder)
ctags -f .git/tags *.c

# open preview window and display function "write_char"
:ptag write_char
    or
<C-w>}
# close preview window
:pclose


# move to start of current block enclosed in {}
[{

# REGEX
\zs     mark start of match
\ze     mark end of match
#example: vimcasts.com -> vimcasts.org
:s/vimcasts.\zscom/org

# (caps invert)
\d      digits
\s      whilespace
\{n}    n matches


# go to specific byte (byte 25)
25go

# insert last inserted text (insert mode)
<C-a>

# insert character above cursor (insert mode)
<C-y>

# (insert mode)
# enter character literally
# or
# enter character with ascii decimal value
<C-v>

# enable virtual editing for easy editing of tables
# (place cursor where there is no actual character)
:set virtualedit=all
# go back to non-virtual editing
:set virtualedit=

# disable magic (regex)
\V
# example: searches for ****
/\V****

# fuzzy find a file
:FZF

# interactive terminal
:terminal
# split and run top
:split term://top

# exit to normal mode
<C-\><C-n>

# DEBUGGING
# start debugging session with ./out
:packadd termdebug
:Termdebug ./out

# inspect variable under cursor (editor, normal mode)
K

# COMMANDLINE MODE
# open commandline window
q:
# open search history window
q/
# open commandline window from prompt
<C-f>

# EX COMMANDS
# where file name is expected:
# current file
%
# argument list
##

# FZF.VIM
# fuzzy search help pages
:Helptags
# fullscreen fuzzy search
!
# example:
:Lines!

# SESSIONS
# create Session.vim
:mks[ession]
# restore session
:source Session.vim
