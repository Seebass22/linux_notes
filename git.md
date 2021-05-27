# LOG
# FORMATTING
# simple log
git log --oneline

# only show changed files
git log --name-only

# show diffstat (no. of changed lines per file) for every commit
git log --stat

# group commits by author
git shortlog

# FILTERING
# latest 3 commits
git log -3

# after or before date
git log --before="2020-1-1"

# by author (accepts regex)
git log --author="seb"
git log --author="seb\|bob"

# by commit message
git log --grep="UI"

# by file
git log -- foo.py

# find commit that modifies particular line of code
# example: find all commits that modified/added/removed a line containing Debug.Log
git log -S"Debug.Log"

# filter out all merge commits (or only show merges)
git log --no-merges
git log --merges


# MISC
# add everything on root dir
git add :/

# remove file from index but not working tree
git rm --cached <file>

# undo last commit but keep changes (add --hard to discard changes)
git reset HEAD~1

# undo git reset (restore changes)
git reflog
git checkout <SHA>    and    git checkout -b <new branch name>
    or
git reset --hard <SHA>

# find bug through binary search
git bisect

# rewrite history (change commit message, split commits, etc)
# [modify last 8 commits]
git rebase -i HEAD~8

# find commit where file was deleted
git log --diff-filter=D -- path/to/file
# checkout version at the commit before
git checkout <deleting_commit>^ -- <file_path>

# replay commit on current branch
git cherry-pick <SHA>

# ignore changes to tracked file locally
git update-index --skip-worktree <file_path>

# abort merge after pulling
## clear editor window
git merge --abort

# check for whitespace errors or conflict markers
git diff --check
# giff staged files
git diff --staged

# local gitignore (not tracked)
.git/info/exclude

# create source tarball (prints to stdout by default)
git archive <revision>
## use tar.gz format
git archive --format=tar.gz HEAD > source_code.tar.gz
## output zip, infer output format by extension
git archive -o latest.zip HEAD
## create a zip that contains directory with source
## this will only add files relative to directory it is run in, so run it from repo root 
--prefix=dirname/
git archive --prefix=latest/ -o latest.zip HEAD
