%% find package that provides specific file
dnf provides */whatever.h
%% list files in package
dnf repoquery -l <packagename>
%% list packages from repo
dnf repository-packages <repo-name> list
%% remove packages from repo
dnf repository-packages <repo-name> remove
