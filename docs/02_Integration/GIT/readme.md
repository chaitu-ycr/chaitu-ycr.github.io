# 🐙 Git Notes

A concise, organized Git cheat sheet for daily use.

---

## 1. 🚀 Getting Started

| Task                        | Command/Instruction |
|-----------------------------|--------------------|
| Check Git version           | `git --version`    |
| Install Git                 | [Download Git](https://git-scm.com/downloads) and follow platform instructions |
| Initialize repository       | `git init`         |
| Get help                    | `git help` or `git <command> --help` |
| Check if in a Git repo      | `git rev-parse --is-inside-work-tree` |
| Show current config         | `git config --list` |
| Show working tree status    | `git status` |
| List remotes                | `git remote -v` |
| Add all files and commit    | `git add .`<br>`git commit -m "Initial commit"` |
| Clone via HTTPS             | `git clone https://github.com/user/repo.git` |

> 💡 **Tip:** Always initialize a repository with `git init` before running other commands in a new project.

---

## 2. ⚙️ Configuration

### Scopes

| Scope   | List Config                | Edit Config                |
|---------|----------------------------|----------------------------|
| System  | `git config --system --list` | `git config --system --edit` |
| Global  | `git config --global --list` | `git config --global --edit` |
| Local   | `git config --local --list`  | `git config --edit`          |

### Common Settings

| Setting           | Command Example |
|-------------------|----------------|
| User Name/Email   | `git config --global user.name "Your Name"`<br>`git config --global user.email "your_email@example.com"` |
| Editor            | `git config --global core.editor "code --wait"` |
| Diff/Merge Tool   | `git config --global diff.tool <toolname>`<br>`git config --global merge.tool <toolname>` |
| Aliases           | `git config --global alias.co checkout` |
| Default Branch    | `git config --global init.defaultBranch main` |
| Colored Output    | `git config --global color.ui auto` |
| Line Endings      | Windows: `git config --global core.autocrlf true`<br>macOS/Linux: `git config --global core.autocrlf input` |
| Credential Helper | `git config --global credential.helper cache` |
| Push Default      | `git config --global push.default simple` |
| HTTP/Network      | `git config --global http.postBuffer 524288000`<br>`git config --global http.lowSpeedLimit 0`<br>`git config --global http.lowSpeedTime 999999` |

#### Git LFS Timeouts

```sh
git config lfs.dialtimeout 3600
git config lfs.activitytimeout 3600
git config lfs.tlstimeout 3600
git config lfs.keepalive 3600
git config lfs.transfer.maxretries 10
```

> 💡 **Tip:** Use global settings for identity/editor, local for repo-specific preferences. Aliases speed up common commands.

---

## 3. 🔑 SSH Key Management

| Task                        | Command/Instruction |
|-----------------------------|--------------------|
| Generate Ed25519 key        | `ssh-keygen -t ed25519 -C "your_email@example.com"` |
| Generate RSA key            | `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` |
| Custom file                 | `ssh-keygen -t ed25519 -C "your_email@example.com" -f ~/.ssh/my_custom_key` |
| Add public key to provider  | `cat ~/.ssh/id_ed25519.pub` (copy and paste) |
| Test SSH connection         | `ssh -T git@github.com` |
| Use specific SSH key        | Edit `~/.ssh/config`:<br>`Host github.com`<br>  User git<br>  IdentityFile ~/.ssh/my_custom_key`<br>or use `ssh -i ~/.ssh/my_custom_key` |
| Add key to agent            | `eval "$(ssh-agent -s)"`<br>`ssh-add ~/.ssh/id_ed25519` |
| List/remove loaded keys     | `ssh-add -l`<br>`ssh-add -d ~/.ssh/id_ed25519` |
| SSH timeout                 | Edit `~/.ssh/config`:<br>`Host *`<br>`  ServerAliveInterval 60`<br>`  ServerAliveCountMax 120` |

> 🔒 **Tip:** Use a passphrase for private key security. Use SSH config for multiple keys/accounts.

---

## 4. 📦 Cloning Repositories

| Task                        | Command |
|-----------------------------|---------|
| Clone repo                  | `git clone <repository_url> [directory_name]` |
| Clone specific branch/tag   | `git clone -b <branch_name> <repository_url> <target_directory>`<br>`git clone --branch <tag_name> --single-branch <repository_url>` |
| Shallow/sparse/submodules   | `git clone --depth 1 <repository_url>`<br>`git clone --filter=blob:none --sparse <repository_url>`<br>`cd <repo>`<br>`git sparse-checkout init --cone`<br>`git sparse-checkout set <folder_or_file>`<br>`git clone --recurse-submodules <repository_url>` |
| Clone using SSH             | `git clone git@github.com:user/repo.git` |

> 🏃 **Tip:** Use shallow/sparse clones for large repos or CI/CD. Mirror/bare clones for backups/servers.

---

## 5. 🌳 Branching & Switching

| Task                        | Command |
|-----------------------------|---------|
| List branches               | `git branch` (local)<br>`git branch -a` (all)<br>`git branch -r` (remote) |
| Show last commit/tracking   | `git branch -v` / `git branch -vv` |
| Create/rename/delete branch | `git branch <new_branch>`<br>`git branch -m <new_name>`<br>`git branch -d <branch>` / `git branch -D <branch>` |
| Delete remote branch        | `git push origin --delete <branch>` |
| Set upstream                | `git branch --set-upstream-to=origin/<remote_branch> <local_branch>` |
| Switch branch               | `git switch <branch>` or `git checkout <branch>` |
| Create and switch           | `git switch -c <new_branch>` or `git checkout -b <new_branch>` |
| Restore file                | `git restore <file>` or `git checkout -- <file>` |
| Restore to previous commit  | `git checkout <commit_hash> -- <file>` |
| Detached HEAD               | `git checkout <commit_hash>` or `git checkout <tag_name>` |
| Partial/selected file checkout | `git checkout <branch> -- <file_or_folder>` |
| Merge/compare               | `git merge <branch>`<br>`git diff <branch1>..<branch2>` |

> 🌱 **Tip:** Use `git switch` for branches, `git restore` for files (modern Git).

---

## 6. ⬇️ Fetch & Pull

| Task                        | Command |
|-----------------------------|---------|
| Fetch                       | `git fetch [origin] [branch]`<br>`git fetch --all`<br>`git fetch --prune`<br>`git fetch --tags` |
| Pull                        | `git pull [origin] [branch]`<br>`git pull --rebase`<br>`git pull --autostash` |
| After fetch                 | `git log HEAD..origin/<branch>`<br>`git diff HEAD origin/<branch>` |

> 🧲 **Tip:** `git fetch` is safe and non-destructive. Use `--rebase` for linear history.

---

## 7. ✍️ Add, Status, Commit

| Task                        | Command |
|-----------------------------|---------|
| Stage files                  | `git add <file>`<br>`git add .`<br>`git add -A`<br>`git add -u` |
| Interactive/patch            | `git add -p` |
| Force add ignored            | `git add -f <file>` |
| Pattern/directory            | `git add '*.txt'`<br>`git add <directory>/` |
| Dry run                      | `git add --dry-run .` |
| Show status                  | `git status`<br>`git status -s`<br>`git status --porcelain`<br>`git status --untracked-files=all`<br>`git status --ignored`<br>`git status <path>` |
| Commit staged                | `git commit`<br>`git commit -m "Message"` |
| Commit all modified/deleted  | `git commit -a -m "Message"` |
| Amend last commit            | `git commit --amend`<br>`git commit --amend -m "New message"` |
| Custom author/date           | `git commit --author="Name <email>" -m "Message"`<br>`git commit --date="YYYY-MM-DD HH:MM:SS" -m "Message"` |
| Skip hooks/signoff/sign      | `git commit --no-verify -m "Message"`<br>`git commit --signoff -m "Message"`<br>`git commit -S -m "Message"` |
| Partial commit               | `git add <file1> <file2>`<br>`git commit -m "Partial commit"` |

> 📝 **Tip:** Use `git status` to review staged/unstaged changes. Only amend unpushed commits.

---

## 8. 🚀 Push

| Task                        | Command |
|-----------------------------|---------|
| Push branch/tag             | `git push origin <branch>`<br>`git push origin <tag>`<br>`git push origin --tags` |
| Push all branches           | `git push --all origin` |
| Force push                  | `git push origin <branch> --force`<br>`git push --force-with-lease origin <branch>` |
| Set upstream                | `git push -u origin <branch>` |
| Delete remote branch/tag    | `git push origin --delete <branch>`<br>`git push origin :refs/tags/<tag>` |
| Dry run/mirror              | `git push --dry-run`<br>`git push --mirror <remote>` |

> ⚠️ **Tip:** Prefer `--force-with-lease` over `--force`.

---

## 9. 📜 Log & Reflog

| Task                        | Command |
|-----------------------------|---------|
| Basic/compact/graph         | `git log`<br>`git log --oneline`<br>`git log --graph --oneline --all` |
| Custom format/filter        | `git log --pretty=format:"%h %s"`<br>`git log --author="Name"`<br>`git log --grep="term"`<br>`git log <commit1>..<commit2>`<br>`git log -- <file>` |
| Since/until                 | `git log --since="YYYY-MM-DD"`<br>`git log --until="YYYY-MM-DD"` |
| Show stats/patches          | `git log --stat`<br>`git log -p` |
| Show merges/no-merges       | `git log --merges`<br>`git log --no-merges` |
| Decorate                    | `git log --decorate` |
| Show reflog                 | `git reflog` |

> 🔍 **Tip:** Combine options for powerful queries.

---

## 10. 🪄 Rebase

| Task                        | Command |
|-----------------------------|---------|
| Rebase onto branch          | `git rebase <branch>` |
| Interactive rebase          | `git rebase -i <branch>`<br>`git rebase -i HEAD~<n>` |
| Continue/skip/abort         | `git rebase --continue`<br>`git rebase --skip`<br>`git rebase --abort` |
| Autosquash                  | `git rebase -i --autosquash <branch>` |
| Rebase all local branches   | `git fetch --all`<br>`git rebase origin/<branch>` |
| Preserve merges             | `git rebase -p <branch>` |

> ⚠️ **Note:** Rebasing rewrites history. Avoid on shared branches.

---

## 11. 👜 Stash

| Task                        | Command |
|-----------------------------|---------|
| Stash changes               | `git stash`<br>`git stash push -m "Message"`<br>`git stash push -u` (include untracked)<br>`git stash push -a` (include ignored) |
| List/show/apply/pop/drop/clear | `git stash list`<br>`git stash show [-p <stash@{n}>]`<br>`git stash apply [<stash@{n}>]`<br>`git stash pop [<stash@{n}>]`<br>`git stash drop <stash@{n}>`<br>`git stash clear` |
| Branch from stash           | `git stash branch <branch> [<stash@{n}>]` |

> 🧳 **Tip:** Use before switching branches or rebasing.

---

## 12. 🧹 Clean, Reset, Restore

| Task                        | Command |
|-----------------------------|---------|
| Remove untracked files/dirs | `git clean -xfd` |
| Dry run                     | `git clean -xfdn` |
| Remove only ignored         | `git clean -Xfd` |
| Reset tracked files         | `git reset --hard` |
| Unstage files               | `git reset <file>` |
| Reset to commit             | `git reset --hard <commit_hash>` |
| Remove last commit(s)       | `git reset --hard HEAD~1`<br>`git reset --hard HEAD~<N>` |
| Restore file/all            | `git restore <file>` or `git checkout -- <file>`<br>`git restore .` or `git checkout -- .` |

> ⚠️ **Warning:** These commands are destructive. Use `--dry-run` with `git clean` to preview.

---

## 13. 🧩 Submodules

| Task                        | Command |
|-----------------------------|---------|
| Add submodule               | `git submodule add <repository_url> [<path>]` |
| List/status/init/update     | `git submodule`<br>`git submodule status`<br>`git submodule init`<br>`git submodule update --init --recursive` |
| Update to latest            | `git submodule update --remote --merge` |
| Remove submodule            | 1. `git submodule deinit -f <path>`<br>2. `rm -rf .git/modules/<path>`<br>3. `git rm -f <path>` |
| Clone with submodules       | `git clone --recurse-submodules <repository_url>` |
| Sync URLs                   | `git submodule sync --recursive` |

> 🧩 **Tip:** Always commit after updating submodules.

---

## 14. 🏷️ Tags

| Task                        | Command |
|-----------------------------|---------|
| Create tag                  | `git tag <tag>`<br>`git tag -a <tag> -m "Message"`<br>`git tag -s <tag> -m "Message"` |
| List/search                 | `git tag`<br>`git tag -l "<pattern>"` |
| Show details                | `git show <tag>` |
| Push/delete                 | `git push origin <tag>`<br>`git push origin --tags`<br>`git tag -d <tag>`<br>`git push origin :refs/tags/<tag>` |
| Move tag                    | `git tag -d <tag>`<br>`git tag <tag> <commit>`<br>`git push --force origin <tag>` |
| Checkout/branch from tag    | `git checkout <tag>`<br>`git switch --detach <tag>`<br>`git checkout -b <branch> <tag>` |

> 🏷️ **Tip:** Use annotated/signed tags for releases.

---

## 15. 🍒 Cherry-pick

| Task                        | Command |
|-----------------------------|---------|
| Apply commit(s)             | `git cherry-pick <commit>`<br>`git cherry-pick <commit1> <commit2>`<br>`git cherry-pick <start>^..<end>` |
| Edit/sign/no-commit         | `git cherry-pick -e <commit>`<br>`git cherry-pick -S <commit>`<br>`git cherry-pick -n <commit>` |
| Custom author               | `git cherry-pick --author="Name <email>" <commit>` |
| Conflict resolution         | `git cherry-pick --continue`<br>`git cherry-pick --skip`<br>`git cherry-pick --abort` |
| Merge strategy              | `git cherry-pick -X theirs <commit>` |

> 🍒 **Tip:** Use for moving individual commits between branches.

---

## 16. 🛠️ Other Useful Commands

| Task                        | Command |
|-----------------------------|---------|
| Graphical history           | `gitk`<br>`gitk --all`<br>`git log --graph --oneline --all` |
| Diff tools                  | `git difftool`<br>`git difftool <commit1> <commit2>` |
| Show file history/blame     | `git blame <file>` |
| Show remotes                | `git remote -v`<br>`git remote show <remote>` |
| Show tags/refs              | `git show-ref --tags`<br>`git show-ref` |
| Show staged/unstaged changes| `git diff --cached`<br>`git diff` |
| Show unpushed/unpulled commits | `git log @{u}..`<br>`git log ..@{u}` |
| Show ignored files          | `git check-ignore -v *`<br>`git status --ignored` |
| Show current branch/root/commit | `git rev-parse --abbrev-ref HEAD`<br>`git rev-parse --show-toplevel`<br>`git rev-parse HEAD` |
| Show conflicts after merge  | `git diff --name-only --diff-filter=U` |

> 🛠️ **Tip:** Set your preferred diff tool with:<br>`git config --global diff.tool <toolname>`

> 📄 **Tip:** Create a `.gitignore` file to exclude files/folders from version control. Example:  
> `echo node_modules/ > .gitignore`

