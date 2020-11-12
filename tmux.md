# vi-copy mode
prefix [
# paste
prefix ]

#split horizontally, vertically
prefix %
prefix "

# sync panes
:set synchronize-panes on

# rename window
prefix ,
    or
:rename-window

# rename session
prefix $
    or
:rename-session

# resize pane
prefix ctrl arrow_key
# resize pane (up, 5 lines)
:resize-pane -U 5

# switch to prev session
prefix (
# interactively select session
prefix s

# list and interactively select windows
prefix w

# move window to index (prompt)
prefix .

# briefly display pane indexes
prefix q

# rotate panes in curent window
prefix ctrl o
