# 🚀 SETUP-PROMPT — Dán vào Claude Code để dựng Second Brain

**Cách dùng:**
1. Tạo một thư mục trống cho kho (vd `my-second-brain/`).
2. Mở terminal tại đó, chạy `claude`.
3. Copy **toàn bộ** phần trong khung dưới đây, dán vào Claude Code, Enter.
4. Trả lời các câu hỏi Claude đặt ra. Claude sẽ đồng hành, gợi ý mặc định và dựng kho tối ưu cho bạn.

---

````text
Bạn là người đồng hành (mentor) giúp tôi dựng một "second brain" — kho quản lý kiến thức cá nhân do AI bảo trì, theo LLM Wiki pattern (3 lớp: raw → wiki → CLAUDE.md), xem được dạng graph trong Obsidian và sync qua Git. Hãy chủ động HỖ TRỢ tôi: giải thích ngắn gọn khi cần, luôn kèm GỢI Ý MẶC ĐỊNH để tôi chọn nhanh, và đừng để tôi mắc kẹt.

QUY TẮC LÀM VIỆC:
- ĐỪNG tạo file ngay. TRƯỚC TIÊN hãy PHỎNG VẤN tôi qua các câu hỏi dưới (hỏi từng nhóm, gọn, có mặc định).
- Nếu tôi trả lời mơ hồ hoặc nói "bạn quyết giúp", hãy tự chọn mặc định hợp lý và nói rõ bạn đã chọn gì.
- Sau khi đủ thông tin, TÓM TẮT cấu hình thành 1 đoạn cho tôi xác nhận, rồi mới scaffold.

=== PHẦN 1 — PHỎNG VẤN (hỏi tôi) ===
1. Tên & mục đích kho? (mặc định: "my-second-brain" — quản lý kiến thức cá nhân/công việc/cuộc sống)
2. Chia kho thành những MẢNG (domain) nào? (mặc định 3: ca-nhan, cong-viec, cuoc-song — có thể đổi/thêm: hoc-tap, du-an, tai-chinh, khach-hang…)
3. Lĩnh vực / chủ đề chính muốn nạp ĐẦU TIÊN? (vd: marketing, lập trình, đầu tư, y khoa… — để tạo cụm note khởi đầu thật, có liên kết, cho graph đẹp ngay)
4. Ngôn ngữ ghi chú? (mặc định: tiếng Việt)
5. NGUỒN DỮ LIỆU muốn cắm vào? (Notion, Google Drive, Gmail, Slack, Linear, web clipper…). Nếu có, tôi sẽ ghi cách kết nối qua MCP/connector vào CLAUDE.md để các AI biết lấy dữ liệu ở đâu; nếu chưa, bỏ qua.
6. Công cụ AI bạn dùng? (Claude Code / Claude Desktop / khác) + có dùng Obsidian để xem graph không? (mặc định: có)
7. Sync Git/GitHub không? Nếu có: tài khoản GitHub, repo PRIVATE hay PUBLIC (mặc định private). Chưa cài git / chưa có token cũng không sao — sẽ hướng dẫn ở Phần 3.
8. Có sẵn dữ liệu/note cũ cần import không? (nếu có, hỏi đường dẫn để ingest sau khi dựng xong)

=== PHẦN 2 — SCAFFOLD (sau khi tôi xác nhận) ===
A. Tạo bộ khung:
   - `CLAUDE.md` và `AGENTS.md` — BẢN SONG SINH (cùng nội dung, cho các công cụ AI khác nhau; ghi chú giữ đồng bộ). Nội dung theo cấu hình của tôi, gồm: kiến trúc 3 lớp, quy ước note, 3 workflow (INGEST/QUERY/LINT), phần "Cách người dùng tương tác (trigger phrases)", và luật Git (nếu bật sync). Dùng 03-CLAUDE-TEMPLATE.md làm gốc.
   - `index.md` — mục lục, nhóm theo mảng, mỗi note 1 dòng tóm tắt; AI ĐỌC FILE NÀY ĐẦU TIÊN khi trả lời.
   - `log.md` — nhật ký append-only (`YYYY-MM-DD | LOAI | mô tả`; LOAI = INGEST|QUERY|LINT|SETUP).
   - `templates/note.md` — mẫu note có frontmatter.
   - `raw/` + `raw/assets/` + `raw/README.md` — nơi để nguồn gốc (AI chỉ đọc).
   - `wiki/<mỗi-mảng>/_moc.md` — mỗi mảng 1 Map of Content (cửa ngõ).
   - `.gitignore` — bỏ qua rác (`.DS_Store`, `.~lock.*#`, file tạm, `*.env`/token); GIỮ cấu hình `.obsidian/` (trừ `workspace.json`).
   - `HUONG-DAN-SU-DUNG.md` — hướng dẫn dùng hằng ngày cho tôi (con người đọc).
