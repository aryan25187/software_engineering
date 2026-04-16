#  Assignment 2




---

##  The 3 Areas - How a File Moves

```
Working Directory -> Staging Area -> Repository
        git add           git commit
```

**Reverse flow:**
```
Staging -> Working ->  Gone
 git restore --staged   git restore
```

**Key Insight (basic-staging)**  
 A file can have **two versions of changes at once**:
 - `git diff` -> shows *unstaged*
 - `git diff --staged` -> shows *staged*

---

## Everyday Commands

```bash
git status                         # Check current state (always safe)
git log --oneline --graph --all   # Visualize history

git add <file>                    # Stage file
git add .                         # Stage everything
git commit -m "message"           # Commit changes

git diff                          # Unstaged changes
git diff --staged                 # Staged changes
git diff <b1> <b2>                # Compare branches

git branch                        # List branches
git switch <branch>               # Switch branch
git switch -c <branch>            # Create + switch
```

---

## "Oh No" Recovery

### Undo staged change (safe)
```bash
git restore --staged <file>
```

### Discard working changes (destructive)
```bash
git restore <file>
```

### Undo a commit (safe for shared history)
```bash
git revert <commit-sha>
```

### Remove untracked files
```bash
git clean -n        # preview (safe)
git clean -n -d     # preview incl. folders
git clean -f -d     # delete permanently
```

###  Stashing (pause work)
```bash
git stash
git stash apply --index
git stash drop
git stash list
```

Use `--index` to preserve staged vs unstaged changes

---

## Branch -> Merge -> Remote Workflow

### Start a feature
```bash
git switch -c feature-name
git add . && git commit -m "..."
```

### Merge back
```bash
git switch master
git merge feature-name
git branch -d feature-name
```

### Inspect before merging
```bash
git log --oneline --graph --all
git diff master..feature-name
```

### Remote basics
```bash
git remote -v
git push origin <branch>
git pull
git clone <url>
```

---

## Common Mistakes (From These Katas)

**basic-staging**
- `git diff` after staging -> saw nothing  
  -> Needed `git diff --staged`

- Used `git restore file.txt` to unstage  
  -> Deleted changes  
  -> Use `git restore --staged`

---

**basic-branching**
- Forgot `--all` in `git log --graph`  
  -> Missed other branches

---

**basic-revert**
- Thought revert deletes history  
  -> It **adds** an undo commit

---

**basic-cleaning**
- Almost ran `git clean -f` blindly  
  -> Always run `git clean -n` first

---

**basic-stashing**
- Used `git stash apply` without `--index`  
  -> Lost staged/unstaged separation

---



---

##  Quick Rules to Remember

-  Always start with `git status`
-  Always dry-run destructive commands (`-n`)
-  Use branches for *everything*
-  Stash when interrupted
-  Prefer `git revert` over rewriting history


