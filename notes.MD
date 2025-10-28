# 🧩 GIT MASTER COMMAND CHEAT SHEET — All in One 🚀

This guide gives you a **complete overview of essential Git commands**, their **purpose**, **usage examples**, **behind-the-scenes behavior**, and **simple explanations** — all in one place.  
Perfect for **learning, revising, and interview prep** ✅

---

## ⚡ GIT COMMANDS TABLE

| 🧠 **Command**             | 🎯 **Purpose**                           | 🧰 **Example**                            | ⚙️ **What It Does (Behind the Scenes)**                    | 💡 **Simple Explanation / Memory Trick**         |
| -------------------------- | ---------------------------------------- | ----------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------ |
| **`git`**                  | The main Git tool                        | `git --version`                           | Verifies Git is installed.                                 | 🧍‍♂️ Git = Your version control manager.        |
| **`git init`**             | Create a new local repo                  | `git init`                                | Creates `.git/` folder with all version-tracking info.     | 🏁 “Start a new project timeline.”               |
| **`git clone`**            | Copy remote repo locally                 | `git clone <url>`                         | Downloads full repo + commit history.                      | 📥 “Duplicate GitHub project to your system.”    |
| **`git add`**              | Stage files for commit                   | `git add file.txt` or `git add .`         | Moves changes from **Working Directory → Staging Area**.   | 📦 “Tell Git: I’m ready to commit these.”        |
| **`git status`**           | Show current changes                     | `git status`                              | Lists untracked, staged, and committed files.              | 🕵️ “Check what’s changed.”                      |
| **`git commit`**           | Save staged changes permanently          | `git commit -m "message"`                 | Moves changes from **Staging → Local Repository**.         | 💾 “Take a snapshot of work.”                    |
| **`git log`**              | Show commit history                      | `git log`                                 | Displays all commits (hash, author, date, msg).            | 📜 “Timeline of your project.”                   |
| **`git log --oneline`**    | Short commit history                     | `git log --oneline`                       | Shows one-line per commit (short hash + msg).              | 🧾 “Compact project timeline.”                   |
| **`git branch`**           | List branches                            | `git branch`                              | Shows all branches and current one (`*`).                  | 🌿 “Branches = separate storylines.”             |
| **`git branch <name>`**    | Create new branch                        | `git branch feature1`                     | Creates new pointer from current commit.                   | 🌱 “Start a new mini-project.”                   |
| **`git checkout <name>`**  | Switch branches                          | `git checkout feature1`                   | Moves HEAD pointer to another branch.                      | 🔀 “Jump to another storyline.”                  |
| **`git switch <name>`**    | (Modern version of checkout)             | `git switch main`                         | Safer way to switch branches.                              | 🚦 Easier than checkout.                         |
| **`git merge <branch>`**   | Merge another branch                     | `git merge feature1`                      | Combines commits from that branch into current.            | 🤝 “Bring their work into mine.”                 |
| **`git rebase <branch>`**  | Reapply commits on top of another branch | `git rebase main`                         | Moves commits to new base commit.                          | 🧱 “Rebuild history linearly.”                   |
| **`git diff`**             | Show file differences                    | `git diff`                                | Compares working dir vs last commit.                       | 🔍 “What changed exactly?”                       |
| **`git pull`**             | Get + merge from remote                  | `git pull origin main`                    | = `fetch` + `merge`. Downloads and applies remote changes. | 🌐 “Update my local copy.”                       |
| **`git fetch`**            | Only get updates (no merge)              | `git fetch origin`                        | Downloads new commits but doesn’t apply them.              | 📡 “See updates but don’t apply yet.”            |
| **`git push`**             | Upload local commits to remote           | `git push origin main`                    | Sends local commits → GitHub.                              | 🚀 “Publish my changes.”                         |
| **`git remote -v`**        | Show remote URLs                         | `git remote -v`                           | Lists where fetch/push happens.                            | 🌍 “See which GitHub repo is linked.”            |
| **`git revert <id>`**      | Undo commit safely                       | `git revert a1b2c3`                       | Adds new commit reversing old one.                         | 🔁 “Undo but keep history.”                      |
| **`git reset --soft`**     | Undo commit, keep staged                 | `git reset --soft HEAD~1`                 | Moves HEAD pointer back, keeps files staged.               | 🧮 “Undo commit but still ready to recommit.”    |
| **`git reset --mixed`**    | Undo commit + unstage                    | `git reset --mixed HEAD~1`                | Unstages files (keep changes).                             | 🧩 “Undo and move changes back to working area.” |
| **`git reset --hard`**     | Undo + delete everything                 | `git reset --hard HEAD~1`                 | Resets to commit, discards all new changes.                | 💣 “Time travel and erase!”                      |
| **`git stash`**            | Save work temporarily                    | `git stash` / `git stash pop`             | Saves working files in hidden stack.                       | 🗄️ “Hide half-done work, come back later.”      |
| **`git squash`**           | Combine commits                          | `git rebase -i HEAD~3` then mark `squash` | Combines multiple commits into one.                        | 🧃 “Merge small commits → one clean one.”        |
| **`git cherry-pick <id>`** | Copy one commit from another branch      | `git cherry-pick a1b2c3`                  | Applies that specific commit to current branch.            | 🍒 “Pick 1 good commit and apply here.”          |
| **`git tag`**              | Label a commit                           | `git tag v1.0`                            | Marks commit as version/release.                           | 🏷️ “Name a version.”                            |
| **`git show`**             | View commit details                      | `git show <commit-id>`                    | Shows changes made in that commit.                         | 🔎 “See what this commit did.”                   |
| **`git rm`**               | Remove file from tracking                | `git rm file.txt`                         | Deletes file and stages its removal.                       | 🧹 “Remove file from project.”                   |
| **`git mv`**               | Rename file                              | `git mv old.txt new.txt`                  | Renames and stages change.                                 | ✍️ “Rename with tracking.”                       |
| **`git restore`**          | Undo changes in working directory        | `git restore file.txt`                    | Restores file to last commit version.                      | 🧱 “Undo changes before staging.”                |
| **`git reflog`**           | Show all movements of HEAD               | `git reflog`                              | Shows recent HEAD positions (includes resets).             | 🕰️ “Full movement history (your time machine).” |
| **`git config`**           | Configure user or repo                   | `git config --global user.name "Kalyan"`  | Stores Git settings.                                       | ⚙️ “Set your Git identity.”                      |
| **`git merge --abort`**    | Stop a merge in conflict                 | `git merge --abort`                       | Cancels merge process.                                     | 🚫 “Stop merge safely.”                          |
| **`git clean -f`**         | Remove untracked files                   | `git clean -f`                            | Deletes untracked files.                                   | 🧽 “Remove junk files.”                          |

