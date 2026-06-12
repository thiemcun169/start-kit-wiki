# 🧠 Second Brain Wiki — Starter Kit

Bộ công cụ giúp bạn **tự xây một kho kiến thức (second brain)** do **AI tự bảo trì**, xem được dạng **graph trong Obsidian** và **đồng bộ qua Git** — theo *LLM Wiki pattern*.

> Bạn **đưa nguồn + đặt câu hỏi**, AI lo **toàn bộ việc bảo trì**: viết note, liên kết chéo, cập nhật mục lục, phát hiện mâu thuẫn.

## Bắt đầu trong 15 phút
1. Cài [Claude Code](https://claude.com/claude-code) và [Obsidian](https://obsidian.md/).
2. Tạo một thư mục trống cho kho, mở terminal tại đó, chạy `claude`.
3. Mở [`02-SETUP-PROMPT.md`](02-SETUP-PROMPT.md), copy prompt và dán vào Claude Code.
4. Trả lời các câu hỏi (mảng kiến thức, lĩnh vực, nguồn dữ liệu, Git/GitHub…). Claude sẽ tự dựng toàn bộ cấu trúc.
5. Mở Obsidian → *Open folder as vault* → chọn thư mục kho → bật **Graph View**.

## Nội dung kit (theo hành trình: hiểu → setup → dùng)
| File | Dùng để |
|---|---|
| [`00-ONBOARD-HOC-VIEN.md`](00-ONBOARD-HOC-VIEN.md) | Tổng quan & các bước, kèm hướng dẫn chuẩn bị Git + token |
| [`01-GIAI-THICH-KIEN-THUC.md`](01-GIAI-THICH-KIEN-THUC.md) | **HIỂU** — *vì sao* hệ thống hoạt động (LLM Wiki, 3 lớp, workflow) |
| [`02-SETUP-PROMPT.md`](02-SETUP-PROMPT.md) | **SETUP** — prompt chính dán vào Claude Code để dựng kho |
| [`03-CLAUDE-TEMPLATE.md`](03-CLAUDE-TEMPLATE.md) | Mẫu `CLAUDE.md` (luật vận hành) — tham chiếu cho setup |
| [`04-HUONG-DAN-SU-DUNG.md`](04-HUONG-DAN-SU-DUNG.md) | **SỬ DỤNG** — hướng dẫn dùng hằng ngày |

## Hệ thống hoạt động thế nào
```
raw/      Nguồn gốc bất biến (AI chỉ đọc)
wiki/     Tri thức do AI sở hữu & bảo trì (note .md liên kết chéo)
CLAUDE.md / AGENTS.md   Luật vận hành cho mọi AI
+ index.md (mục lục) + log.md (nhật ký)
```
3 workflow: **INGEST** (nạp nguồn) · **QUERY** (hỏi đáp) · **LINT** (dọn dẹp). Chi tiết trong [`01-GIAI-THICH-KIEN-THUC.md`](01-GIAI-THICH-KIEN-THUC.md).

## Nguồn tham khảo
- LLM Wiki — Andrej Karpathy: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- Building a Second Brain — Tiago Forte
- Zettelkasten / How to Take Smart Notes — Sönke Ahrens
- Obsidian: https://obsidian.md/

---
*Miễn phí sử dụng cho mục đích học tập. Đóng góp/issue luôn được hoan nghênh.*
