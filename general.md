# Shell wildcards
*               matches any string of characters
?               matches any single character
[set]           matches any character in the set of characters
[!set]          matches any character not in the set of characters
[a-g]           matches any character a-g
{txt,jpg,bmp}   matches anything in the list

%% nvim file.c file.h
nvim file.[ch]

%% nvim file.cpp file.h
nvim file.{cpp,h}

# LaTeX
%% automatic latex compilation
latexmk -pvc -pdf filename

%% remove latex compile files
latexmk -c  %% keep pdf
latexmk -C  %% delete pdf

%% latex documentation
texdoc {packagename}

%% programming & terminal help
curl cheat.sh/c++

%% show audio sources
pacmd list-sources

%% search installed packages
apt-cache search

%% find directory of program
which
whereis

%% create a symbolic link
ln -s file1 file2

%% display tree view of filesystem
tree
tree -d     %% only directories

%% find files
locate
locate term1 | grep term2
    or
find /usr -type f -name gcc     %% searches in usr for files called gcc
(slower than locate)

%% find documentation
whatis      or      man -f
apropos     or      man -k      // all man pages discussing a topic
info                            // GNU info pages

%% match exact string
grep -w "string"
grep "\<string\>"

%% display filetype information
file <files>

%% show word count and more
wc

%% close frozen SSH session
<enter>
~
.

%% reset terminal
reset

%% kill last suspended job
kill %%

%% read core file (debug)
gdb /path/to/application /path/to/corefile

%% show environment variables
env

%% invert grep
grep -v

%% update mpd db
mpc update

%% change keyboard layout
setxkbmap us

%% connect to known wifi network
nmcli connection up <network-name>

%% kill flatpak app
flatpak kill org.riot.Riot

%% show window info
xwininfo
xprop

%% unhighlight search in less
ESC u

%% indicate end of args
--
%%example:
man grep | grep -C5 -- '-C'

%% save to clipboard
echo asdf | xclip -selection clipboard
%% save to primary selection
echo adsf | xclip
%% paste from primary selection
<middle mouse button>

%% check spelling of text file
aspell check foo.txt

%% convert octal to hexadecimal
echo "obase=16; ibase=8; octal-number-here" | bc

%% find keycodes and and key symbols
xev

%% sort by 2nd field
sort -k 2

%% format as a table
column -t
