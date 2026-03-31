📄 README.md — Kho Nhạc Karaoke (Single-file App)
🎤 Giới thiệu

Kho Nhạc Karaoke là web app cá nhân giúp lưu và quản lý các bài hát bạn hay hát.

Thiết kế để:

dùng ngay khi đi karaoke
không cần nhớ bài
không cần internet vẫn dùng được
🚀 Triết lý
⚡ Mở là chạy
🧠 Tối giản nhưng đủ dùng
💾 Local-first (không phụ thuộc server)
🔄 Sync chỉ là bổ sung, không bắt buộc
🧱 Kiến trúc
1 file index.html
+ Vanilla JS
+ localStorage (source of truth)
+ Supabase (optional sync)
+ Groq (optional AI autofill)
📦 Cách sử dụng
1. Mở app

Chỉ cần:

double click index.html

👉 Không cần:

npm
build
server
2. Thêm bài
Nhập tên bài
Enter → lưu ngay (Quick Add)
3. Autofill bằng AI (optional)
Nhập Groq API key trong Settings
Bấm “AI Autofill”

👉 AI chỉ hỗ trợ:

title
artist
genre
moods

❌ Không generate lyrics

4. Lyrics
Người dùng tự nhập/dán
Editable hoàn toàn
5. Karaoke Mode
Giao diện fullscreen
Tìm bài cực nhanh
1 tap:
copy tên bài
mở YouTube
6. Sync (optional)
Nhập Supabase URL + Anon key trong Settings
Bấm Sync
Push: local → Supabase  
Pull: Supabase → local

👉 Không auto sync
👉 Không login
👉 Không auth

7. Export / Import
Export → tải file JSON
Import → xác nhận trước khi overwrite
🧠 Data Model
Song {
  id,
  id_user,
  id_app,
  title,
  artist,
  artist_pref,
  composer,
  genre,
  moods[],
  difficulty,
  voice_range,
  key_transpose,
  personal_notes,
  self_rating,
  status,
  signature_lyrics[],
  full_lyrics,
  youtube_url,
  last_sung_at,
  sing_count,
  created_at,
  updated_at
}
👤 User System
const USER_ID = "RongLeo"
const APP_ID  = "karaoke"

👉 Không login
👉 Không multi-user

🔒 Data Safety
Luôn filter theo:
id_user
id_app
Import có guard:
không ghi đè app khác
không trộn data
🤖 AI (Groq)
Dùng cho:
Autofill metadata
Không dùng cho:
lyrics
nội dung cần độ chính xác cao
⚙️ Settings
Groq API Key
Supabase URL + Anon key
Theme (Dark / Light)
Stats cơ bản
🎯 Tính năng chính
✅ Quick Add
✅ Full CRUD + Personal Layer
✅ Karaoke Mode
✅ Random bài tủ
✅ Recently sung / Forgotten
✅ Search + Filter
✅ Dark mode
✅ Export / Import
✅ Supabase sync (optional)
✅ AI Autofill (optional)
⚠️ Giới hạn
Không có auth
Không multi-user
Không auto sync
AI không đảm bảo 100% chính xác
🧪 Use case thực tế
Đi karaoke → mở app → chọn bài trong 3 giây
Nghe được bài hay → Quick Add ngay
Không mạng → vẫn dùng bình thường
🧠 Ghi chú kỹ thuật
Supabase load lazy → không ảnh hưởng performance
localStorage là nguồn dữ liệu chính
Sync không block UI
🔥 Mục tiêu

Không phải app hoàn hảo
Mà là app dùng được ngay, trong tình huống thật

🐉 Tác giả

RongLeo system 🧠
Built for real usage, not demo.