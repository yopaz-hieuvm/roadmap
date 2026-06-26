Các câu git thường dùng
| Câu lệnh                   | Mục đích                                            |
| -------------------------- | --------------------------------------------------- |
| `git clone <url>`          | Clone project từ remote về máy.                     |
| `git status`               | Kiểm tra trạng thái file đã thay đổi.               |
| `git add .`                | Đưa tất cả file đã thay đổi vào staging.            |
| `git commit -m "message"`  | Tạo một commit với nội dung mô tả.                  |
| `git push origin <branch>` | Đẩy commit lên remote.                              |
| `git pull origin <branch>` | Lấy code mới và merge về branch hiện tại.           |
| `git fetch`                | Lấy thông tin mới từ remote nhưng chưa merge.       |
| `git checkout <branch>`    | Chuyển sang branch khác.                            |
| `git checkout -b <branch>` | Tạo và chuyển sang branch mới.                      |
| `git branch`               | Xem danh sách branch local.                         |
| `git merge <branch>`       | Gộp branch vào branch hiện tại.                     |
| `git rebase <branch>`      | Rebase branch hiện tại lên branch khác.             |
| `git stash`                | Lưu tạm thay đổi chưa commit.                       |
| `git stash pop`            | Lấy lại thay đổi đã stash.                          |
| `git reset --soft HEAD~1`  | Quay lại commit trước nhưng giữ code trong staging. |
| `git reset --hard HEAD~1`  | Quay lại commit trước và xóa luôn thay đổi.         |
| `git revert <commit>`  | hoàn tác một commit đã được tạo, nhưng không xóa lịch sử Git.         |
| `git cherry-pick <commit>`  | lấy commit từ branch khác để áp dụng vào branch hiện tại       |

