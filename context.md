# Project Context: Ứng Dụng Tách Nền, Thiết Kế Sticker & Xuất Vector Cutline (.AI)

## 1. Tổng quan dự án (Project Overview)
Ứng dụng chạy trực tiếp trên **Windows** (mở qua [index.html](file:///d:/App%20tách%20nền/index.html) hoặc [Chay_App_Tach_Nen.bat](file:///d:/App%20tách%20nền/Chay_App_Tach_Nen.bat)) với giao diện trực quan lấy cảm hứng từ **remove.bg**. Ứng dụng cho phép import một hoặc nhiều hình ảnh cùng lúc, tự động tách nền bằng AI **RMBG-1.4**, chỉnh sửa vùng chọn bằng cọ, thêm chữ thiết kế kết dính liền khối với viền trắng Sticker và tạo đường Vector bao quanh toàn bộ để xuất file **.AI / .SVG / .PNG** chất lượng gốc.

---

## 2. Các Tính Năng Chính Đã Triển Khai

### 2.1. Tự động tách nền & Điều chỉnh vùng chọn (Phần cắt)
- **Tự động tách nền AI (RMBG-1.4):** Tự động nhận diện vật thể chính và loại bỏ phông nền cũng như các chi tiết thừa nhỏ ở góc ảnh.
- **Điều chỉnh Thêm / Bớt vùng chọn bằng Cọ (Brush Mask Editor):**
  - **Bớt vùng chọn (Xóa):** Tô cọ vào vùng muốn xóa thêm.
  - **Thêm vùng chọn (Khôi phục):** Tô cọ vào vùng muốn lấy lại từ ảnh gốc (có chế độ *"Hiện mờ ảnh gốc"* để nhìn rõ phần cần khôi phục).
  - Hỗ trợ chỉnh **Cỡ cọ**, **Hoàn tác (`Ctrl + Z`)** và **Đặt lại AI**.

### 2.2. Thiết kế Thêm Chữ Kết Dính Liền Khối Sticker
- **Thêm chữ tùy chỉnh:**
  - Nhập nội dung chữ, chọn **Font chữ** (Baloo 2, Montserrat, Be Vietnam Pro, Pacifico, Playfair Display, Impact), **Cỡ chữ**, **Màu chữ**.
  - **Kéo thả trực tiếp trên hình** để thay đổi vị trí chữ hoặc kéo chấm tròn góc dưới phải của khung chữ để phóng to/thu nhỏ nhanh.
- **Bọc viền trắng dính liền (Unified Sticker Weld):**
  - Khi bật chế độ **Tạo Sticker (Viền trắng)**, phần viền trắng tự động bao bọc quanh cả **Hình ảnh vừa tách nền** lẫn **Phần chữ**, tự động hàn nối (weld) tạo thành **1 miếng Sticker liền khối duy nhất**.

### 2.3. Tab "Vector" (Dựa trực tiếp trên Viền Trắng Tạo Sticker)
- **Tab chức năng "Vector" ngang hàng với Phần cắt, Thiết kế, Tạo Sticker:**
  - Tự động nhận diện đường Vector khép kín dựa trực tiếp trên phần **viền trắng** đã tạo từ chức năng **"Tạo Sticker"** (sử dụng thuật toán loang nền ngoài + khử giao cắt 2x2 + làm mượt không co rút Taubin Smoothing + đường cong Bézier bậc 2 liền mạch).
  - Hỗ trợ đầy đủ 4 công cụ điều khiển trong tab **Vector**:
    1. **Điều chỉnh độ mượt (Smooth)** của đường Vector.
    2. **Điều chỉnh độ mở rộng (Offset)** của Vector so với mép viền trắng Sticker (`0px` bám sát mép viền trắng, `> 0px` mở rộng ra ngoài, `< 0px` thu vào trong).
    3. **Nút "Nhận diện lại Vector"** để làm mới lại đường Vector bất cứ lúc nào.
    4. **Điều chỉnh màu sắc của Vector** (các nút màu nhanh + bảng chọn màu tùy ý).
- **Xuất file chuyên nghiệp:**
  - **Xuất file `.SVG` đơn lẻ và hàng loạt (`.ZIP` hoặc từng file rời):** Chứa cả layer hình ảnh Sticker và layer đường cắt Vector `CutContour_Vector`.
  - **Xuất file `.PNG` & `.ZIP` hàng loạt:** Giữ nguyên chất lượng ảnh gốc.