---

## 🧠 Git Workflow Overview

| 📍 **Stage** | 🧭 **Meaning** | ⚙️ **Commands Involved** | 🧩 **Notes** |
|--------------|----------------|---------------------------|--------------|
| **Working Directory** | Where you edit files | `git status`, `git diff` | Untracked or modified files live here. |
| **Staging Area** | Prepare changes for commit | `git add`, `git reset` | Like a “Ready to save” zone. |
| **Local Repository** | Saved commits (local only) | `git commit`, `git log` | Stored in your `.git/` folder. |
| **Remote Repository** | Cloud copy (GitHub, etc.) | `git push`, `git pull`, `git fetch` | Shared repo accessible by others. |

---

## ⚙️ Technical Internals (Quick View)

| 🔧 **Action** | 🧩 **What Happens Inside Git** |
|---------------|-------------------------------|
| `git add` | Adds file snapshots (SHA hashes) to **staging index**. |
| `git commit` | Creates a **commit object** linking to parent + file tree. |
| `git push` | Uploads commit objects to remote repository. |
| `git pull` | Runs `fetch` then `merge` your local branch. |
| `git reset` | Moves the **HEAD pointer** to another commit. |
| `git revert` | Creates a *new commit* that reverses previous changes. |
| `git stash` | Stores changes as a temporary diff in `.git/refs/stash`. |

---

## 🧩 Category Shortcuts

