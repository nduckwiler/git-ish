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
