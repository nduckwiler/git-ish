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
