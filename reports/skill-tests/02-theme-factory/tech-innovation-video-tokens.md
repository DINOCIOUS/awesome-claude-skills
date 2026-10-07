# Theme đã chọn: Tech Innovation (áp cho video diesel, 1920×1080)

Nguồn: `theme-factory/themes/tech-innovation.md`. Phần "quy tắc dùng" là em bổ sung sau khi đo độ tương phản, vì skill không có hướng dẫn riêng cho video.

## Màu

| Vai trò | Tên | Mã | Dùng cho |
|---|---|---|---|
| Nền | Dark Gray | `#1e1e1e` | Nền mọi cảnh |
| Chữ chính | White | `#ffffff` | Tiêu đề, số lớn, chữ nội dung |
| Nhấn mạnh | Neon Cyan | `#00ffff` | Phụ đề, tên mục, một con số hoặc một cột cần nhấn |
| Nhấn hình khối | Electric Blue | `#0066ff` | Thanh dọc bên trái, đường gạch, cột biểu đồ |

## Độ tương phản trên nền `#1e1e1e` (WCAG)

| Màu | Tỉ lệ | Chữ lớn (cần từ 3) | Chữ nhỏ (cần từ 4.5) |
|---|---|---|---|
| White | 16.7 | Đạt | Đạt |
| Neon Cyan | 13.3 | Đạt | Đạt |
| Electric Blue | **3.4** | Đạt, sát ngưỡng | **Không đạt** |

## Font
- Tiêu đề: DejaVu Sans Bold
- Nội dung: DejaVu Sans
- Hiển thị tiếng Việt có dấu tốt (đã kiểm tra).

## Quy tắc dùng cho video (em đề xuất, Ming duyệt)
1. **Electric Blue không dùng cho chữ nhỏ.** Chỉ dùng cho thanh, đường kẻ, cột biểu đồ, hình khối lớn.
2. **Neon Cyan dùng tiết kiệm:** mỗi cảnh một chỗ nhấn chính (một con số hoặc một cột). Dùng nhiều dễ mỏi mắt khi xem lâu.
3. Chữ tối thiểu khoảng 44 px ở 1920×1080 để đọc được trên điện thoại.
4. Lề trái 120 px, thanh xanh dọc 24 px ở mép trái, đồng nhất mọi cảnh.
5. Cảnh nháp luôn có dòng "DRAFT, số liệu ⚠ chưa kiểm chứng" ở chân. Xoá khi số liệu đã chốt.

## Ba cảnh mẫu đã dựng (`applied/`)
- `scene-01-title.png`: khung tiêu đề với hook.
- `scene-02-big-number.png`: số lớn $6.53.
- `scene-03-definition.png`: định nghĩa crack spread kèm cột so sánh.
Số liệu trong cảnh mẫu là số ⚠ chưa kiểm chứng.
