# practice
Because practice makes perfect.

# Lessons
## Undoing
1. Changing History
   1. Make changes, commit, make more changes
   1. Amend previous commit without changing commit message
<details>
  <summary>Show answer</summary>
  <pre> 
  git commit --amend --no-edit
  </pre>
</details>
<br>

2. The Three Stages of Git
   1. Make changes and commit
   1. Undo commit only
   1. Unstage files
   1. Undo changes in working directory (so that files look like previous commit
<details>
  <summary>Show answer</summary>
  <pre> 
  ii.  git reset --soft HEAD^
  iii. git reset .
  iv.  git checkout .
  </pre>
</details>
<br>

## Git Object Model
3. What Is A Repo? 
   1. View the checksums of all git objects in repo (ignoring `info` and `pack` dirs)
   1. View the contents of two objects: one blob and one tree
   1. Show the trees and blobs in the current commit
   1. View the contents of the tree object
<details>
  <summary>Show answer</summary>
  <pre> 
  i.   tree -I "info|pack" .git/objects
  ii.  git cat-file -t <checksum>   # To determine type of obj
       git cat-file -p <checksum>   # To view contents of obj
  iii. git ls-tree master <or checksum>
  iv.  git cat-file -p <checksum>   # To view contents of obj (even trees!)
  </pre>
</details>
<br>

4. Git Object Model: Investigate Master 
   1. Print the object type of master.
   1. Pretty print the object.
   1. List the contents of the object (hint: use `ls-tree`).
   1. Use a different command to list the contents of that object (hint: use the checksum of the tree from the previous command).
   1. Print the object type of that tree.
   1. Print the object type of one of the blobs in that tree.
   1. Pretty print the blob.
<details>
  <summary>Show answer</summary>
  <pre> 
  i.   git cat-file -t master
  ii.  git cat-file -p master
  iii. git ls-tree master
  iv.  git cat-file -p &lt;checksum of tree&gt;
  v.   git cat-file -t &lt;checksum of tree&gt;
  vi.  git cat-file -t &lt;checksum of a blob&gt;
  vii. git cat-file -p &lt;checksum of a blob&gt;
  </pre>
</details>
<br>
