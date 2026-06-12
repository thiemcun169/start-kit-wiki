# 🧠 Second Brain Wiki — Starter Kit

Bộ công cụ giúp bạn **tự xây một kho kiến thức (second brain)** do **AI tự bảo trì**, xem được dạng **graph trong Obsidian** và **đồng bộ qua Git** — theo *LLM Wiki pattern*.

> Bạn **đưa nguồn + đặt câu hỏi**, AI lo **toàn bộ việc bảo trì**: viết note, liên kết chéo, cập nhật mục lục, phát hiện mâu thuẫn. (Không phải "AI quản lý hết thay bạn" — bạn vẫn curate & quyết định; xem [`01-GIAI-THICH-KIEN-THUC.md`](01-GIAI-THICH-KIEN-THUC.md).)

## Bạn sẽ có gì sau ~15 phút
- Kho 3 lớp: `raw/` (nguồn gốc) → `wiki/` (note do AI bảo trì) → `CLAUDE.md`/`AGENTS.md` (luật).
- `index.md` (mục lục), `log.md` (nhật ký), `templates/`, một cụm note khởi đầu có liên kết để Graph đẹp ngay.
- Tuỳ chọn: repo GitHub + tự động sync. Mở bằng Obsidian để xem mạng kiến thức.

## Bắt đầu trong 15 phút
1. Cài [Claude Code](https://claude.com/claude-code) và [Obsidian](https://obsidian.md/) (miễn phí). Muốn sync nhiều máy thì cần **Git** + **GitHub** — chưa có cũng không sao (xem mục dưới).
2. Tạo một thư mục trống cho kho (vd `my-second-brain/`), mở terminal tại đó, chạy `claude`.
3. Mở [`02-SETUP-PROMPT.md`](02-SETUP-PROMPT.md), copy **toàn bộ** prompt trong khung và dán vào Claude Code.
4. Trả lời các câu hỏi (Claude sẽ hỏi bạn muốn setup mức Nhanh/Vừa/Sâu, rồi hỏi mảng kiến thức, lĩnh vực, git…). Claude tự dựng toàn bộ cấu trúc.
5. Mở Obsidian → *Open folder as vault* → chọn thư mục kho → bật **Graph View**.
6. Dùng hằng ngày theo [`04-HUONG-DAN-SU-DUNG.md`](04-HUONG-DAN-SU-DUNG.md).

## Chuẩn bị Git & token (chỉ cần nếu muốn sync GitHub)
Có thể để Claude hướng dẫn ngay trong lúc setup, hoặc làm trước:
1. **Cài Git** (kiểm tra: `git --version`):
   - macOS: `xcode-select --install` hoặc `brew install git`
   - Windows: https://git-scm.com/download/win · Linux: `sudo apt install git`
2. **Tạo tài khoản GitHub** (miễn phí): https://github.com/signup
3. **Lấy Personal Access Token (PAT):** https://github.com/settings/tokens → *Generate new token*.
   - Token *classic*: tick scope **`repo`**. (Hoặc *fine-grained*: **Administration** + **Contents** = Read/write, phạm vi **All repositories**.)
   - Copy token (`ghp_...` / `github_pat_...`) và giữ lại — đưa cho Claude khi setup.
4. Khi chạy SETUP-PROMPT, Claude dùng token tạo repo (private/public tuỳ bạn), push, và **lưu token an toàn vào trình quản lý mật khẩu hệ thống** (không để plaintext).

> ⚠️ Token = mật khẩu. Đừng commit/chia sẻ công khai. Nên revoke & tạo mới nếu token từng hiển thị ở nơi không an toàn.

## Nội dung kit (theo hành trình: hiểu → setup → dùng)
| File | Dùng để |
|---|---|
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

> Mẹo: không cần hiểu hết kỹ thuật. Cứ chạy SETUP-PROMPT, trả lời câu hỏi là có kho riêng. File "giải thích kiến thức" để đọc khi muốn hiểu sâu.

## Nguồn tham khảo
- LLM Wiki — Andrej Karpathy: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- Building a Second Brain — Tiago Forte
- Zettelkasten / How to Take Smart Notes — Sönke Ahrens
- Obsidian: https://obsidian.md/

---
*Miễn phí sử dụng cho mục đích học tập. Đóng góp/issue luôn được hoan nghênh.*
