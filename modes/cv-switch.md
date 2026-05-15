# Mode: cv-switch — Switch Active CV

Khi user muốn đổi CV đang active (cv.md) sang một CV khác trong thư viện `cvs/`. Gọi qua `/career-ops cv-switch` hoặc `/career-ops cv switch`.

## Inputs

1. **Thư viện CV tại** `cvs/` — liệt kê tất cả file `.md` (trừ `_archive/`)
2. **CV hiện tại** `cv.md` — để biết CV nào đang active

## Step 1 — Liệt Kê CV

Đọc tất cả file `.md` trong `cvs/` (bỏ qua `_archive/` và `.gitkeep`):

```
┌─────────────────────────────────────────────────────────┐
│  📂 CV LIBRARY — Chọn CV để kích hoạt                    │
│                                                         │
│  ┌──────────────────────────────────────────────────┐  │
│  │  [1] base.md                      (CV gốc)        │  │
│  │  [2] techco-senior-java.md    ★ active             │  │
│  │  [3] vnpay-backend-dev.md        (15/05/2026)     │  │
│  │  [4] fpt-java-fresher.md         (10/05/2026)     │  │
│  └──────────────────────────────────────────────────┘  │
│                                                         │
│  CV đang active: techco-senior-java.md                  │
│                                                         │
│  Gõ số để chọn, hoặc "q" để thoát...                   │
└─────────────────────────────────────────────────────────┘
```

Đánh dấu ★ cho CV đang active (kiểm tra: nội dung `cv.md` giống với file nào trong `cvs/`).

## Step 2 — Chọn & Kích Hoạt

Khi user chọn 1 số:

1. Copy file được chọn → `cv.md` (ghi đè)
2. Xác nhận:

```
✅ Đã kích hoạt: {tên file}

cv.md hiện tại là bản sao của cvs/{file-name}.md
```

## Edge Cases

### Chỉ có 1 CV

Nếu `cvs/` chỉ có `base.md`:

```
📂 CV LIBRARY

Chỉ có 1 CV: base.md (đang active)

Không có CV nào khác để chuyển.
Dùng /career-ops new-cv để tạo CV mới.
```

### Không có CV nào

Nếu `cvs/` trống (chưa có file `.md` nào):

```
📂 CV LIBRARY

Chưa có CV nào trong thư viện.

Dùng /career-ops new-cv để tạo CV đầu tiên.
```

### Số không hợp lệ

Nếu user gõ số ngoài danh sách:

```
❌ Số {N} không hợp lệ. Chọn từ 1 đến {max}.
```

## Step 3 — Post-Switch

Sau khi chuyển CV, gợi ý:

```
💡 Gợi ý:
- CV này có thể chưa tailored cho JD cụ thể.
  Paste JD để tôi đánh giá và tạo CV tailored.
- Hoặc chạy /career-ops gap-fill để phân tích gap.
```

## NEVER

1. Xóa file trong `cvs/` — chỉ copy, không xóa
2. Tự động chọn CV — user phải chọn thủ công
3. Sửa nội dung CV khi copy — giữ nguyên 100%
