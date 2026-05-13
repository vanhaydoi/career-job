# Chế độ: pipeline — Hộp thư URL (Second Brain)

Xử lý các URL offer tích lũy trong `data/pipeline.md`. Người dùng thêm URL bất cứ lúc nào rồi chạy `/career-ops pipeline` để xử lý tất cả.

## Quy trình

1. **Đọc** `data/pipeline.md` → tìm mục `- [ ]` trong phần "Đang chờ"
2. **Cho mỗi URL đang chờ**:
   a. Tính số `REPORT_NUM` tiếp theo tuần tự (đọc `reports/`, lấy số cao nhất + 1)
   b. **Trích xuất JD** bằng Playwright (browser_navigate + browser_snapshot) → WebFetch → WebSearch
   c. Nếu URL không truy cập được → đánh dấu `- [!]` với ghi chú và tiếp tục
   d. **Thực hiện auto-pipeline đầy đủ**: Đánh giá A-F → Report .md → PDF (nếu điểm >= 3.0) → Tracker
   e. **Chuyển từ "Đang chờ" sang "Đã xử lý"**: `- [x] #NNN | URL | Công ty | Vai trò | Điểm/5 | PDF ✅/❌`
3. **Nếu có 3+ URL đang chờ**, chạy agents song song (Agent tool với `run_in_background`) để tối đa tốc độ.
4. **Khi hoàn thành**, hiển thị bảng tổng hợp:

```
| # | Công ty | Vai trò | Điểm | PDF | Hành động khuyến nghị |
```

## Định dạng pipeline.md

```markdown
## Đang chờ
- [ ] https://jobs.example.com/posting/123
- [ ] https://boards.greenhouse.io/company/jobs/456 | Company Inc | Senior PM
- [!] https://private.url/job — Lỗi: cần đăng nhập

## Đã xử lý
- [x] #143 | https://jobs.example.com/posting/789 | Acme Corp | AI PM | 4.2/5 | PDF ✅
- [x] #144 | https://boards.greenhouse.io/xyz/jobs/012 | BigCo | SA | 2.1/5 | PDF ❌
```

## Phát hiện JD thông minh từ URL

1. **Playwright (ưu tiên):** `browser_navigate` + `browser_snapshot`. Hoạt động với mọi SPA.
2. **WebFetch (fallback):** Cho trang tĩnh hoặc khi Playwright không khả dụng.
3. **WebSearch (phương án cuối):** Tìm trên các portal phụ có index JD.

**Trường hợp đặc biệt:**
- **LinkedIn**: Có thể cần đăng nhập → đánh dấu `[!]` và yêu cầu người dùng dán văn bản
- **PDF**: Nếu URL trỏ đến PDF, đọc trực tiếp bằng Read tool
- **Tiền tố `local:`**: Đọc file cục bộ. Ví dụ: `local:jds/linkedin-pm-ai.md` → đọc `jds/linkedin-pm-ai.md`
- **ITviec/VietnamWorks**: Các nền tảng tuyển dụng VN thường có JD mở, Playwright xử lý tốt

## Đánh số tự động

1. Liệt kê tất cả file trong `reports/`
2. Trích xuất số từ tiền tố (vd: `142-medispend...` → 142)
3. Số mới = số lớn nhất tìm thấy + 1

## Đồng bộ nguồn

Trước khi xử lý bất kỳ URL nào, kiểm tra đồng bộ:
```bash
node cv-sync-check.mjs
```
Nếu có mất đồng bộ, cảnh báo ứng viên trước khi tiếp tục.
