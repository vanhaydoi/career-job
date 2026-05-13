# Session Log: Vietnamese Localization for Career-Ops

**Date:** 2026-04-14
**Task:** Thêm hỗ trợ tiếng Việt (Vietnamese) cho toàn bộ hệ thống career-ops

---

## Bối cảnh

User clone career-ops về và muốn chuyển hệ thống từ chỉ hỗ trợ tiếng Anh/Tây Ban Nha/Pháp sang hỗ trợ thêm tiếng Việt để người Việt Nam sử dụng.

## Phân tích ban đầu

- Project **không dùng framework i18n** -- localization hoàn toàn bằng thư mục mode riêng dưới `modes/`
- Mỗi ngôn ngữ có `modes/{lang}/` với: `_shared.md`, `oferta.md` (đổi tên theo ngôn ngữ), `apply.md`, `pipeline.md`, `README.md`
- Tiếng Việt cần thêm từ vựng đặc thù: BHXH/BHYT/BHTN, lương gross/net, thưởng Tết, lương tháng 13, hợp đồng lao động, thử việc
- Cần cập nhật: modes, README, docs, scripts

## Những gì đã thực hiện

### 1. Tạo thư mục `modes/vi/` (5 file)

#### `modes/vi/_shared.md` (12.1 KB)
- Dịch toàn bộ `modes/_shared.md` sang tiếng Việt
- Hệ thống chấm điểm 6 khối A-F (1-5 điểm)
- Khối G: Tính xác thực tin tuyển dụng (3 mức: Độ tin cậy cao / Cần thận trọng / Đáng ngờ)
- 6 archetype: LLMOps, Agentic, PM, SA, FDE, Transformation
- Quy tắc KHÔNG BAO GIỜ (8 quy tắc) và LUÔN LUÔN (11 quy tắc)
- Bảng công cụ: WebSearch, WebFetch, Playwright, Read, Write, Edit, Bash
- Phần viết chuyên nghiệp & tương thích ATS
- **Thêm mới:** Từ vựng đặc thù thị trường VN (BHXH, BHYT, BHTN, thuế TNCN, ITviec, VietnamWorks, TopCV)
- **Thêm mới:** Framework đàm phán lương VN (gross/net)
- **Thêm mới:** Chính sách địa điểm VN

#### `modes/vi/danh-gia.md` (10.3 KB)
- Dịch từ `modes/oferta.md` (tiếng Tây Ban Nha)
- Đầy đủ khối A-G:
  - A: Tóm tắt vai trò
  - B: Phù hợp CV (có phần gaps + chiến lược giảm thiểu)
  - C: Cấp bậc & Chiến lược ("bán senior mà không nói dối")
  - D: Lương bổng & Nhu cầu (kèm ITviec, VietnamWorks làm nguồn)
  - E: Kế hoạch cá nhân hóa (Top 5 CV + Top 5 LinkedIn)
  - F: Kế hoạch phỏng vấn (STAR+R với cột Reflection)
  - G: Tính xác thực tin tuyển dụng (5 tín hiệu phân tích)
- Edge cases: nhà nước/học viện, evergreen, startup, niche/điều hành
- Sau đánh giá: lưu report .md + đăng ký tracker

#### `modes/vi/ung-tuyen.md` (4.8 KB)
- Dịch từ `modes/apply.md` (tiếng Anh)
- 8 bước quy trình: PHÁT HIỆN → XÁC ĐỊNH → TÌM KIẾM → TẢI → SO SÁNH → PHÂN TÍCH → TẠO → TRÌNH BÀY
- Xử lý thay đổi vai trò giữa đánh giá và lúc nộp
- Phân loại câu hỏi form: đã trả lời trong Phần G vs câu hỏi mới
- Định dạng output copy-paste sẵn
- Post-apply: cập nhật trạng thái tracker

#### `modes/vi/pipeline.md` (2.8 KB)
- Dịch từ `modes/pipeline.md` (tiếng Tây Ban Nha)
- Xử lý URL trong `data/pipeline.md`
- Phát hiện JD thông minh: Playwright → WebFetch → WebSearch
- Trường hợp đặc biệt: LinkedIn, PDF, prefix `local:`, ITviec/VietnamWorks
- Đánh số tự động cho report

#### `modes/vi/README.md` (5.7 KB)
- Hướng dẫn kích hoạt (2 cách: theo phiên / cố định qua profile.yml)
- Bảng mode đã dịch vs giữ nguyên
- Từ điển tham chiếu Anh-Việt (~25 thuật ngữ)
- Hướng dẫn đóng góp

### 2. Tạo `README.vi.md` (~280 dòng)
- Dịch toàn bộ README.md tiếng Anh sang tiếng Việt
- Badge VI đỏ (cờ Việt Nam)
- Thanh ngôn ngữ đầy đủ 9 ngôn ngữ
- Cấu trúc dự án cập nhật với `modes/vi/`
- Từ "open source" giữ nguyên

### 3. Cập nhật docs (4 file)

