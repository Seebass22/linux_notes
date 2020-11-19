# find package that provides specific file
dnf provides */whatever.h

# list files in package
dnf repoquery -l <packagename>

# find package that provides specific executable
dnf whatprovides xxd

# list packages from repo
dnf repository-packages <repo-name> list

# remove packages from repo
dnf repository-packages <repo-name> remove
