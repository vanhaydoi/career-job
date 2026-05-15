# cv-input — Nơi lưu CV cũ để convert

Thư mục này dùng để chứa CV cũ của bạn ở nhiều định dạng khác nhau. Hệ thống sẽ tự động convert sang markdown và lưu vào `converted/`.

## Cách dùng

### Bước 1: Bỏ CV cũ vào thư mục tương ứng

| Định dạng | Thư mục |
|-----------|---------|
| PDF | `pdf/` |
| Word (.docx) | `docx/` |
| Ảnh chụp (.png, .jpg) | `image/` |
| Text (.txt) | `text/` |
| LinkedIn URL | Không cần file — dán URL trực tiếp khi chạy convert |

### Bước 2: Chạy convert

```bash
# Trong Claude Code / OpenCode:
/career-ops convert

# Hoặc từ command line:
# (hệ thống sẽ tự detect file trong cv-input/)
```

### Bước 3: Xem kết quả

File `.md` đã convert sẽ được lưu trong `converted/`. Bạn có thể:
- Xem lại và chỉnh sửa nếu cần
- Dùng file này khi chạy wizard tạo CV mới (`/career-ops new-cv`) — hệ thống sẽ tự động đọc và điền sẵn thông tin

## Lưu ý

- File trong `cv-input/` thuộc **User Layer** — sẽ không bị hệ thống tự động cập nhật hay ghi đè
- Sau khi convert xong, bạn có thể xóa file gốc để tiết kiệm dung lượng
- File `.md` trong `converted/` có thể được dùng làm base cho wizard tạo CV mới

## Ví dụ

```
cv-input/
├── pdf/
│   └── my-old-cv.pdf          ← CV cũ dạng PDF
├── docx/
│   └── cv-tieng-viet.docx     ← CV cũ dạng Word
├── converted/
│   ├── my-old-cv.md           ← Kết quả convert từ PDF
│   └── cv-tieng-viet.md       ← Kết quả convert từ DOCX
└── README.md                  ← File này
```
