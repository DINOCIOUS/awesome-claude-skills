# Bộ skill của Ming (project skills)

Thư mục này chứa các skill Ming chọn, để Claude Code tự nạp khi làm việc trong repo này.
Ghi chú: các skill là **bản sao**, không phải liên kết. Nếu sửa bản gốc ở thư mục gốc của repo thì cần chép lại sang đây.

| Skill | Nguồn | Chi phí | Dùng cho |
|---|---|---|---|
| `content-research-writer` | Repo awesome (`./content-research-writer/`) | Miễn phí | Dàn ý, hook, trích dẫn, góp ý từng phần |
| `deep-research` | Skill đồng bộ trong tài khoản Ming (kiểu `anthropic-skills:deep-research`), chạy bằng nhiều agent con | Không tốn thêm ngoài gói Claude | Research nhiều nguồn, ra báo cáo có trích dẫn |
| `theme-factory` | Repo awesome | Miễn phí | Chọn và áp theme màu, font |
| `canvas-design` | Repo awesome | Miễn phí | Ảnh tĩnh: thumbnail, poster |
| `image-enhancer` | Repo awesome | Miễn phí | Nâng chất lượng ảnh |
| `artifacts-builder` | Repo awesome | Miễn phí | Trang HTML/React nhiều thành phần |
| `skill-creator` | Repo awesome | Miễn phí | Tạo skill mới |

## Không đưa vào (có chủ ý)
- `deep-research` của sanjay3290: cần GEMINI_API_KEY, tốn khoảng $2–5 mỗi lần chạy.
- Pixelbin, YouTube Automation (Composio): cần tài khoản trả phí.

## Lưu ý về giấy phép
- `theme-factory`, `canvas-design`, `artifacts-builder`, `skill-creator` kèm tệp `LICENSE.txt` của chính chúng.
- `deep-research` không có tệp giấy phép đi kèm trong bản đồng bộ. Ming xác nhận nguồn gốc và quyền chia sẻ trước khi để repo công khai.

## Phần còn thiếu cần bổ sung (theo kết quả test)
Xác nhận nội dung (cổng duyệt khẳng định, nguồn), storyboard chung, giọng đọc và phụ đề, SFX và nhạc nền, ghép và mix âm thanh, đóng gói YouTube. Xem `reports/skill-tests/`.