| 📚 **Category** | 🧠 **Commands** | 🪄 **Memory Trick** |
|------------------|----------------|---------------------|
| 🚀 **Start Project** | `git init`, `git clone` | “Start or copy project.” |
| ✍️ **Daily Work** | `git add`, `git commit`, `git status`, `git log` | “Track, Save, Check.” |
| 🌿 **Branching** | `git branch`, `git checkout`, `git switch`, `git merge`, `git rebase` | “Create, Jump, Combine.” |
| 🌍 **Remote** | `git push`, `git pull`, `git fetch`, `git remote -v` | “Sync with GitHub.” |
| 🧹 **Undo / Fix** | `git reset`, `git revert`, `git restore`, `git stash` | “Undo or clean safely.” |
| 🍒 **Advanced** | `git cherry-pick`, `git squash`, `git reflog`, `git tag` | “Pro-level Git moves.” |

---


| 🧩 **Command**                         | 🎯 **Purpose**                        | ⚙️ **What It Does**                                                  | 💡 **When to Use**                                  | 🧱 **Commits Lost?**   | 🧍‍♂️ **Affects main branch?** | 🧾 **Example**                           |
| -------------------------------------- | ------------------------------------- | -------------------------------------------------------------------- | --------------------------------------------------- | ---------------------- | ------------------------------ | ---------------------------------------- |
| `git branch -d branch_name`            | Safe delete local branch              | Deletes branch **only if merged** with main (protects unmerged work) | After merging branch work into main                 | ❌ No                   | ❌ No                           | `git branch -d feature/login`            |
| `git branch -D branch_name`            | Force delete local branch             | Deletes branch **even if not merged** (no safety check)              | When you’re sure you don’t need that branch anymore | ⚠️ Yes (if not merged) | ❌ No                           | `git branch -D test-feature`             |
| `git push origin --delete branch_name` | Delete remote branch (GitHub/GitLab)  | Removes the branch from the remote repository                        | To clean up remote after merge                      | ❌ No                   | ❌ No                           | `git push origin --delete feature/login` |
| `git push origin :branch_name`         | Old syntax for deleting remote branch | Same as above                                                        | Rarely used now                                     | ❌ No                   | ❌ No                           | `git push origin :feature/login`         |
| `git branch`                           | List local branches                   | Shows all branches in your local repo                                | To check before/after delete                        | ❌ No                   | ❌ No                           | `git branch`                             |
| `git branch -r`                        | List remote branches                  | Shows all branches on remote (origin)                                | To verify remote deletion                           | ❌ No                   | ❌ No                           | `git branch -r`                          |
| `git checkout branch_name`             | Switch branch                         | Moves you to another branch (can’t delete the one you’re on)         | Before deleting current branch                      | ❌ No                   | ❌ No                           | `git checkout main`                      |


| 💬 **Question**             | 🧠 **Answer**                                               |
| --------------------------- | ----------------------------------------------------------- |
| What does `-d` do?          | Safely deletes branch only if merged.                       |
| What does `-D` do?          | Force deletes branch even if not merged — can lose commits. |
| Does it delete main branch? | ❌ Never. It only deletes the branch you name.               |
| Does it delete commits?     | ❌ No (if merged). ⚠️ Yes (if not merged).                   |
| Does it create a commit?    | ❌ No. It only removes the branch pointer.                   |
| How to check if deleted?    | Run `git branch` (local) or `git branch -r` (remote).       |



🧠 Simple way to remember:

🟢 -d = “Delete safely after merging.”
🔴 -D = “Delete no matter what — even if not merged.”


🧩 Case 1 — Safe Delete (git branch -d feature)

✅ Only deletes if merged into main.
No commits lost.

Before:
           (feature)
               │
A --- B --- C --- D --- E   ← main
              \
               D --- E       ← feature (merged)

Command:
git checkout main
git branch -d feature

After:
A --- B --- C --- D --- E   ← main
(feature deleted)
✅ All commits safe in main



⚡ Case 2 — Force Delete (git branch -D feature)

⚠️ Deletes even if not merged.
Unmerged commits can be lost.

Before:
           (feature)
               │
A --- B --- C   ← main
        \
         D --- E   ← feature (NOT merged)

Command:
git checkout main
git branch -D feature

After:
A --- B --- C   ← main
(feature deleted)
💥 Commits D and E are not reachable (may be lost)


🧠 Simple way to remember:

Branch deletion = pointer removed, not a commit change.
-d = safe pointer removal --> Still no new commit is created.
-D = forced pointer removal  --> Still no new commit is created.

### 🏁 Final Note:
> 📘 **Tip for Interviews:**  
> Always explain **what happens internally** (like “moves HEAD pointer” or “creates new commit”) — it shows strong Git knowledge.