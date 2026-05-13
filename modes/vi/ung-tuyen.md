# Chế độ: ung-tuyen — Trợ lý nộp đơn trực tiếp

Chế độ tương tác khi ứng viên đang điền form ứng tuyển trên Chrome. Đọc nội dung trên màn hình, tải ngữ cảnh offer trước đó, và tạo câu trả lời cá nhân hóa cho từng câu hỏi trong form.

## Yêu cầu

- **Tốt nhất với Playwright hiển thị**: Ở chế độ hiển thị, ứng viên thấy trình duyệt và Claude có thể tương tác với trang.
- **Không Playwright**: ứng viên chia sẻ screenshot hoặc dán câu hỏi thủ công.

## Quy trình

```
1. PHÁT HIỆN  → Đọc Chrome tab đang hoạt (screenshot/URL/tiêu đề)
2. XÁC ĐỊNH   → Trích xuất công ty + vai trò từ trang
3. TÌM KIẾM   → So khớp với reports hiện có trong reports/
4. TẢI        → Đọc report đầy đủ + Phần G (nếu có)
5. SO SÁNH    → Vai trò trên màn hình có khớp với đã đánh giá không? Nếu thay đổi → thông báo
6. PHÂN TÍCH  → Xác định TẤT CẢ câu hỏi form nhìn thấy
7. TẠO        → Cho mỗi câu hỏi, tạo câu trả lời cá nhân hóa
8. TRÌNH BÀY  → Hiển thị câu trả lời định dạng sẵn để copy-paste
```

## Bước 1 — Phát hiện offer

**Với Playwright:** Chụp snapshot trang đang hoạt. Đọc tiêu đề, URL, và nội dung hiển thị.

**Không Playwright:** Yêu cầu ứng viên:
- Chia sẻ screenshot của form (Read tool đọc được hình ảnh)
- Hoặc dán câu hỏi form dạng văn bản
- Hoặc nói công ty + vai trò để tìm kiếm

## Bước 2 — Xác định và tìm ngữ cảnh

1. Trích xuất tên công ty và tiêu đề vai trò từ trang
2. Tìm trong `reports/` theo tên công ty (Grep không phân biệt hoa thường)
3. Nếu khớp → tải report đầy đủ
4. Nếu có Phần G → tải câu trả lời nháp trước đó làm cơ sở
5. Nếu KHÔNG khớp → thông báo và đề xuất chạy auto-pipeline nhanh

## Bước 3 — Phát hiện thay đổi trong vai trò

Nếu vai trò trên màn hình khác với đã đánh giá:
- **Thông báo cho ứng viên**: "Vai trò đã thay đổi từ [X] sang [Y]. Bạn muốn tôi đánh giá lại hay điều chỉnh câu trả lời cho title mới?"
- **Nếu điều chỉnh**: Chỉnh câu trả lời cho vai trò mới mà không đánh giá lại
- **Nếu đánh giá lại**: Thực hiện đánh giá A-F đầy đủ, cập nhật report, tạo lại Phần G
- **Cập nhật tracker**: Đổi title vai trò trong applications.md nếu cần

## Bước 4 — Phân tích câu hỏi form

Xác định TẤT CẢ câu hỏi nhìn thấy:
- Trường tự do (thư xin việc, lý do ứng tuyển, v.v.)
- Dropdown (nguồn biết tin, quyền làm việc, v.v.)
- Có/Không (chuyển chỗ, visa, v.v.)
- Trường lương (khoảng, kỳ vọng)
- Upload (CV, thư xin việc PDF)

Phân loại từng câu hỏi:
- **Đã trả lời trong Phần G** → điều chỉnh câu trả lời hiện có
- **Câu hỏi mới** → tạo câu trả lời từ report + cv.md

## Bước 5 — Tạo câu trả lời

Cho mỗi câu hỏi, tạo câu trả lời theo:

1. **Ngữ cảnh report**: Dùng proof points từ khối B, câu chuyện STAR từ khối F
2. **Phần G trước đó**: Nếu có câu trả lời nháp, dùng làm cơ sở và tinh chỉnh
3. **Giọng "Tôi chọn bạn"**: Cùng framework như auto-pipeline
4. **Tính cụ thể**: Tham chiếu điểm cụ thể từ JD đang hiển thị trên màn hình
5. **Proof point career-ops**: Bao gồm trong "Thông tin bổ sung" nếu có trường

**Định dạng đầu ra:**

```
## Câu trả lời cho [Công ty] — [Vai trò]

Dựa trên: Report #NNN | Điểm: X.X/5 | Archetype: [loại]

---

### 1. [Câu hỏi chính xác từ form]
> [Câu trả lời sẵn sàng copy-paste]

### 2. [Câu hỏi tiếp theo]
> [Câu trả lời]

...

---

Ghi chú:
- [Bất kỳ quan sát nào về vai trò, thay đổi, v.v.]
- [Gợi ý cá nhân hóa mà ứng viên nên xem lại]
```

## Bước 6 — Sau khi nộp (tuỳ chọn)

Nếu ứng viên xác nhận đã gửi đơn:
1. Cập nhật trạng thái trong `applications.md` từ "Evaluated" thành "Applied"
2. Cập nhật Phần G của report với câu trả lời cuối cùng
3. Gợi ý bước tiếp theo: `/career-ops contacto` cho LinkedIn outreach

## Xử lý cuộn trang

Nếu form có nhiều câu hỏi hơn những gì nhìn thấy:
- Yêu cầu ứng viên cuộn và chia sẻ screenshot khác
- Hoặc dán các câu hỏi còn lại
- Xử lý theo vòng lặp cho đến khi bao phủ toàn bộ form
