# Career-Ops

## Đây là gì?

Career-Ops biến bất kỳ CLI AI coding nào thành một trung tâm chỉ huy tìm việc toàn diện. Thay vì theo dõi đơn ứng tuyển thủ công trong bảng tính, bạn có một pipeline hỗ trợ AI:

- **Đánh giá offer** với hệ thống chấm điểm A-F có cấu trúc (10 tiêu chí có trọng số)
- **Tạo PDF cá nhân hóa** -- CV tối ưu ATS được điều chỉnh theo từng mô tả công việc
- **Quét portal tự động** (Greenhouse, Ashby, Lever, trang công ty)
- **Xử lý hàng loạt** -- đánh giá 10+ offer song song với sub-agents
- **Theo dõi mọi thứ** trong một nguồn dữ liệu duy nhất với kiểm tra tính toàn vẹn

> **Quan trọng: Đây KHÔNG phải công cụ spam rải đơn.** Career-ops là bộ lọc -- giúp bạn tìm những offer xứng đáng với thời gian trong hàng trăm tin tuyển dụng. Hệ thống khuyến nghị không nộp đơn cho bất kỳ offer nào dưới 4.0/5. Thời gian của bạn quý giá, và nhà tuyển dụng cũng vậy. Luôn xem lại trước khi nộp.

Career-ops là agentic: Claude Code điều hướng trang tuyển dụng với Playwright, đánh giá sự phù hợp bằng cách phân tích CV của bạn vs mô tả công việc (không phải so khớp từ khóa), và điều chỉnh CV cho từng tin tuyển dụng.

> **Lưu ý: những đánh giá đầu tiên sẽ chưa tốt.** Hệ thống chưa biết bạn. Hãy cung cấp ngữ cảnh -- CV, câu chuyện nghề nghiệp, proof points, sở thích, điểm mạnh, những gì bạn muốn tránh. Nuôi dưỡng nó càng nhiều, nó càng tốt hơn. Hãy nghĩ như onboard một recruiter mới: tuần đầu họ cần học về bạn, sau đó họ trở nên vô giá.

## Tính năng

| Tính năng | Mô tả |
|-----------|--------|
| **Auto-Pipeline** | Dán URL, nhận đánh giá đầy đủ + PDF + tracker entry |
| **Đánh giá 6 khối** | Tóm tắt vai trò, phù hợp CV, chiến lược cấp bậc, nghiên cứu lương, cá nhân hóa, chuẩn bị phỏng vấn (STAR+R) |
| **Ngân sách câu chuyện phỏng vấn** | Tích lũy câu chuyện STAR+Reflection qua các đánh giá -- 5-10 câu chuyện chủ lực trả lời mọi câu hỏi hành vi |
| **Kịch bản đàm phán** | Framework đàm phán lương, phản đối chiết khấu địa lý, tận dụng offer cạnh tranh |
| **Tạo PDF ATS** | CV tiêm keywords với thiết kế Space Grotesk + DM Sans |
| **Quét Portal** | 45+ công ty đã cấu hình sẵn (Anthropic, OpenAI, ElevenLabs, Retool, n8n...) + truy vấn tùy chỉnh trên Ashby, Greenhouse, Lever, Wellfound |
| **Xử lý hàng loạt** | Đánh giá song song với `claude -p` workers |
| **Dashboard TUI** | Giao diện terminal để duyệt, lọc, và sắp xếp pipeline |
| **Human-in-the-Loop** | AI đánh giá và khuyến nghị, bạn quyết định và hành động. Hệ thống không bao giờ nộp đơn -- bạn luôn có quyết định cuối cùng |
| **Tính toàn vẹn Pipeline** | Tự động merge, dedup, chuẩn hoá trạng thái, kiểm tra sức khỏe |

## Bắt đầu nhanh

```bash
# 1. Clone và cài đặt
git clone https://github.com/vanhaydoi/career-job.git
cd career-ops && npm install
npx playwright install chromium   # Cần thiết cho tạo PDF

# 2. Kiểm tra thiết lập
npm run doctor                     # Xác thực tất cả điều kiện tiên quyết

# 3. Cấu hình
cp config/profile.example.yml config/profile.yml  # Sửa với thông tin của bạn
cp templates/portals.example.yml portals.yml       # Tùy chỉnh công ty

# 4. Thêm CV của bạn
# Tạo cv.md ở thư mục gốc dự án với CV dạng markdown

# 5. Cá nhân hóa với Claude
claude   # Mở Claude Code trong thư mục này

# Sau đó yêu cầu Claude điều chỉnh hệ thống cho bạn:
# "Đổi archetype sang vai trò backend engineering"
# "Dịch mode sang tiếng Việt"
# "Thêm 5 công ty này vào portals.yml"
# "Cập nhật profile với CV tôi vừa dán"

# 6. Bắt đầu sử dụng
# Dán URL tuyển dụng hoặc chạy /career-ops
```

