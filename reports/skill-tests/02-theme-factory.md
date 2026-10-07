# Test 2: `theme-factory`

Chủ đề test: chọn theme cho video diesel (khung tiêu đề 16:9).

## Quy trình của skill (4 bước)
1. Hiện file `theme-showcase.pdf` (không sửa).
2. Hỏi người dùng chọn theme.
3. Chờ xác nhận rõ ràng.
4. Đọc file theme tương ứng trong `themes/` và áp màu, font.

Skill có cổng xác nhận rõ ràng ở bước 2–3, đúng kiểu "dừng lại chờ người dùng chọn". Đây là điểm tốt so với skill 1.

## Em đã làm gì
- Chuyển 10 trang PDF thành ảnh PNG (`02-theme-factory/themes/`).
- Làm thêm ảnh xem trước 16:9 cho cả 10 theme, áp màu và font thật của từng file theme lên khung tiêu đề video diesel, có kèm dòng tiếng Việt để thử dấu (`02-theme-factory/preview/`).

## Kết quả đo độ tương phản (WCAG; chữ lớn cần từ 3, chữ nhỏ cần từ 4.5)

| # | Theme | Tiêu đề / nền | Phụ đề / nền | Nhận xét |
|---|---|---|---|---|
| 1 | Ocean Depths | 14.8 | 10.3 | Rất tốt |
| 2 | Sunset Boulevard | 6.0 | 4.9 | Tốt |
| 3 | Forest Canopy | 9.4 | 4.2 | Chữ phụ nhỏ hơi yếu |
| 4 | Modern Minimalist | 9.9 | 6.6 | Tốt |
| 5 | Golden Hour | 5.0 | 5.3 | Tốt |
| 6 | Arctic Frost | 4.0 | 4.0 | **Yếu**, chữ nhỏ không đạt |
| 7 | Desert Rose | 7.6 | 7.6 | Tốt |
| 8 | Tech Innovation | 16.7 | 13.3 | Rất tốt |
| 9 | Botanical Garden | 4.4 | 4.8 | Chữ tiêu đề lớn đạt, sát ngưỡng |
| 10 | Midnight Galaxy | 12.6 | 5.4 | Tốt |

(Cách gán vai trò màu cho nền, tiêu đề, phụ đề là do em chọn từ mô tả trong từng file theme. Skill không quy định rõ.)

## Phát hiện về skill
1. **File showcase PDF không giúp chọn:** mỗi trang chỉ là bảng màu và mẫu chữ trên nền nhạt, không phải một cảnh thực tế. Trang Tech Innovation còn hiện chữ cyan trên nền trắng gần như không đọc được. Phải dựng ảnh xem trước riêng mới so sánh được.
2. **Lỗi đặt tên màu:** Sunset Boulevard gọi `#264653` là "Deep Purple", nhưng đó là màu xanh lục đậm (teal), không phải tím.
3. **Font:** toàn bộ dùng DejaVu và FreeSans, là font hệ thống có sẵn. Hiển thị tiếng Việt có dấu tốt (đã kiểm tra trên cả 10 ảnh), nhưng khá chung chung, không có nét riêng cho kênh.
4. **Skill chỉ nói về slide, tài liệu và trang HTML.** Không có hướng dẫn riêng cho video: tỉ lệ 16:9, vùng an toàn, cỡ chữ tối thiểu khi xem trên điện thoại.
5. **Có tính năng tạo theme riêng** (bước "Create your own theme"): chưa test vì chờ Ming chọn theme trước.

## Gợi ý chọn cho video diesel (Ming quyết định)
- **Ocean Depths (1):** chuyên nghiệp, tương phản rất cao, trầm tĩnh, hợp nội dung kinh tế và kỹ thuật.
- **Sunset Boulevard (2):** tông hổ phách trên nền xanh lục đậm, gợi năng lượng và dầu mỏ, có tính nhận diện hơn.
- **Tech Innovation (8):** tương phản cao nhất, hợp khán giả kỹ thuật, nhưng cyan neon dễ mỏi mắt khi xem lâu.

## Chờ Ming
- [ ] Chọn một theme (1–10), hoặc muốn em tạo theme riêng cho kênh.
