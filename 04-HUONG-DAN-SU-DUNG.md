# 🛠️ Hướng dẫn sử dụng Second Brain (luồng thực tế)

Sau khi đã chạy SETUP-PROMPT và có kho, đây là cách bạn **dùng nó hằng ngày**. Nguyên tắc duy nhất cần nhớ: **bạn đưa nguồn + đặt câu hỏi bằng tiếng Việt tự nhiên, AI lo phần còn lại.**

> Cách làm việc: mở terminal tại thư mục kho → gõ `claude` → nói chuyện như nhắn tin. Mở Obsidian song song để xem note & graph cập nhật.

---

## 0. Mở đầu mỗi phiên (10 giây)
**Bạn gõ:**
> "pull và check có gì mới"

**AI làm:** kéo bản mới nhất về (`git pull`), báo có gì thay đổi từ máy khác. → Luôn làm bước này trước khi bắt đầu để khỏi xung đột.

---

## 1. 📥 Nạp kiến thức — INGEST (dùng nhiều nhất)
Bất cứ khi nào gặp thứ đáng giữ: bài viết, link, đoạn chat hay, ý tưởng, ghi chú họp…

**Cách A — dán thẳng:**
> "ingest cái này vào second brain: [dán link hoặc đoạn text]"

**Cách B — bỏ file vào rồi bảo AI:** kéo PDF/ảnh vào thư mục `raw/`, rồi:
> "ingest các nguồn mới trong raw/"

**AI làm:** lưu bản gốc vào `raw/` → rút ý chính → tạo/cập nhật note trong `wiki/` → tự nối `[[liên kết]]` tới note liên quan → cập nhật mục lục → lưu & đồng bộ git.

**Ví dụ thật:**
> Bạn: "ingest cái này: https://... (bài về cách viết email bán hàng)"
> AI: "Đã lưu nguồn, tạo note `viet-email-ban-hang.md` trong mảng `cong-viec`, nối với note `copywriting` và `pheu-ban-hang` đã có. Cập nhật mục lục xong."

→ Mở Obsidian, bật **Graph View**: bạn sẽ thấy note mới xuất hiện và nối vào mạng.

---

## 2. 💬 Hỏi đáp & ra quyết định — QUERY
Kho càng đầy, trả lời càng "hiểu bạn". Hỏi tự nhiên:

> "tôi đã ghi gì về định giá sản phẩm?"
> "tổng hợp mọi note liên quan đến tuyển dụng giúp tôi"
> "tôi đang phân vân có nên nhận dự án X — kho có note nào liên quan để cân nhắc không?"

**AI làm:** đọc mục lục → tìm note liên quan → trả lời **kèm trích dẫn** `[[tên-note]]` để bạn lần ngược về nguồn. Nếu trong lúc trả lời nảy ra ý mới đáng giữ, AI sẽ đề xuất tạo note để không trôi mất.

→ Đây chính là **compound effect**: 1 quyết định hôm nay được hàng trăm note cũ hỗ trợ.

---

## 3. ✍️ Thêm note nhanh (khi tự nghĩ ra)
Không cần nguồn ngoài, chỉ là ý của bạn:

> "thêm note vào mảng ca-nhan: bài học hôm nay là nên xác nhận deadline bằng văn bản"

**AI làm:** tạo note đúng quy ước (frontmatter, đặt đúng mảng) + nối liên kết phù hợp.

*Hoặc tự tay trong Obsidian:* tạo file mới từ `templates/note.md`, điền nội dung, đặt vào `wiki/<mảng>/`. AI sẽ dọn liên kết giúp ở lần lint sau.

---

## 4. 🧹 Dọn dẹp định kỳ — LINT (hằng tuần/tháng)
> "lint second brain"

**AI làm:** rà mâu thuẫn giữa các note, note "mồ côi" (không ai link tới), link treo, chỗ thiếu liên kết → đề xuất hợp nhất/bổ sung. Đây cũng là lúc bạn **đọc lại để thấy pattern cá nhân** (mình hay lặp lỗi gì, insight gì).

---

## 5. 🔬 Research một chủ đề sâu
Khi muốn "nạp dày" một lĩnh vực mới:

> "research giúp tôi chủ đề "quảng cáo Facebook": tìm vài nguồn tốt, tạo cụm note liên kết trong mảng cong-viec"

**AI làm:** tìm nguồn (web search), lưu trích dẫn vào `raw/`, tạo nhiều note concept liên kết chéo + một MOC chủ đề. → Graph của bạn có ngay một "cụm" mới.

---

## 6. 🔌 Kết nối nguồn dữ liệu (nếu đã cấu hình)
Nếu lúc setup bạn đã khai báo Notion / Google Drive / Gmail… (qua MCP):

> "lấy các trang trong Notion mục 'Đọc sau' và ingest vào kho"

**AI làm:** dùng connector lấy dữ liệu → ingest như mục 1.

---

## 7. 🔄 Đồng bộ nhiều máy
- AI **tự push** sau khi nạp/dọn nên thường bạn không phải làm gì.
- Máy mới: `git clone <repo của bạn>` → mở bằng Obsidian. Nhớ **"pull và check có gì mới"** trước khi sửa.

---

## ✅ Thói quen để kho thực sự hiệu quả
- **Capture ngay, đừng để dành** — gặp gì hay thì ingest liền, AI lo phân loại.
- **1 note = 1 ý**, cứ để AI nối liên kết — graph càng dày, AI tổng hợp càng giỏi.
- **Hỏi kho trước khi quyết định** quan trọng.
- **Lint mỗi tuần** 5 phút để kho không thành bãi rác.
- Kiên trì: lợi ích **compound** rõ rệt sau ~6 tháng.

> Nhớ: Second Brain **phục vụ** bộ não thật của bạn, không thay thế. Nó giúp bạn nhớ và kết nối — còn quyết định vẫn là của bạn.
