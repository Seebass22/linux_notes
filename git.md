# find commit where file was deleted
git log --diff-filter=D -- path/to/file
# checkout version at the commit before
git checkout <deleting_commit>^ -- <file_path>

# replay commit on current branch
git cherry-pick <SHA>


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


# undo last commit but keep changes (add --hard to discard changes)
git reset HEAD~1

# undo git reset (restore changes)
git reflog
git checkout <SHA>    and    git checkout -b <new branch name>
    or
git reset --hard <SHA>

# check for whitespace errors or conflict markers
git diff --check
# giff staged files
git diff --staged

# find bug through binary search
git bisect

# rewrite history (change commit message, split commits, etc)
# [modify last 8 commits]
git rebase -i HEAD~8
