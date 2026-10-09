# WYL (What You Love) — Mini Retro Pixel Music Player

Trình phát nhạc desktop siêu tối giản phong cách Flat Retro Pixel cổ điển, hỗ trợ tìm kiếm và stream nhạc trực tiếp từ YouTube & SoundCloud không cần tải file về máy.

---

## ✨ Điểm nổi bật & Triết lý thiết kế

1. **Thiết kế Flat Retro Pixel (Anti-AI Design)**:
   - Tối giản tối đa: Vuông vức, phẳng hoàn toàn, không bo góc (zero border-radius), không viền mờ neon, không glassmorphism.
   - Bảng màu vintage hoài cổ: Nền be ấm (`#F4EEDD`), màn hình LCD kem (`#FFFDF8`), điểm nhấn cam retro (`#FF7A29`), viền mực đen than (`#202020`).
   - Hiệu ứng màn hình LCD hoài cổ: Chữ chạy Marquee mượt mà, biểu đồ sóng âm ASCII VU Meter động (` ▂▃▅`).

2. **Siêu nhẹ & Zero Phụ thuộc (Zero-Dependency Standalone)**:
   - File chạy độc lập `WYL.exe` chỉ **~72.8 MB** (đã tối ưu cắt giảm hơn 52% từ 153MB).
   - Tích hợp sẵn Python runtime, PySide6 và thư viện LibVLC Audio tối giản.
   - **Máy người dùng mới cài lại Windows, không cần cài Python, không cần cài Node.js, không cần cài VLC vẫn nhấp đúp là nghe nhạc ngay.**

3. **Chất lượng âm thanh tùy biến (Audio Quality Selector)**:
   - Nút `Q:xxxk` trên thanh tiêu đề hỗ trợ chuyển nhanh giữa 5 mức xử lý âm học:
     - `64k`: Nén tối đa, tiết kiệm băng thông cho mạng yếu.
     - `96k`: Nén nhẹ, chế độ tiết kiệm (Eco Mode).
     - `128k`: Chuẩn gốc (Flat Sound).
     - `256k`: Bù dải âm Hi-Fi (Boost dải trầm Bass & dải Treble).
     - `512k`: Bù tối đa (Studio Master Harmonic Expansion).

4. **Quản lý Playlist hoàn chỉnh**:
   - **Tạo Playlist**: Nút `[+ PL]` tạo playlist cá nhân mới (lưu cục bộ vĩnh viễn).
   - **Xóa Playlist**: Nút `[- PL]` xóa playlist đang chọn.
   - **Thêm bài**: Bấm nút `[+ VÀO PLAYLIST]` hoặc nhấp **chuột phải** vào bài $\to$ `+ Thêm vào Playlist...`.
   - **Xóa bài**: Bấm nút `[- XÓA BÀI]`, phím `Delete` / `Backspace` hoặc chuột phải $\to$ `- Xóa khỏi danh sách này`.

5. **Tốc độ cao & Ổn định tuyệt đối**:
   - Bắt đầu phát luồng audio chỉ sau ~1.6 giây.
   - Tự động nạp trước (prefetch) bài kế tiếp dưới nền giúp chuyển bài không độ trễ.
   - Xử lý mượt các bài thời lượng siêu dài (1 giờ+) mà không bị treo hay tự tắt ứng dụng.

---

## 🚀 Hướng dẫn khởi chạy & Cài đặt

### Cách 1: Chạy file `.exe` độc lập (Khuyên dùng cho người dùng cuối)
1. Tải file `dist\WYL.exe` (72.8 MB).
2. Nhấp đúp chuột vào file để mở và thưởng thức âm nhạc. Không cần cài đặt bất kỳ môi trường hay phần mềm nào khác.

### Cách 2: Chạy trực tiếp từ mã nguồn Python
Yêu cầu máy có Python 3.11+ và VLC desktop:
```powershell
# Chạy script tự động thiết lập venv và mở player:
.\run_pixel.ps1

# Hoặc khởi chạy thủ công bằng python:
.\.venv\Scripts\python.exe pixel_player.py
```

### Cách 3: Tự đóng gói thành file `.exe`
```powershell
powershell -ExecutionPolicy Bypass -File .\build_pixel_exe.ps1
```
File thực thi độc lập sẽ được tạo tại: `dist\WYL.exe`.

---

## ⌨️ Phím tắt & Thao tác nhanh

| Thao tác / Phím tắt | Chức năng |
|---|---|
| `Space` | Tạm dừng (Pause) / Tiếp tục phát (Play) |
| `Mũi tên Trái / Phải` | Giảm / Tăng âm lượng (-5% / +5%) |
| `Phím Delete / Backspace` | Xóa bài đang chọn khỏi playlist |
| `Kéo thả thanh tiêu đề` | Di chuyển cửa sổ tự do trên màn hình |
| `Nút PIN` | Ghim cửa sổ luôn nổi trên cùng khi làm việc |
| `Nút Q:xxxk` | Đổi mức chất lượng âm thanh / bù dải tần |
| `Nút ▼ DS / ▲ GỌN` | Đóng / Mở khay tìm kiếm và danh sách playlist |
| `Chuột phải lên bài hát` | Mở menu ngữ cảnh: Phát, Thêm vào playlist, Xóa |

---

## 📂 Dữ liệu lưu trữ
Toàn bộ danh sách bài hát gần đây và các playlist cá nhân được lưu tự động tại:
`%LOCALAPPDATA%\PulseMusic\library.json`
