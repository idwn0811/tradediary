# TradeDiary – Nhật ký giao dịch XAUUSD

Trang tĩnh (index.html), chạy trên GitHub Pages. Dữ liệu lưu ở Firebase Firestore, đăng nhập Google để dùng trên nhiều thiết bị.

## 1. Firebase (làm 1 lần)
1. https://console.firebase.google.com → Add project.
2. Project settings → Your apps → Web (</>) → copy `firebaseConfig` dán vào `index.html` (đã điền sẵn cho project `tradediary-b88d4`).
3. Build → Authentication → Sign-in method → bật **Google**.
4. Authentication → Settings → Authorized domains → thêm `TEN-GITHUB.github.io`.
5. Build → Firestore Database → Create database → tab **Rules** → dán nội dung `firestore.rules` → Publish.

## 2. Đẩy lên GitHub
```
git init -b main
git add .
git commit -m "TradeDiary"
git remote add origin https://github.com/TEN-GITHUB/tradediary.git
git push -u origin main
```

## 3. Bật GitHub Pages
Repo → Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save.
Link dùng: `https://TEN-GITHUB.github.io/tradediary/`

Lưu ý: apiKey của Firebase web không phải bí mật, an toàn nằm ở Firestore Rules và Authorized domains.
Muốn chỉ riêng email của bạn được dùng, đổi điều kiện rule thành: `request.auth.token.email == 'email-cua-ban@gmail.com'`.
