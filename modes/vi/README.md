# career-ops -- Chế độ tiếng Việt (`modes/vi/`)

Thư mục này chứa các bản dịch tiếng Việt của các mode chính career-ops dành cho ứng viên tìm việc tại thị trường Việt Nam.

## Khi nào sử dụng các mode này?

Sử dụng `modes/vi/` nếu ít nhất một trong các điều kiện sau được đáp ứng:

- Bạn đang ứng tuyển chủ yếu vào các **tin tuyển dụng tiếng Việt** (ITviec, VietnamWorks, TopCV, LinkedIn VN, trang tuyển dụng công ty)
- **CV của bạn bằng tiếng Việt** hoặc bạn chuyển đổi giữa VI và EN tuỳ theo tin tuyển dụng
- Bạn cần câu trả lời và thư xin việc bằng **tiếng Việt công nghệ tự nhiên**, không phải dịch máy
- Bạn cần xử lý các **đặc thù thị trường Việt Nam**: hợp đồng lao động, thử việc, BHXH/BHYT/BHTN, lương gross/net, lương tháng 13, thưởng Tết, phép năm

Nếu phần lớn tin tuyển dụng bạn ứng tuyển là tiếng Anh, hãy sử dụng các mode mặc định trong `modes/`. Các mode tiếng Anh vẫn hoạt động với tin tiếng Việt, nhưng không nắm rõ chi tiết thị trường Việt Nam.

## Cách kích hoạt?

career-ops không có "công tắc ngôn ngữ" trong code. Thay vào đó có 2 cách:

### Cách 1 -- Theo phiên

Nói với Claude đầu phiên:

> "Sử dụng mode tiếng Việt trong `modes/vi/`."

hoặc

> "Đánh giá và ứng tuyển bằng tiếng Việt. Đọc `modes/vi/_shared.md` và `modes/vi/danh-gia.md`."

Claude sẽ đọc file từ thư mục này thay vì `modes/`.

### Cách 2 -- Cố định qua profile

Thêm cấu hình ngôn ngữ trong `config/profile.yml`:

```yaml
language:
  primary: vi
  modes_dir: modes/vi
```

Trong phiên đầu tiên, nói với Claude rằng bạn đã cấu hình `language.modes_dir` ("Nhìn vào `profile.yml`, tôi đã đặt `language.modes_dir`"). Claude sẽ tự động sử dụng mode tiếng Việt.

> Ghi chú: `language.modes_dir` là quy ước, không phải schema bắt buộc. Người bảo trì có thể thay đổi tên trường này bất cứ lúc nào.

## Những mode nào đã dịch?

Đợt đầu tiên covers 4 mode có tác động lớn nhất:

| File | Dịch từ | Vai trò |
|------|---------|---------|
| `_shared.md` | `modes/_shared.md` (EN) | Ngữ cảnh chung, archetype, quy tắc toàn cầu, đặc thù thị trường VN |
| `danh-gia.md` | `modes/oferta.md` (ES) | Đánh giá toàn diện offer (Khối A-F) |
| `ung-tuyen.md` | `modes/apply.md` (EN) | Trợ lý trực tiếp điền form ứng tuyển |
| `pipeline.md` | `modes/pipeline.md` (ES) | Hộp thư URL / Second Brain cho offer thu thập |

Các mode khác (`scan`, `batch`, `pdf`, `tracker`, `auto-pipeline`, `deep`, `contacto`, `ofertas`, `project`, `training`) vẫn giữ nguyên EN/ES. Nội dung của chúng chủ yếu là tooling, đường dẫn và lệnh -- nên độc lập với ngôn ngữ.

## Những gì giữ tiếng Anh?

Cố ý không dịch vì là từ vựng công nghệ tiêu chuẩn:

- `cv.md`, `pipeline`, `tracker`, `report`, `score`, `archetype`, `proof point`
- Tên công cụ (`Playwright`, `WebSearch`, `WebFetch`, `Read`, `Write`, `Edit`, `Bash`)
- Giá trị trạng thái trong tracker (`Evaluated`, `Applied`, `Interview`, `Offer`, `Rejected`)
- Đoạn mã, đường dẫn, lệnh

Các mode sử dụng tiếng Việt công nghệ tự nhiên, như cách nói trong các đội engineering tại TP.HCM và Hà Nội: văn bản chính bằng tiếng Việt, thuật ngữ kỹ thuật giữ tiếng Anh khi đó là cách dùng thông dụng. Không dịch "Pipeline" thành "Đường ống" hay "Deploy" thành "Triển khai ứng dụng".

## Từ điển tham chiếu

Để giữ giọng điệu nhất quán khi chỉnh sửa hoặc mở rộng mode:

| Tiếng Anh | Tiếng Việt (trong codebase này) |
|-----------|-------------------------------|
| Job posting | Tin tuyển dụng |
| Application | Đơn ứng tuyển / Hồ sơ ứng tuyển |
| Cover letter | Thư xin việc |
| Resume / CV | CV / Sơ yếu lý lịch |
| Salary | Lương |
| Compensation | Thu nhập / Đãi ngộ |
| Skills | Kỹ năng |
| Interview | Phỏng vấn |
| Hiring manager | Quản lý tuyển dụng |
| Recruiter | Nhà tuyển dụng / HR |
| AI | AI (Trí tuệ nhân tạo) |
| Requirements | Yêu cầu |
| Career history | Lịch sử nghề nghiệp |
| Notice period | Thời hạn báo trước |
| Probation | Thời gian thử việc |
| Vacation | Phép năm |
| 13th month salary | Lương tháng 13 |
| Tet bonus | Thưởng Tết |
| Full-time employment | Toàn thời gian / Chính thức |
| Remote | Làm việc từ xa |
| Hybrid | Kết hợp (Hybrid) |
| Social insurance | Bảo hiểm xã hội (BHXH) |
| Health insurance | Bảo hiểm y tế (BHYT) |
| Gross salary | Lương gross (trước thuế) |
| Net salary | Lương net (sau thuế) |
| Personal income tax | Thuế thu nhập cá nhân (TNCN) |
| Probation period | Thời gian thử việc |
| Employment contract | Hợp đồng lao động |

## Đóng góp

Để cải thiện bản dịch hoặc thêm mode:

1. Mở Issue với đề xuất (xem `CONTRIBUTING.md`)
2. Tuân thủ từ điển ở trên để giữ giọng điệu nhất quán
3. Dịch theo cách tự nhiên -- không dịch word-by-word
4. Giữ nguyên các yếu tố cấu trúc (Khối A-F, bảng, khối code, hướng dẫn công cụ)
5. Test với tin tuyển dụng tiếng Việt thực (ITviec, VietnamWorks, TopCV) trước khi submit PR
