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

### Terminal thực hành

```bash
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ./

nothing added to commit but untracked files present (use "git add" to track)

$ git add git-practice/git-practice.md
warning: could not open directory 'git-practice/git-practice/': No such file or directory
fatal: pathspec 'git-practice/git-practice.md' did not match any files

$ git commit -m "Add Git practice file"
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ./

nothing added to commit but untracked files present (use "git add" to track)

$ git switch feature/git-practice
Switched to branch 'feature/git-practice'

$ git switch main
Switched to branch 'main'
Your branch is up to date with 'main'.

$ git merge feature/git-practice
Updating bfb8728..ff6c94e
Fast-forward
 git-practice/git-practice.md | 7 +++++++
 1 file changed, 7 insertions(+)
 create mode 100644 git-practice/git-practice.md
# Nội dung được tạo trên feature branch.

$ git stash
Saved working directory and index state WIP on main: ff6c94e add branch practice

$ git stash pop
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   git-practice.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (3a36cf71dd799ca14efad57754aedc0c9ada256b)

$ git commit -m "Add amend practce"
[main 2c04ea0] Add amend practce
 1 file changed, 9 insertions(+), 1 deletion(-)

$ git commit --amend -m "Add amend practice"
[main 28392f9] Add amend practice
 Date: Tue Sep 15 13:50:52 2026 +0700
 1 file changed, 9 insertions(+), 1 deletion(-)

$ git log --oneline
28392f9 (HEAD -> main) Add amend practice
ff6c94e (feature/git-practice) add branch practice
bfb8728 (origin/main, origin/HEAD) fix
82fab61 weekly-reports
e0933e2 Remove duplicate day 01 file
9c3e4a7 Add initial content for Day 01, covering Git commands, TypeScript concepts, and ESLint usage
18f0d12 Update config my own repo
67a320a Updaload test
b6247e3 Properly add hugo-theme-learn as git submodule
1060471 Update baseURL to match LAZTAR-PEEP repo name
aae8a18 first commit

$ git switch -c cherry-pick-demo
Switched to a new branch 'cherry-pick-demo'

$ git cherry-pick b2acd16
[main 290f733] Add cherry-pick practice
 Date: Tue Sep 15 13:55:36 2026 +0700
 1 file changed, 5 insertions(+), 1 deletion(-)

$ git merge conflict-demo
Auto-merging git-practice/git-practice.md
CONFLICT (content): Merge conflict in git-practice/git-practice.md
Automatic merge failed; fix conflicts and then commit the result.

$ git reset --soft HEAD~1

$ git branch
* main

$ git fetch

$ git pull
Already up to date.

$ git remote
origin
```

## Khó khăn gặp phải

- Cần làm quen với Front Matter của Hugo.
- Một số thay đổi cần kiểm tra lại trên môi trường local.

## Kế hoạch ngày tiếp theo

- Tiếp tục hoàn thiện weekly report.
- Tìm hiểu cách tùy chỉnh giao diện.
- Kiểm tra responsive và navigation của website.