---
title: "Thứ 3"
weight: 2
---

# Ngày: Thứ 3

## Công việc đã làm

- Tìm hiểu cấu trúc thư mục content của Hugo.
- Thực hành tạo và chỉnh sửa file Markdown.
- Tìm hiểu cách sử dụng theme hugo-theme-learn.
- Kiểm tra website sau khi thay đổi nội dung.

## Ví dụ thực hành Git

### Common Commands

| Command | Meaning |
| --- | --- |
| `git init` | Create a new Git repository |
| `git remote` | Manage connections to remote repositories |
| `git clone` | Copy a remote repository to the local machine |
| `git fetch` | Download remote changes without merging them |
| `git pull` | Download and merge remote changes |
| `git status` | Show the current repository state |
| `git branch` | List, create, or delete branches |
| `git switch` | Move to another branch |
| `git checkout` | Switch branches or restore files |
| `git add` | Stage changes for the next commit |
| `git commit` | Save staged changes to the repository history |
| `git commit --amend` | Update the latest commit |
| `git push` | Upload local commits to a remote repository |
| `git reset` | Unstage changes or move commit history |
| `git rebase` | Reapply commits on top of another branch |
| `git rebase -i` | Edit, squash, or reorder commits interactively |
| `git stash` | Temporarily save uncommitted work |
| `git stash pop` | Restore the latest stashed work |
| `git merge` | Combine changes from another branch |
| `git cherry-pick` | Apply a specific commit to the current branch |

### Merge Conflict Handling

| Situation | Solution in Code Source Control |
| --- | --- |
| Keep changes from both branches | Open the file, edit the conflict manually, then mark it as resolved |
| Keep the current branch version | Use Accept Current Change in the conflict editor |
| Keep the incoming branch version | Use Accept Incoming Change in the conflict editor |
| Cancel the merge | Open Source Control, use the `...` menu, then choose Abort Merge |
| Resolve conflicts manually | Review the marked conflict blocks and keep the correct final code |

### Ví dụ từng lệnh

#### git init

#### git remote

```bash
git remote
```

![git remote](/images/git-practice/19-git-remote.png)

#### git clone

#### git fetch

```bash
git fetch
```

![git fetch](/images/git-practice/17-git-fetch.png)

#### git pull

```bash
git pull
```

![git pull](/images/git-practice/18-git-pull.png)

#### git status

```bash
git status
```

![git status](/images/git-practice/01-git-status.png)

#### git branch

```bash
git branch
```

![git branch](/images/git-practice/04-git-branch.png)

#### git switch

```bash
git switch feature/git-practice
```

![git switch feature](/images/git-practice/05-git-switch-feature.png)

```bash
git switch main
```

![git switch main](/images/git-practice/06-git-switch-main.png)

```bash
git switch -c cherry-pick-demo
```

![git switch -c](/images/git-practice/13-git-switch-c.png)

#### git checkout

#### git add

```bash
git add git-practice/git-practice.md
```

![git add](/images/git-practice/02-git-add.png)

#### git commit

```bash
git commit -m "Add Git practice file"
```

![git commit](/images/git-practice/03-git-commit.png)

```bash
git commit -m "Add amend practce"
```

![git commit typo](/images/git-practice/10-git-commit-typo.png)

#### git commit --amend

```bash
git commit --amend -m "Add amend practice"
```

![git commit --amend](/images/git-practice/11-git-commit-amend.png)

#### git log

```bash
git log --oneline
```

![git log --oneline](/images/git-practice/12-git-log-oneline.png)

#### git push

#### git reset

```bash
git reset --soft HEAD~1
```

![git reset --soft](/images/git-practice/16-git-reset-soft.png)

#### git rebase

#### git rebase -i

#### git stash

```bash
git stash
```

![git stash](/images/git-practice/08-git-stash.png)

#### git stash pop

```bash
git stash pop
```

![git stash pop](/images/git-practice/09-git-stash-pop.png)

#### git merge

```bash
git merge feature/git-practice
```

![git merge fast-forward](/images/git-practice/07-git-merge-ff.png)

```bash
git merge conflict-demo
```

![git merge conflict](/images/git-practice/15-git-merge-conflict.png)

#### git cherry-pick

```bash
git cherry-pick b2acd16
```

![git cherry-pick](/images/git-practice/14-git-cherry-pick.png)

## Khó khăn gặp phải

- Cần làm quen với Front Matter của Hugo.
- Một số thay đổi cần kiểm tra lại trên môi trường local.

## Kế hoạch ngày tiếp theo

- Tiếp tục hoàn thiện weekly report.
- Tìm hiểu cách tùy chỉnh giao diện.
- Kiểm tra responsive và navigation của website.