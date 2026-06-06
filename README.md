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

## Folder Structure

```
app/src/main/java/com.teatrack/
│
├── client/                          # Phần khách hàng
│   ├── auth/                        # Thanh Thanh
│   │   ├── LoginActivity
│   │   ├── RegisterActivity
│   │   ├── ForgotPasswordActivity
│   │   └── OtpActivity
│   ├── home/                        # Bảo Vy
│   │   ├── HomeActivity
│   │   └── MenuFragment
│   ├── product/                     # Bảo Vy
│   │   ├── ProductDetailActivity
│   │   └── CartActivity
│   ├── checkout/                    # Bảo Vy
│   │   ├── CheckoutActivity
│   │   └── PaymentActivity
│   ├── profile/                     # Thanh Thanh
│   │   ├── UserProfileActivity
│   │   └── OrderHistoryActivity
│   ├── tracking/                    # Thanh Thanh
│   │   └── OrderTrackingActivity
│   ├── content/                     # Hồng Hạnh
│   │   ├── AboutUsActivity
│   │   ├── AgencyActivity
│   │   ├── BlogGeneralActivity
│   │   ├── BlogDetailActivity
│   │   └── ContactUsActivity
│   └── error/                       # Hồng Hạnh
│       └── NotFoundActivity
│
├── admin/                           # Phần quản trị
│   ├── auth/                        # Hoàng Đức
│   │   └── AdminLoginActivity
│   ├── dashboard/                   # Hoàng Đức
│   │   └── AdminDashboardActivity
│   ├── account/                     # Hoàng Đức
│   │   ├── AdminAccountActivity
│   │   └── AdminProfileActivity
│   ├── product/                     # Hoàng Đức
│   │   ├── AdminProductActivity
│   │   └── OrdersActivity
│   ├── content/                     # Trung Nhân
│   │   ├── AgencyAdminActivity
│   │   ├── BlogAdminActivity
│   │   └── PromotionActivity
│   ├── support/                     # Trung Nhân
│   │   └── ContactComplaintsActivity
│   └── error/                       # Trung Nhân
│       └── Admin404Activity
│
└── shared/                          # Dùng chung cả 2 side
    ├── model/                       # User, Product, Order, Blog, Promotion...
    ├── api/                         # ApiService, RetrofitClient, ApiCallback
    ├── utils/                       # SessionManager, Constants, ImageUtils
    └── ui/                          # Hồng Hạnh
        ├── BaseActivity
        ├── HeaderFragment           # Header client/admin (before & after login)
        ├── FooterFragment
        └── ChatbotBubbleFragment

app/src/main/res/
├── drawable/
│   └── icons/                       # Icon SVG/PNG toàn app
├── layout/
│   ├── client/                      # File XML giao diện client
│   └── admin/                       # File XML giao diện admin
└── values/
    ├── colors_client.xml            # Theme màu client
    ├── colors_admin.xml             # Theme màu admin
    └── styles.xml
```

### Phân công theo folder

| Folder | Người phụ trách | Màn hình |
| --- | --- | --- |
| `client/auth/` | Thanh Thanh | Đăng nhập, Đăng ký, Forgot password, OTP |
| `client/profile/`, `client/tracking/` | Thanh Thanh | User profile, Order history, Order tracking, 404 client |
| `client/home/`, `client/product/`, `client/checkout/` | Bảo Vy | Homepage, Menu, Product detail, Cart, Checkout, Payment |
| `client/content/`, `client/error/`, `shared/ui/` | Hồng Hạnh | About us, Agency, Blog, Contact, Chatbot, Header, Footer, Email OTP |
| `admin/auth/`, `admin/dashboard/`, `admin/account/`, `admin/product/` | Hoàng Đức | Admin login, Dashboard, Account, Profile, Product, Orders |
| `admin/content/`, `admin/support/`, `admin/error/` | Trung Nhân | Agency admin, Blog admin, Contact/complaints, Promotion, Admin 404 |
| `shared/model/`, `shared/api/`, `shared/utils/` | Bảo Vy (lead) | — |

> **Lưu ý:** File XML layout đặt đúng subfolder (`layout/client/` hoặc `layout/admin/`) để tránh conflict khi merge.

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