#### `CLAUDE.md`
- Thêm entry Vietnamese trong phần Language Modes
- Thêm 3 điều kiện kích hoạt Vietnamese modes
- Ghi chú đặc thù VN: BHXH/BHYT/BHTN, lương gross/net, ITviec, VietnamWorks, TopCV

#### `DATA_CONTRACT.md`
- Thêm `modes/fr/*`, `modes/ja/*`, `modes/vi/*` vào bảng system layer
- Trước đó chỉ có `modes/de/*`

#### `update-system.mjs`
- Thêm `modes/fr/`, `modes/ja/`, `modes/vi/` vào mảng SYSTEM_PATHS
- Trước đó chỉ có `modes/de/`

#### `.github/labeler.yml`
- Thêm `modes/vi/**` vào label "🌐 i18n"

### 4. Cập nhật README language bars (7 file)

Thêm `[Tiếng Việt](README.vi.md)` vào thanh ngôn ngữ của:
- `README.md` (EN)
- `README.es.md` (ES)
- `README.ja.md` (JA)
- `README.ko-KR.md` (KO)
- `README.pt-BR.md` (PT-BR)
- `README.ru.md` (RU)
- `README.zh-TW.md` (ZH-TW)

### 5. Cập nhật scripts (2 file)

#### `liveness-core.mjs`
- Thêm 3 expired patterns tiếng Việt:
  - `/việc làm không còn tuyển dụng/i`
  - `/vị trí đã được tuyển/i`
  - `/tin tuyển dụng đã hết hạn/i`
  - `/không còn nhận hồ sơ/i`
- Thêm 3 apply patterns tiếng Việt:
  - `/\bnộp hồ sơ\b/i`
  - `/\bứng tuyển\b/i`
  - `/\bapply now\b/i`

#### `templates/states.yml`
- Thêm VN aliases cho tất cả 8 trạng thái:
  - evaluated → `đã đánh giá`
  - applied → `đã nộp hồ sơ`
  - responded → `đã phản hồi`
  - interview → `phỏng vấn`
  - offer → `nhận offer`
  - rejected → `bị từ chối`
  - discarded → `đã hủy`
  - skip → `bỏ qua`

## Tổng kết thay đổi

| Loại | Số lượng | Chi tiết |
|------|----------|----------|
| File mới | 6 | modes/vi/ (5 file) + README.vi.md |
| File cập nhật | 8 | CLAUDE.md, DATA_CONTRACT.md, update-system.mjs, labeler.yml, liveness-core.mjs, states.yml, README.md, 7 READMEs khác |
| **Tổng** | **14** | |

## Từ vựng đặc thù thị trường Việt Nam đã đưa vào

| Thuật ngữ | Giải thích |
|-----------|-----------|
| Hợp đồng lao động | Employment contract |
| Thời gian thử việc | Probation (2 tháng, lương >= 85%) |
| Lương gross | Trước thuế + bảo hiểm |
| Lương net | Thực nhận sau trừ TNCN + BHXH + BHYT + BHTN |
| Lương tháng 13 | Không bắt buộc theo luật, thông lệ |
| Thưởng Tết | Phụ thuộc kết quả kinh doanh |
| Phép năm | Tối thiểu 12 ngày/năm (Luật Lao động) |
| BHXH | Bảo hiểm xã hội (~10.5% lương) |
| BHYT | Bảo hiểm y tế (~4.5% lương) |
| BHTN | Bảo hiểm thất nghiệp (~1%) |
| Thuế TNCN | Thuế suất lũy tiến 5-35% |
| ITviec | Nền tảng tuyển dụng IT hàng đầu VN |
| VietnamWorks | Nền tảng tuyển dụng tổng hợp lớn nhất |
| TopCV | Nền tảng tuyển dụng phổ biến |

## Cách kích hoạt tiếng Việt

**Theo phiên:** Nói "Sử dụng mode tiếng Việt trong `modes/vi/`" hoặc "dùng mode tiếng Việt"

**Cố định qua profile** (`config/profile.yml`):
```yaml
language:
  primary: vi
  modes_dir: modes/vi
```

## Quyết định thiết kế

1. **Không dịch tool names** -- Playwright, WebSearch, WebFetch, Read, Write, Edit, Bash giữ nguyên
2. **Không dịch tracker status** -- Evaluated, Applied, Interview, Offer, Rejected giữ nguyên trong tracker
3. **Không dịch tech terms** -- pipeline, report, score, archetype, proof point giữ nguyên
4. **Giữ nguyên cấu trúc** -- Khối A-F, bảng, code blocks, tool instructions giữ nguyên định dạng
5. **Tiếng Việt công nghệ tự nhiên** -- Văn bản chính bằng tiếng Việt, thuật ngữ tech giữ tiếng Anh khi là cách dùng thông dụng trong đội engineering VN
6. **Thêm đặc thù VN** -- Bảng từ vựng BHXH/lương gross-net/ITviec/VietnamWorks riêng cho thị trường VN
