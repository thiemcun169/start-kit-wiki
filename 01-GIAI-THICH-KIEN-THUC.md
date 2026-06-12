# 📚 Giải thích kiến thức: LLM Wiki = Second Brain + AI

Đọc file này để hiểu *bản chất* hệ thống. Có 2 lớp ý tưởng ghép lại: **Second Brain** (Tiago Forte) + **cách tổ chức Wiki/Zettelkasten**, rồi thêm **AI (LLM)** để vận hành.

---

## 1. Second Brain là gì? (nền tảng — Tiago Forte)
**Second Brain = một hệ thống SỐ lưu trữ thông tin thay cho não thật**, để bộ não dành sức cho việc nó giỏi nhất: **ra quyết định & sáng tạo**.

> Nguyên tắc cốt lõi: **Second Brain PHỤC VỤ First Brain (não thật), KHÔNG thay thế.** Bạn vẫn là người suy nghĩ và quyết định — kho chỉ là bộ nhớ ngoài đáng tin.

**Bài toán nó giải:**
- Đọc xong sách 1 tháng quên ~90%.
- Thông tin rải rác khắp nơi: Slack / Drive / giấy / chat AI.
- Mỗi tuần mất thời gian tìm lại file cũ.
- Ý hay lúc 11h đêm → sáng quên sạch; họp xong action items biến mất.

**Lợi ích — chỉ thấy rõ khi tích luỹ 6 tháng+:**
| Lợi ích | Cụ thể |
|---|---|
| Compound effect | 1 quyết định mới được hỗ trợ bởi hàng trăm note cũ |
| Pattern cá nhân | Đọc lại note cũ thấy mình lặp lỗi / insight |
| Idea generation | 2 note tự link qua `[[wikilink]]` → bật ra insight (Zettelkasten) |
| Career portability | Đổi công ty, kiến thức vẫn là của bạn |
| Tăng tốc viết | 1 bài 2-3h thay vì 6-8h |

*"1 note hôm nay = giúp 100 quyết định trong 5 năm tới" — nhưng chỉ khi kiên trì tích luỹ + distill (chắt lọc).*

## 2. Cách tổ chức: Wiki + Zettelkasten
Để kho không thành "bãi rác note", ta tổ chức như một **wiki**:
- **1 note = 1 ý** (atomic), đặt tên rõ ràng.
- **Liên kết `[[wikilink]]`** giữa các note → tạo mạng tri thức (Zettelkasten). Chính các liên kết này sinh ra insight, và hiện thành **graph** trong Obsidian.
- **MOC (Map of Content)** = note cửa ngõ gom các note cùng chủ đề.

→ **Chính cách tổ chức wiki này LÀ "second brain" của bạn** — một mạng kiến thức liên kết, không phải đống file rời.

## 3. Điểm KHÁC BIỆT: thêm AI (LLM Wiki)
Đây là chỗ tiến hoá so với Second Brain truyền thống (vốn con người tự bảo trì). Tham khảo *LLM Wiki pattern* của Andrej Karpathy: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f

Với một **LLM** cắm vào kho, AI giúp bạn:
- **Extract** — đọc nguồn thô (bài viết, PDF, chat) và rút ý chính.
- **Tổ chức & Quản lý** — tạo note đúng quy ước, đặt đúng mảng, cập nhật mục lục.
- **Link** — tự nối `[[wikilink]]` giữa các note liên quan, giữ mạng liên kết luôn sống.
- **Truy vấn** — bạn hỏi tự nhiên, AI tổng hợp từ kho và trích dẫn nguồn.

> ⚠️ **KHÔNG phải "AI quản lý hết thay bạn".** Vai trò vẫn rạch ròi:
> - **Con người** curate nguồn, đặt câu hỏi, ra quyết định (First Brain).
> - **AI** lo phần *bookkeeping* mệt mỏi (viết note, cập nhật liên kết, chắt lọc, dò mâu thuẫn) — thứ giết chết hầu hết hệ thống tự-tay.
> - **File markdown** vẫn là **nơi lưu trữ** thật sự — của bạn, mở được mọi nơi, không khoá vào app nào.

Nói gọn: **bạn curate + hỏi; AI làm bookkeeping; file là kho.**

## 4. Kiến trúc 3 lớp (hiện thực hoá ý trên)
```
┌─────────────────────────────────────────────┐
│  raw/      Nguồn gốc bất biến (AI chỉ ĐỌC)    │  ← bạn bỏ bài viết, PDF, ảnh, ghi chú thô
├─────────────────────────────────────────────┤
│  wiki/     Tri thức do AI tổ chức & bảo trì   │  ← note .md liên kết chéo, chia theo mảng
├─────────────────────────────────────────────┤
│  CLAUDE.md / AGENTS.md   Luật vận hành        │  ← để mọi AI làm việc nhất quán
└─────────────────────────────────────────────┘
        +  index.md (mục lục, AI đọc trước)
        +  log.md   (nhật ký append-only)
```

## 5. Ba workflow
- **INGEST (nạp):** đưa nguồn → AI lưu `raw/`, extract, tạo/cập nhật note `wiki/`, link chéo, cập nhật mục lục, ghi log, sync git.
- **QUERY (hỏi):** AI đọc `index.md` → tìm note → trả lời kèm trích dẫn `[[..]]`; ý mới đáng giữ → tạo note (không để trôi vào chat).
- **LINT (dọn):** định kỳ rà mâu thuẫn, note mồ côi, link treo, đề xuất hợp nhất.

## 6. Vì sao Obsidian + Markdown + Git
- **Markdown** = file `.md` thuần → mở mọi nơi, không khoá vào app.
- **Obsidian** = giao diện + **Graph View** trực quan hoá mạng `[[wikilink]]` (local-first, miễn phí).
- **Git** = lịch sử phiên bản + đồng bộ nhiều máy, miễn phí.
- **Luật trong `CLAUDE.md`/`AGENTS.md`** → bất kỳ AI nào đọc cũng vận hành giống nhau ("context engineering").

## Nguồn tham khảo
- Second Brain / CODE / PARA — Tiago Forte: https://www.buildingasecondbrain.com/book
- LLM Wiki — Andrej Karpathy: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- How to Take Smart Notes (Zettelkasten) — Sönke Ahrens: https://www.soenkeahrens.de/en/takesmartnotes
- Evergreen notes — Andy Matuschak: https://notes.andymatuschak.org/Evergreen_notes
- Obsidian: https://obsidian.md/
