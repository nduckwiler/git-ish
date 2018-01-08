# practice
Because practice makes perfect.

# Lessons
## Undoing
<details>
  <summary>1. Make changes, commit, make more changes, amend previous commit without changing commit message</summary>
  <br>
  <pre> 
  git commit --amend --no-edit
  </pre>
</details>

<details>
  <summary>2. Make changes, commit, undo commit only, unstage files, undo changes in working directory (so that files look like previous commit</summary>
  <br>
  <pre> 
  git reset --soft HEAD^
  git reset .
  git checkout .
  </pre>
</details>

<details>
  <summary>3. View the checksums of all git objects in repo (ignoring `info` and `pack` dirs), view the contents of two objects: one blob and one tree, show the trees and blobs in the current commit, view the contents of the tree object</summary>
  <br>
  <pre> 
  tree -I "info|pack" .git/objects
  git cat-file -t <checksum>   # To determine type of obj
  git cat-file -p <checksum>   # To view contents of obj
  git ls-tree master <or checksum>
  git cat-file -p <checksum>   # To view contents of obj (even trees!)
  </pre>
</details>

<details>
  <summary>
  4. Print the object type of master.
  * Pretty print the object.
  * List the contents of the object (hint: use `ls-tree`).
  * Use a different command to list the contents of that object (hint: you'll need to use the checksum of the tree from the previous command).
  * Print the object type of that tree.
  * Print the object type of one of the blobs in that tree.
  * Pretty print the blob.
  <br>
  <pre> 
  git cat-file -t master
  git cat-file -p master
  git ls-tree master
  git cat-file -p <checksum of tree>
  git cat-file -t <checksum of tree>
  git cat-file -t <checksum of a blob>
  git cat-file -p <checksum of a blob>
  </pre>
</details>
