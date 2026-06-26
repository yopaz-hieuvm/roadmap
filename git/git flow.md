# Git Flow dự án HBS (Backend)

## 1. Tạo nhánh làm việc cho `stage`

### Cập nhật nhánh `stage` mới nhất

```bash
git checkout stage
git pull
```

### Tạo nhánh feature từ `stage`

```bash
git checkout -b feature/issue-{ma-issue}-{noi-dung}
```

### Đồng bộ submodule về đúng commit mà `stage` đang ghim

```bash
git submodule update --init --recursive
```

---

## 2. Thực hiện code và commit

- Code trên nhánh vừa tạo.
- Commit theo đúng scope công việc.
- **Không sửa `src/liberty-asp`** thì **không được để thay đổi gitlink submodule** ngoài ý muốn.

---

## 3. Trường hợp có sửa submodule `src/liberty-asp`

### Bước 1: Tạo nhánh trong submodule

```bash
cd src/liberty-asp

git checkout -b feature/issue-{ma-issue}-{noi-dung}
```

### Bước 2: Code, commit và push

```bash
git push origin feature/issue-{ma-issue}-{noi-dung}
```

### Bước 3: Tạo Pull Request

Tạo PR của nhánh submodule vào:

```text
develop-yopaz-refactor
```

### Bước 4: Cập nhật gitlink trong parent repo

Sau khi submodule đã được merge:

```bash
cd ../..

git add src/liberty-asp
git commit -m "feat: update liberty-asp submodule"
```

### Lưu ý

- Parent repo chỉ nên trỏ tới commit của submodule **đã tồn tại trên remote**.
- Không push parent repo nếu gitlink đang trỏ tới commit local chưa có trên GitHub.

---

## 4. Tạo Pull Request vào `stage`

### Push nhánh feature

```bash
git push origin feature/issue-{ma-issue}-{noi-dung}
```

### Tạo PR vào `stage`

**PR Title**

```text
[Feat][Stage][#{issue task}] Nội dung task
```

Ví dụ:

```text
[Feat][Stage][#1234] Validate required options khi update câu hỏi
```

---

## 5. Tạo nhánh tương ứng cho `develop-yopaz`

### Cập nhật nhánh

```bash
git checkout develop-yopaz
git pull
```

### Tạo nhánh mới

```bash
git checkout -b feature/issue-{ma-issue}-{noi-dung}-dev
```

### Cherry-pick các commit nghiệp vụ từ nhánh `stage`

```bash
git cherry-pick <commit-1> <commit-2> ...
```

---

## 6. Nếu có update submodule cho nhánh `develop-yopaz`

Đảm bảo submodule đang ở commit đã được merge trên nhánh `develop-yopaz-refactor`.

### Cập nhật submodule

```bash
cd src/liberty-asp

git checkout develop-yopaz-refactor
git pull

cd ../..
```

### Cập nhật gitlink trong parent repo

```bash
git add src/liberty-asp
git commit -m "feat: update liberty-asp submodule for develop-yopaz"
```

### Push và tạo Pull Request

Push nhánh `-dev` và tạo PR vào:

```text
develop-yopaz
```

**PR Title**

```text
[Feat][Develop][#{issue task}] Nội dung task
```

Ví dụ:

```text
[Feat][Develop][#1234] Validate required options khi update câu hỏi
```
