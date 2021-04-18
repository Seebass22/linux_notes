# find package that provides specific executable
dnf whatprovides xxd

# find package that provides specific file
dnf provides */whatever.h

# list files in package
dnf repoquery -l <packagename>

# list packages from repo
dnf repository-packages <repo-name> list

# list installed packages
dnf list installed
# all list commands allow you to filter using glob expressions
dnf list installed '*v42l*'

# list [installed] package groups
dnf group list [installed]

# remove packages from repo
dnf repository-packages <repo-name> remove

# include descriptions and URLs in search
dnf search all <term>

# dnf transaction history
dnf history

# undo or redo transaction
dnf history undo <id>
dnf history redo <id>

# list enabled repositories
dnf repolist --enabled
# more detailed info
dnf repolist --enabled -v
