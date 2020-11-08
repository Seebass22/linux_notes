%% find commit where file was deleted
git log --diff-filter=D -- path/to/file
%% checkout version at the commit before
git checkout <deleting_commit>^ -- <file_path>

%% replay commit on current branch
git cherry-pick <SHA>

# LOG
%% simple log
git log --oneline

%% only show changed files
git log --name-only

%% undo last commit but keep changes (add --hard to discard changes)
git reset HEAD~1

%% undo git reset (restore changes)
git reflog
git checkout <SHA>    and    git checkout -b <new branch name>
    or
git reset --hard <SHA>

%% check for whitespace errors or conflict markers
git diff --check
%% giff staged files
git diff --staged

%% find bug through binary search
git bisect

%% rewrite history (change commit message, split commits, etc)
%% [modify last 8 commits]
git rebase --interactive HEAD~8
