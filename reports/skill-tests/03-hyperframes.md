# Test: thiết kế cảnh video bằng HyperFrames

Câu hỏi của Ming: "design bằng HyperFrames thì sao" (thay cho `canvas-design` cho bước tạo ảnh và chuyển động).

**HyperFrames** là khung mã nguồn mở của HeyGen: viết cảnh bằng HTML, CSS và GSAP, rồi render ra MP4. Nó không nằm trong bộ awesome và không phải skill của Ming. Đây là một ứng viên để bổ sung vào quy trình.

## Đã kiểm chứng
- Giấy phép Apache 2.0, không tính phí mỗi lần render ([nguồn](https://www.noqta.tn/en/blog/heygen-hyperframes-html-to-mp4-ai-agent-video-2026)).
- Gói npm `hyperframes` bản 0.8.139, giấy phép Apache-2.0 (kiểm tra trực tiếp bằng `npm view`).
- Yêu cầu: Node 22 trở lên và ffmpeg ([nguồn](https://github.com/heygen-com/hyperframes)). Môi trường này đã có.

## Em đã làm gì
1. Cài và chạy `hyperframes doctor`. Tắt telemetry ẩn danh (`hyperframes telemetry disable`).
2. Tải Chrome Headless Shell (khoảng 114 MB) bằng `hyperframes browser ensure`.
3. Tạo dự án trống, dựng **một video 15 giây, 1080p, 30 fps** gồm ba cảnh theme Tech Innovation (tiêu đề với hook, số lớn $6.53, định nghĩa crack spread kèm cột biểu đồ chuyển động).
4. Chạy `check` (kiểm tra lỗi, bố cục, tương phản), sửa lỗi, render ra MP4.

Kết quả: `diesel-scenes-tech-innovation.mp4`, 15.0 giây, 1920×1080, H.264, khoảng 2 MB, **render mất khoảng 26 giây**. Mã nguồn dự án nằm ở `diesel-video/`.

## Phát hiện

### Điểm mạnh
1. **Có chuyển động thật:** GSAP làm xuất hiện, trượt, mở rộng thanh, cột biểu đồ mọc lên. `canvas-design` chỉ ra ảnh tĩnh.
2. **Bộ kiểm tra tích hợp (`check`) rất hữu ích:**
   - Bắt lỗi chữ tràn khung: dòng tiêu đề font DejaVu 112 px tràn 262 px ra ngoài khung 1920 px, công cụ nêu rõ cỡ chữ nên giảm. Em cần hai vòng sửa (112 → 100 → 90 px) mới hết lỗi.
   - Kiểm tra độ tương phản WCAG AA tự động, 33/33 chữ đạt. Điều này khớp với kết luận của test 2.
3. **Kết quả lặp lại được:** cùng đầu vào cho ra cùng video, hợp để chạy tự động.
4. **Theme chuyển được nguyên vẹn:** các mã màu của Tech Innovation đưa vào CSS qua biến `--bg`, `--cyan`, `--blue`, `--white`. Đổi theme chỉ cần đổi các biến này.
5. **Có công cụ cục bộ cho các khâu còn thiếu** (em chưa chạy thử, cần cài thêm thư viện và tải mô hình):
   - `hyperframes tts`: giọng đọc bằng mô hình cục bộ Kokoro-82M, giấy phép Apache-2.0 theo kết quả tìm kiếm ([nguồn](https://elevenlabsmagazine.com/kokoro-82m-ai-voice-model-guide-2026/)).
   - `hyperframes transcribe`: tạo phụ đề có mốc thời gian từng từ.
   - `hyperframes remove-background`: tách nền.
   - Nhạc nền bằng MusicGen cục bộ. **Cảnh báo:** trọng số MusicGen theo giấy phép CC-BY-NC 4.0, tức không dùng cho mục đích thương mại, nên **không dùng cho kênh bật kiếm tiền** ([nguồn](https://huggingface.co/spaces/facebook/MusicGen/discussions/8)).
6. **Có bộ skill riêng cho trợ lý AI** (`/hyperframes`, `/faceless-explainer`, `/motion-graphics`, `/general-video`...), cài bằng `npx hyperframes skills update`. Em **chưa cài** vì chưa cần cho test này.

### Điểm yếu và lưu ý
1. **Font mặc định bị thay:** khi để `font-family: "DejaVu Sans"`, HyperFrames tự tải font Inter từ Google Fonts và dùng nó, nên video không đúng font của theme. Muốn đúng font phải nhúng tệp font cục bộ bằng `@font-face`. Em đã làm và xác nhận khớp.
2. **Thư viện GSAP tải từ CDN bị chặn** trong môi trường này (`ERR_TUNNEL_CONNECTION_FAILED`). Em tải GSAP về `assets/gsap.min.js` và dùng bản cục bộ. Với dự án thật, nên luôn lưu cục bộ.
3. **Cảnh báo cấu trúc:** công cụ khuyên mỗi cảnh nên là một tệp con (sub-composition, thuộc tính `data-composition-src`). Với video 13–14 phút nhiều cảnh, đây là cách tổ chức đúng. Test này gộp một tệp để đơn giản, nên còn 3 cảnh báo (không phải lỗi).
4. **Hạn chế animation:** GSAP chỉ hỗ trợ `set, to, from, fromTo` và một số thuộc tính (opacity, x, y, scale, width, height, rotation...). Hiệu ứng "đếm số tăng dần" cần cách làm khác, em chưa thử.
5. **Chất lượng cuối:** tài liệu nói render cục bộ có thể khác giữa các máy (font, bản Chrome); muốn chuẩn sản xuất cần Docker (môi trường này không chạy được Docker).
6. **Có tuỳ chọn render trên đám mây của HeyGen** (`hyperframes cloud`) và đăng nhập tài khoản HeyGen. Em không dùng, vì Ming không muốn dịch vụ mất phí.
7. **Cần tải nhiều thứ:** Chrome khoảng 114 MB, các gói npm. Mỗi môi trường mới đều phải cài lại.
8. **Dự án sinh ra có file `CLAUDE.md` và `AGENTS.md`** hướng dẫn trợ lý AI, đây là nội dung của HyperFrames, em không sửa.

## So sánh với `canvas-design`

| Tiêu chí | `canvas-design` | HyperFrames |
|---|---|---|
| Đầu ra | PNG, PDF tĩnh | MP4 có chuyển động (cũng xuất được WebM trong suốt) |
| Chuyển động | Không | Có (GSAP) |
| Kiểm tra lỗi bố cục, tương phản | Không | Có, tự động |
| Chữ tiếng Việt | Cần kiểm tra font đi kèm | Đã thử dấu tiếng Việt, hiển thị tốt khi nhúng font |
| Phong cách | Triết lý thẩm mỹ, tự do sáng tạo, 90% hình ảnh | Do mình thiết kế bằng HTML/CSS, bám theme |
| Chi phí | Miễn phí | Miễn phí (Apache 2.0) |
| Phù hợp nhất | Thumbnail, poster nghệ thuật | Cảnh video, biểu đồ chuyển động, ghép toàn bộ video |

## Kết luận
- **HyperFrames phù hợp hơn `canvas-design` cho phần thiết kế và chuyển động của video**, vì nó phủ luôn bước "tạo ảnh, tạo chuyển động, tạo video" trong quy trình của Ming, miễn phí, kèm kiểm tra tự động.
- **`canvas-design` vẫn hữu ích cho thumbnail** (ảnh tĩnh nghệ thuật). Test 3 của skill này có thể dành cho thumbnail.
- Phần còn thiếu: giọng đọc, SFX, nhạc nền, ghép âm thanh vào video. Giọng đọc cục bộ Kokoro (Apache-2.0) là ứng viên cần test riêng. Nhạc nền cần nguồn khác MusicGen.

## Việc tiếp theo (chờ Ming)
- [ ] Ming xem video mẫu và các khung hình.
- [ ] Quyết định dùng HyperFrames cho bước chuyển động và dựng video.
- [ ] Test giọng đọc cục bộ (Kokoro) với đoạn hook?
- [ ] Làm storyboard cho kịch bản 13–14 phút trước khi dựng toàn bộ?