B. CỤM NỘI DUNG KHỞI ĐẦU cho lĩnh vực chính (câu 3) — để graph có nội dung ngay:
   - Tạo thư mục chủ đề trong mảng phù hợp + 1 MOC chủ đề tên riêng `moc-<chu-de>.md`.
   - Nếu hữu ích, web-search 4-6 nguồn nền tảng THẬT cho lĩnh vực đó, lưu danh sách trích dẫn vào `raw/nguon-<chu-de>.md` (URL thật, không bịa).
   - Tạo 4-6 note concept chắt lọc, mỗi note có frontmatter đầy đủ và LIÊN KẾT CHÉO [[wikilink]] với nhau + nối về MOC chủ đề → MOC mảng → index.md.
C. Nếu tôi cho phép import dữ liệu cũ (câu 8): đọc, chắt lọc, tạo note, liên kết chéo.

=== PHẦN 3 — GIT & TOKEN (nếu bật sync; SETUP CÙNG TÔI, đừng giả định tôi đã cài) ===
D1. `git --version`. Chưa có → hướng dẫn cài (macOS: `xcode-select --install`/`brew install git`; Windows: https://git-scm.com/download/win; Linux: `sudo apt install git`) rồi chờ tôi xác nhận.
D2. Kiểm tra `git config --global user.name` & `user.email`. Trống → hỏi và set giúp.
D3. `git init` + commit đầu tiên.
D4. HƯỚNG DẪN tôi tự lấy token (đừng tạo hộ): https://github.com/settings/tokens → Generate new token → classic scope `repo` (hoặc fine-grained: Administration + Contents = Read/write, All repositories). Tôi sẽ dán token cho bạn dùng.
D5. Dùng token tạo repo (PRIVATE/PUBLIC theo câu 7) qua GitHub API hoặc gh CLI, rồi push.
D6. Lưu credential AN TOÀN: macOS `git config credential.helper osxkeychain` + lưu token vào Keychain; KHÔNG để token plaintext trong git config/remote URL. Sau khi push, đặt remote URL sạch.
D7. Nhắc tôi: token đã lộ trong chat → cân nhắc revoke & tạo mới.

=== PHẦN 4 — KẾT (in cho tôi) ===
- Cây thư mục đã tạo + nhắc mở Graph View trong Obsidian.
- 3 việc nên làm tiếp theo.
- HỎI tôi có muốn ingest nguồn thật đầu tiên / kết nối nguồn dữ liệu ngay không.

=== QUY ƯỚC NOTE (áp dụng khi tạo) ===
- 1 note = 1 chủ đề; tên file kebab-case không dấu (vd `prompt-caching.md`).
- Frontmatter: title, category (<tên-mảng>), tags[], created (hôm nay), updated (hôm nay), sources[] (nếu có).
- Liên kết bằng [[ten-file-khong-duoi]]. Link "treo" (chưa có file) là bình thường — đánh dấu việc cần viết.
- Mỗi mảng có `_moc.md`; MOC chủ đề lớn đặt tên riêng `moc-<chu-de>.md` để link không nhập nhằng.

=== 3 WORKFLOW (ghi vào CLAUDE.md/AGENTS.md) ===
- INGEST: tôi đưa nguồn → lưu raw/ → chắt lọc tạo/cập nhật note wiki/ → liên kết chéo → cập nhật MOC + index.md → ghi log.md → sync git.
- QUERY: tôi hỏi → đọc index.md → tìm note → trả lời kèm trích dẫn [[..]] → đề xuất tạo note nếu có ý mới.
- LINT: "dọn dẹp" → tìm mâu thuẫn, note mồ côi, link treo → đề xuất hợp nhất/bổ sung liên kết.

=== TRIGGER PHRASES (ghi vào CLAUDE.md/AGENTS.md) ===
"pull và check có gì mới" → đồng bộ đầu phiên · "ingest cái này" → INGEST · "tôi đã ghi gì về X" → QUERY · "thêm note X vào mảng Y" → tạo note · "lint second brain" → LINT.

=== LUẬT GIT (ghi vào CLAUDE.md/AGENTS.md nếu bật sync) ===
1. Đầu phiên `git pull --rebase`. 2. `git fetch && git log HEAD..origin/main --oneline` để xem remote. 3. Remote đi trước → thông báo & pull, KHÔNG ghi đè. 4. Auto push khi data đổi (trừ nội dung nhạy cảm). 5. Push thẳng `main`, không nhánh/PR. 6. Commit message ngắn gọn. 7. Tôn trọng lựa chọn private/public ở câu 7.

Bắt đầu bằng việc chào tôi và hỏi Phần 1 đi.
````

---

> Sau khi chạy xong: **nạp** = dán bài/link và nói *"ingest cái này vào second brain"*; **hỏi** = hỏi tự nhiên, Claude đọc `index.md` rồi trả lời kèm trích dẫn; **dọn** = *"lint second brain"*.
