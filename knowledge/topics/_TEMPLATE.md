# Hướng dẫn mở rộng kiến thức cá nhân

Thư mục `topics/` là nơi bạn tự tạo các file kiến thức chuyên sâu của riêng mình.

**Khác với `roles/`:**
- `roles/` là bộ khung kỹ năng CHUNG cho từng role (Backend, Frontend, DevOps...). Được hệ thống đọc để sinh câu hỏi và phân tích gap.
- `topics/` là kiến thức CÁ NHÂN của bạn. Bạn tự viết, tự mở rộng. Hệ thống sẽ đọc thêm nếu có.

## Cách tạo file topic

1. Tạo file markdown mới trong thư mục này, ví dụ: `topics/java-nang-cao.md`
2. Viết nội dung theo format tự do — không bắt buộc format như roles/
3. Hệ thống sẽ tự động đọc các file trong `topics/` khi chạy tech-qa mode

## Template gợi ý

```markdown
# Tên chủ đề

## Kiến thức đã nắm
- Điểm 1
- Điểm 2

## Kinh nghiệm thực tế
- Dự án A: đã áp dụng X, Y, Z
- Dự án B: đã gặp vấn đề W và giải quyết bằng...

## Các câu hỏi thường gặp
### Câu 1: ...
**Trả lời:** ...

### Câu 2: ...
**Trả lời:** ...

## Tài liệu tham khảo
- Link 1
- Link 2
```

## Lưu ý

- File trong `topics/` sẽ không bị hệ thống tự động cập nhật hay ghi đè
- Bạn có thể tạo bao nhiêu file tùy thích, đặt tên tùy ý
- Nội dung trong đây sẽ được tech-qa mode tham khảo khi sinh câu trả lời
