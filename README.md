# 🎮 Chơi cờ caro cùng PoPi — V1.3

Web game cờ caro miễn phí, dành cho trẻ từ **6–10 tuổi**, chạy trên trình duyệt máy tính, điện thoại và iPad. Là một trò chơi thuộc hệ sinh thái **PoPi Smart Kids**.

## ✅ Cập nhật V1.3

- Sửa lỗi Safari/iPadOS làm quân **X/O lệch tâm** bằng lớp ký hiệu định vị tuyệt đối chính giữa ô, không phụ thuộc cách iPad render nút HTML.
- Thêm chuyển đổi **Tiếng Việt (VI) / English (EN)** cho toàn bộ giao diện, thông báo kết quả, hướng dẫn và nhãn hỗ trợ tiếp cận; ghi nhớ ngôn ngữ trên trình duyệt.
- Logo ở header được nhúng trực tiếp để không hiện biểu tượng ảnh bị lỗi khi thư mục `assets` thiếu hoặc CDN chậm. Các tệp icon độc lập vẫn nằm trong `assets/icons/`.
- Thương hiệu **PoPi Smart Kids**, font dùng hệ thống phổ biến, tránh lỗi dấu tiếng Việt.
- Giữ nguyên AI, luật chơi, nút điều khiển và thành tích đã lưu từ V1.2.

## 🎯 Tính năng

- Chơi với **PoPi** (máy) theo 3 độ khó: Dễ, Vừa, Khó.
- Hai người chơi cùng nhau trên một thiết bị.
- **10×10 / nối 4** (mới chơi), **15×15 / nối 5** (nâng cao).
- Gợi ý nước đi, đi lại, tạo ván mới, bật/tắt âm thanh.
- Bàn cờ 15×15 có chế độ phóng to để thao tác dễ hơn trên điện thoại.
- Lưu tiến trình và thành tích tại trình duyệt với `localStorage`.
- Không yêu cầu đăng nhập, không quảng cáo, không cần dịch vụ AI trả phí.

**Luật đơn giản:** Người chơi X đi trước, O đi sau; ai nối đủ quân thành một hàng ngang/dọc/chéo thắng. Không áp dụng luật chặn hai đầu.

## 📁 Cấu trúc mã nguồn

```text
/
├── index.html                 # Toàn bộ giao diện và logic game
├── manifest.webmanifest       # Cấu hình shortcut/web app
├── favicon.ico                # Favicon trình duyệt
├── .nojekyll                  # GitHub Pages phục vụ tệp tĩnh trực tiếp
├── README.md
├── LOGO_CONCEPT.md
└── assets/
    └── icons/
        ├── apple-touch-icon.png
        ├── icon-192.png
        ├── icon-512.png
        ├── favicon-16x16.png
        ├── favicon-32x32.png
        └── popi-caro-icon-master.png
```

## 🚀 Đưa lên GitHub Pages

1. Tạo GitHub repository, ví dụ `popikidgames-caro`, chọn **Public**.
2. **Giải nén file ZIP** này, sau đó upload **toàn bộ file và thư mục bên trong** vào thư mục gốc (root) của repository. Không upload nguyên ZIP làm website; không đặt thêm một tầng thư mục bao ngoài `index.html`.
3. Vào **Settings → Pages → Build and deployment → Deploy from a branch**.
4. Chọn branch **main** và thư mục **/(root)**, sau đó chọn **Save**.
5. Chờ GitHub Pages phát hành website, sau đó truy cập liên kết được GitHub hiển thị trong trang Pages. Ví dụ theo cấu trúc: `https://<username>.github.io/popikidgames-caro/`.

Giữ nguyên đường dẫn `assets/icons/` và `manifest.webmanifest` để icon hoạt động.

## 📲 Thêm shortcut lên iPad/iPhone

1. Mở link **GitHub Pages** hoặc trang game tại **popikidgames.com** bằng **Safari**.
2. Chọn **Chia sẻ (Share)** → **Thêm vào Màn hình chính (Add to Home Screen)**.
3. Kiểm tra tên **PoPi Caro**, nhấn **Thêm**.

Shortcut sẽ sử dụng icon `apple-touch-icon.png` (180×180). Trên các trình duyệt hỗ trợ manifest, `manifest.webmanifest` khai báo thêm icon 192×192 và 512×512 cùng chế độ hiển thị standalone.

> **Lưu ý:** Shortcut **không đồng nghĩa với khả năng chơi offline**. Bản này chưa có service worker lưu cache ngoại tuyến; cần internet khi tải game từ GitHub Pages.

## 🧰 Sửa và chạy thử

Game viết bằng HTML/CSS/JavaScript thuần, không cần build hoặc thư viện ngoài. Mở `index.html` trên máy tính để chơi ngay. Để kiểm tra icon và manifest đúng như môi trường web, nên chạy server cục bộ:

```bash
python -m http.server 8000
```

Sau đó truy cập `http://localhost:8000`.

## 🎨 Logo

Logo gồm nhân vật PoPi vui nhộn, bàn cờ và các quân X/O. File gốc ở `assets/icons/popi-caro-icon-master.png`. Các biến thể favicon, Apple và Android/web được xuất sẵn. Xem `LOGO_CONCEPT.md` để biết định hướng nhận diện.

## ♻️ Cập nhật repository đang chạy

1. Giải nén ZIP. Trên GitHub chọn **Add file → Upload files** hoặc dùng Git để thay toàn bộ file cũ; quan trọng nhất là `index.html`, `manifest.webmanifest`, `favicon.ico` và **toàn bộ thư mục `assets/icons/`**.
2. Nếu thấy logo cũ, kiểm tra thư mục `assets/icons` có đúng tên chữ thường và các ảnh PNG thực sự có mặt trên nhánh `main`.
3. Chờ GitHub Pages hoàn tất triển khai và tải lại trang bằng **Ctrl+Shift+R** hoặc đóng mở lại Safari. Với shortcut iPad, đôi khi cần xóa shortcut cũ và **Add to Home Screen** lại để icon mới có hiệu lực.
4. Không đổi địa chỉ repo hoặc đường dẫn trang, dữ liệu tiến trình và điểm số được giữ trên cùng trình duyệt nếu localStorage chưa bị xóa.

**Kiểm thử:** Bản này được kiểm tra bằng Chromium mô phỏng kích thước iPad và desktop; vẫn nên thử thực tế trên Safari iPadOS của anh vì đây là lỗi phụ thuộc thiết bị.
