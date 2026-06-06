# Git Workflow - Group 02

## Branch Structure

| Member      | Branch       |
| ----------- | ------------ |
| Thanh Thanh | `ThanhThanh` |
| Hồng Hạnh   | `HongHanh`   |
| Hoàng Đức   | `HoangDuc`   |
| Trung Nhân  | `TrungNhan`  |
| Bảo Vy      | `BaoVy`      |

> Không code trực tiếp trên `master`.

---

## 1. Clone Repository

```bash
git clone https://github.com/honghanh1431/MOBILE-COMMERCE-DEVELOPMENT---253EIE502802---GROUP-02.git
cd MOBILE-COMMERCE-DEVELOPMENT---253EIE502802---GROUP-02
```

---

## 2. Cập nhật code mới nhất từ master

```bash
git checkout master
git pull origin master
```

---

## 3. Chuyển sang branch cá nhân

### Bảo Vy

```bash
git checkout BaoVy
```

### Trung Nhân

```bash
git checkout TrungNhan
```

### Hoàng Đức

```bash
git checkout HoangDuc
```

### Hồng Hạnh

```bash
git checkout HongHanh
```

### Thanh Thanh

```bash
git checkout ThanhThanh
```

---

## 4. Sau khi code xong

### Kiểm tra thay đổi

```bash
git status
```

### Add file

```bash
git add .
```

### Commit

```bash
git commit -m "Mô tả thay đổi"
```

Ví dụ:

```bash
git commit -m "Add product detail screen"
```

### Push lên branch cá nhân

Ví dụ với branch BaoVy:

```bash
git push origin BaoVy
```

Ví dụ với branch TrungNhan:

```bash
git push origin TrungNhan
```

---

## 5. Đồng bộ branch với master

Trước khi bắt đầu code mỗi ngày:

```bash
git checkout master
git pull origin master

git checkout <your-branch>
git merge master
```

Ví dụ:

```bash
git checkout BaoVy
git merge master
```

Nếu có conflict thì xử lý conflict trước khi push.

---

## 6. Merge vào master

Chỉ Leader hoặc người được phân công mới merge vào `master`.

Quy trình:

```bash
git checkout master
git pull origin master
git merge <branch-name>
git push origin master
```

Ví dụ:

```bash
git checkout master
git merge BaoVy
git push origin master
```

---

## Quick Workflow

```bash
git checkout master
git pull origin master

git checkout BaoVy

# Code...

git add .
git commit -m "Update feature"
git push origin BaoVy
```

## Rules

✅ Luôn làm việc trên branch cá nhân

✅ Pull `master` trước khi code

✅ Commit message rõ ràng

✅ Push lên branch cá nhân

❌ Không push trực tiếp lên `master`

❌ Không code trên `master`
