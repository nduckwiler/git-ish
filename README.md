# git-ish
Because practice makes perfect.

This repository is a place to learn and practice git. Learn using the lessons in this __README__. Practice using any other files in the repo.

# Lessons
## Exploring Your Repo
1. Log
   1. Log the last 5 commits on your branch
   1. Log the last 10 commits on your branch, each with `oneline` of information
   1. Log the last 10 commits on your branch, each with `oneline` of information, in `graph` format
   1. Log the last 10 commits for `all` branches, each with `oneline` of information, in `graph` format (depending on your repo, the output here may be the same as the previous step)
<details>
  <summary>Show answer</summary>
  <pre> 
  i.  git log -5 
  ii. git log --oneline -10
  ii. git log --oneline --graph -10
  ii. git log --oneline --graph --all -10
  </pre>
</details>
<br>

## Undoing
1. Changing History
   1. Make changes and commit
   1. Change commit message
   1. Make changes and commit
   1. Make more changes
   1. Add recent changes to latest commit without changing commit message
<details>
  <summary>Show answer</summary>
  <pre>
  # make changes and commit
  ii. git commit --amend
  # make changes and commit
  # make more changes
  v.  git commit --amend --no-edit
  </pre>
</details>
<br>

2. The Three Stages of Git
   1. Make changes, stage them, and commit
   1. Undo commit only (HEAD should now reference previous commit)
   1. Unstage current changes
   1. Undo changes in working directory

Use `git show` and `git status` to see the effect of each command
<details>
  <summary>Show answer</summary>
  <pre> 
  i.   # make changes, stage them, and commit
  ii.  git reset --soft HEAD^
  iii. git reset .
  iv.  git checkout .
  </pre>
</details>
<br>

## Git Object Model
1. What Is A Repo? 
   1. View the directory containing all git objects in repo
<details>
  <summary>Show answer</summary>
  <pre> 
  i.   tree -I "info|pack" .git/objects  # OR
       ls .git/objects
  </pre>
</details>
<br>

2. Git Object Model: Investigate Master 
   1. `master` refers to a git object. Print the object type. Does it refer to a blob, tree, or commit?
   1. Pretty print a summary of the object.
   1. List the contents of the object (hint: use `ls-tree`).
   1. Use a different command to get the same output (hint: use the checksum of the tree from the previous command).
   1. Print the object type of that tree.
   1. Print the object type of one of the blobs in that tree.
   1. Pretty print the blob.
<details>
  <summary>Show answer</summary>
  <pre> 
  i.   git cat-file -t master (master is a reference to a commit)
  ii.  git cat-file -p master
  iii. git ls-tree master
  iv.  git cat-file -p &lt;checksum of tree&gt;
  v.   git cat-file -t &lt;checksum of tree&gt;
  vi.  git cat-file -t &lt;checksum of a blob&gt;
  vii. git cat-file -p &lt;checksum of a blob&gt;
  </pre>
</details>
<br>

3. Git Object Model: All Refs Lead to Commits 
   1. View all references in your git repository 
   1. `cat` the checksum (commit) to which master currently points to
   1. `show` the commit message related to that checksum
   1. Use `checkout` to create a new ref called `new-branch`
   1. Print the checksum to which `new-branch` currently points to (should be the same as `master`)
   1. Make a change, stage change, commit it
   1. Print the checksum to which `new-branch` currently points to (should be different than `master`)
   1. Delete that `new-branch` ref
<details>
  <summary>Show answer</summary>
  <pre> 
  # in root directory of repository

  i.    tree -C .git/refs # OR ls .git/refs

  ii.   cat .git/refs/heads/master

  iii.  git show &lt;checksum printed in previous step&gt;

  iv.   git checkout -b new-branch

  v.    cat .git/refs/heads/new-branch

  vi.   # make your changes, stage, and commit however you like

  vii.  cat .git/refs/head/new-branch

  viii. git checkout master && git branch -d new-branch
  </pre>
</details>
<br>
