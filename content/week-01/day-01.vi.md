---
title: "Ngày 01 - 15/09/2026 (Tại văn phòng)"
weight: 1
---

## Công việc đã làm

- Tìm hiểu cấu trúc thư mục content của Hugo.
- Thực hành tạo và chỉnh sửa file Markdown.
- Tìm hiểu cách sử dụng theme hugo-theme-learn.
- Kiểm tra website sau khi thay đổi nội dung.

## Ví dụ thực hành Git

### Các lệnh thông dụng

| Lệnh | Ý nghĩa |
| --- | --- |
| `git init` | Khởi tạo một repository Git mới |
| `git remote` | Quản lý kết nối đến repository từ xa |
| `git clone` | Sao chép repository từ xa về máy |
| `git fetch` | Tải về thay đổi từ remote nhưng chưa merge |
| `git pull` | Tải về và merge thay đổi từ remote |
| `git status` | Xem trạng thái hiện tại của repository |
| `git branch` | Liệt kê, tạo hoặc xoá nhánh |
| `git switch` | Chuyển sang nhánh khác |
| `git checkout` | Chuyển nhánh hoặc khôi phục file |
| `git add` | Đưa thay đổi vào staging area |
| `git commit` | Lưu thay đổi đã stage vào lịch sử repository |
| `git commit --amend` | Cập nhật lại commit gần nhất |
| `git push` | Đẩy commit local lên repository từ xa |
| `git reset` | Bỏ stage hoặc di chuyển lịch sử commit |
| `git rebase` | Áp dụng lại các commit lên đầu nhánh khác |
| `git rebase -i` | Chỉnh sửa, gộp hoặc sắp xếp lại commit |
| `git stash` | Cất tạm thay đổi chưa commit |
| `git stash pop` | Lấy lại thay đổi đã cất gần nhất |
| `git merge` | Gộp thay đổi từ nhánh khác vào nhánh hiện tại |
| `git cherry-pick` | Áp dụng một commit cụ thể vào nhánh hiện tại |

### Xử lý xung đột (Merge Conflict)

| Tình huống | Cách xử lý trong Source Control |
| --- | --- |
| Giữ thay đổi của cả hai nhánh | Mở file, sửa thủ công phần xung đột, rồi đánh dấu đã giải quyết |
| Giữ phiên bản của nhánh hiện tại | Chọn Accept Current Change trong trình chỉnh sửa conflict |
| Giữ phiên bản của nhánh được merge vào | Chọn Accept Incoming Change trong trình chỉnh sửa conflict |
| Huỷ bỏ quá trình merge | Vào Source Control, chọn menu `...`, sau đó chọn Abort Merge |
| Tự giải quyết thủ công | Xem từng khối conflict được đánh dấu và giữ lại đoạn code đúng |

### Ví dụ từng lệnh

#### git init

#### git remote

![git remote](/images/git-practice/19-git-remote.png)

#### git clone

#### git fetch

![git fetch](/images/git-practice/17-git-fetch.png)

#### git pull

![git pull](/images/git-practice/18-git-pull.png)

#### git status

![git status](/images/git-practice/01-git-status.png)

#### git branch

![git branch](/images/git-practice/04-git-branch.png)

#### git switch

![git switch feature](/images/git-practice/05-git-switch-feature.png)

![git switch main](/images/git-practice/06-git-switch-main.png)

![git switch -c](/images/git-practice/13-git-switch-c.png)

#### git checkout

#### git add

![git add](/images/git-practice/02-git-add.png)

#### git commit

![git commit](/images/git-practice/03-git-commit.png)

![git commit typo](/images/git-practice/10-git-commit-typo.png)

#### git commit --amend

![git commit --amend](/images/git-practice/11-git-commit-amend.png)

#### git log

![git log --oneline](/images/git-practice/12-git-log-oneline.png)

#### git push

#### git reset

![git reset --soft](/images/git-practice/16-git-reset-soft.png)

#### git rebase

#### git rebase -i

#### git stash

![git stash](/images/git-practice/08-git-stash.png)

#### git stash pop

![git stash pop](/images/git-practice/09-git-stash-pop.png)

#### git merge

![git merge fast-forward](/images/git-practice/07-git-merge-ff.png)

![git merge conflict](/images/git-practice/15-git-merge-conflict.png)

#### git cherry-pick

![git cherry-pick](/images/git-practice/14-git-cherry-pick.png)

## Khó khăn gặp phải

- Cần làm quen với Front Matter của Hugo.
- Một số thay đổi cần kiểm tra lại trên môi trường local.

## Kế hoạch ngày tiếp theo

- Tiếp tục hoàn thiện weekly report.
- Tìm hiểu cách tùy chỉnh giao diện.
- Kiểm tra responsive và navigation của website.