> **Hệ thống được thiết kế để Claude tự tùy chỉnh.** Modes, archetype, trọng số chấm điểm, kịch bản đàm phán -- chỉ cần yêu cầu Claude thay đổi. Nó đọc cùng file nó sử dụng, nên nó biết chính xác cần chỉnh gì.

Xem [docs/SETUP.md](docs/SETUP.md) để biết hướng dẫn thiết lập đầy đủ.

## Cách sử dụng

Career-ops là một lệnh slash duy nhất với nhiều chế độ:

```
/career-ops                → Hiển thị tất cả lệnh có sẵn
/career-ops {dán JD}       → Auto-pipeline đầy đủ (đánh giá + PDF + tracker)
/career-ops scan           → Quét portal tìm offer mới
/career-ops pdf            → Tạo CV tối ưu ATS
/career-ops batch          → Đánh giá hàng loạt nhiều offer
/career-ops tracker        → Xem trạng thái ứng tuyển
/career-ops apply          → Điền form ứng tuyển với AI
/career-ops pipeline       → Xử lý URL đang chờ
/career-ops contacto       → Tin nhắn LinkedIn outreach
/career-ops deep           → Nghiên cứu sâu công ty
/career-ops training       → Đánh giá khóa học/chứng chỉ
/career-ops project        → Đánh giá dự án portfolio
```

Hoặc chỉ cần dán URL tuyển dụng hoặc mô tả công việc trực tiếp -- career-ops tự phát hiện và chạy pipeline đầy đủ.

## Cách hoạt động

```
Bạn dán URL tuyển dụng hoặc mô tả công việc
        │
        ▼
┌──────────────────┐
│  Phát hiện       │  Phân loại: LLMOps / Agentic / PM / SA / FDE / Transformation
│  Archetype       │
└────────┬─────────┘
         │
┌────────▼─────────┐
│  Đánh giá A-F    │  Phù hợp, gaps, nghiên cứu lương, câu chuyện STAR
│  (đọc cv.md)     │
└────────┬─────────┘
         │
    ┌────┼────┐
    ▼    ▼    ▼
 Report  PDF  Tracker
  .md   .pdf   .tsv
```

## Portal đã cấu hình sẵn

Quét đi kèm **45+ công ty** sẵn sàng quét và **19 truy vấn tìm kiếm** trên các job board lớn. Sao chép `templates/portals.example.yml` sang `portals.yml` và thêm của riêng bạn:

**AI Labs:** Anthropic, OpenAI, Mistral, Cohere, LangChain, Pinecone
**Voice AI:** ElevenLabs, PolyAI, Parloa, Hume AI, Deepgram, Vapi, Bland AI
**AI Platforms:** Retool, Airtable, Vercel, Temporal, Glean, Arize AI
**Contact Center:** Ada, LivePerson, Sierra, Decagon, Talkdesk, Genesys
**Enterprise:** Salesforce, Twilio, Gong, Dialpad
**LLMOps:** Langfuse, Weights & Biases, Lindy, Cognigy, Speechmatics
**Automation:** n8n, Zapier, Make.com
**European:** Factorial, Attio, Tinybird, Clarity AI, Travelperk

**Job board được quét:** Ashby, Greenhouse, Lever, Wellfound, Workable, RemoteFront

## Dashboard TUI

Dashboard terminal tích hợp cho phép duyệt pipeline trực quan:

```bash
cd dashboard
go build -o career-dashboard .
./career-dashboard --path ..
```

Tính năng: 6 tab lọc, 4 chế độ sắp xếp, grouped/flat view, lazy-loaded previews, đổi trạng thái inline.

## Cấu trúc dự án

```
career-ops/
├── CLAUDE.md                    # Hướng dẫn agent
├── cv.md                        # CV của bạn (tạo file này)
├── article-digest.md            # Proof points (tuỳ chọn)
├── config/
│   └── profile.example.yml      # Mẫu hồ sơ
├── modes/                       # 14 chế độ kỹ năng
│   ├── _shared.md               # Ngữ cảnh chung (tùy chỉnh)
│   ├── oferta.md                # Đánh giá đơn lẻ
│   ├── pdf.md                   # Tạo PDF
│   ├── scan.md                  # Quét portal
│   ├── batch.md                 # Xử lý hàng loạt
│   ├── vi/                      # Tiếng Việt
│   │   ├── _shared.md           # Ngữ cảnh chung (VI)
│   │   ├── danh-gia.md          # Đánh giá (VI)
│   │   ├── ung-tuyen.md         # Nộp đơn (VI)
│   │   └── pipeline.md          # Pipeline (VI)
│   └── ...
├── templates/
│   ├── cv-template.html         # Mẫu CV tối ưu ATS
│   ├── portals.example.yml      # Mẫu cấu hình scanner
│   └── states.yml               # Trạng thái chuẩn
├── batch/
│   ├── batch-prompt.md          # Prompt worker tự chứa
│   └── batch-runner.sh          # Script điều phối
├── dashboard/                   # Go TUI pipeline viewer
├── data/                        # Dữ liệu theo dõi (gitignored)
├── reports/                     # Report đánh giá (gitignored)
├── output/                      # PDF đã tạo (gitignored)
├── fonts/                       # Space Grotesk + DM Sans
├── docs/                        # Thiết lập, tùy chỉnh, kiến trúc
└── examples/                    # CV mẫu, report, proof points
```

## Công nghệ

![Claude Code](https://img.shields.io/badge/Claude_Code-000?style=flat&logo=anthropic&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat&logo=playwright&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)
![Bubble Tea](https://img.shields.io/badge/Bubble_Tea-FF75B5?style=flat&logo=go&logoColor=white)

- **Agent**: Claude Code với skill và mode tùy chỉnh
- **PDF**: Playwright/Puppeteer + mẫu HTML
- **Scanner**: Playwright + Greenhouse API + WebSearch
- **Dashboard**: Go + Bubble Tea + Lipgloss (Catppuccin Mocha theme)
- **Data**: Bảng Markdown + cấu hình YAML + file TSV hàng loạt

## Tuyên bố miễn trừ trách nhiệm

**career-ops là công cụ local, open source -- KHÔNG phải dịch vụ hosted.** Khi sử dụng phần mềm này, bạn thừa nhận:

1. **Bạn kiểm soát dữ liệu của mình.** CV, thông tin liên lạc, và dữ liệu cá nhân của bạn ở trên máy của bạn và được gửi trực tiếp đến nhà cung cấp AI bạn chọn (Anthropic, OpenAI, v.v.). Chúng tôi không thu thập, lưu trữ, hoặc có quyền truy cập bất kỳ dữ liệu nào của bạn.
2. **Bạn kiểm soát AI.** Prompt mặc định hướng dẫn AI không tự động nộp đơn, nhưng mô hình AI có thể hành vi không lường trước được. Nếu bạn chỉnh sửa prompt hoặc dùng mô hình khác, bạn tự chịu rủi ro. **Luôn xem lại nội dung AI tạo ra về độ chính xác trước khi nộp.**
3. **Bạn tuân thủ ToS bên thứ ba.** Bạn phải sử dụng công cụ này theo Điều khoản dịch vụ của các portal tuyển dụng bạn tương tác (Greenhouse, Lever, Workday, LinkedIn, v.v.). Không dùng công cụ này để spam nhà tuyển dụng hoặc quá tải hệ thống ATS.
4. **Không có bảo đảm.** Đánh giá là khuyến nghị, không phải sự thật. Mô hình AI có thể bịa đặt kỹ năng hoặc kinh nghiệm. Tác giả không chịu trách nhiệm về kết quả tuyển dụng, đơn bị từ chối, hạn chế tài khoản, hoặc bất kỳ hậu quả nào khác.

Xem [LEGAL_DISCLAIMER.md](LEGAL_DISCLAIMER.md) để biết chi tiết đầy đủ. Phần mềm này được cung cấp theo [Giấy phép MIT](LICENSE) "nguyên trạng", không có bảo hành dưới bất kỳ hình thức nào.

## Giấy phép

MIT
