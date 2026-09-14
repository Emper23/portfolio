# Znith — Profile

โปรไฟล์การ์ดหน้าเดียว (static HTML/CSS/JS) ไม่มี backend
พร้อม deploy บนโฮสต์ static ฟรีได้ทันที

## โครงสร้างไฟล์

| ไฟล์ | หน้าที่ |
|---|---|
| `index.html` | หน้าหลัก + สคริปต์ทั้งหมด |
| `style.css` | สไตล์การ์ดโปรไฟล์ |
| `*.webp` | รูปอวาตาร์ |
| `*.jpg` | รูปพื้นหลัง |
| `*.mp3` | เพลงพื้นหลัง |
| `_headers` | cache headers (Cloudflare Pages / Netlify) |

## รัน local

เปิด `index.html` ด้วยเบราว์เซอร์ได้เลย หรือใช้เซิร์ฟเวอร์เล็ก ๆ:

```bash
python -m http.server 8000
# เปิด http://localhost:8000
```

## Deploy (เลือกอย่างใดอย่างหนึ่ง)

### 1) Netlify Drop — ง่ายสุด ไม่ต้องใช้ Git

1. เข้า https://app.netlify.com/drop
2. ลากโฟลเดอร์ทั้งหมดวางในเบราว์เซอร์
3. ได้ลิงก์ออนไลน์ทันที

### 2) Cloudflare Pages — เร็วสุด / CDN ฟรี (แนะนำ)

1. push โปรเจกต์ขึ้น GitHub
2. Cloudflare Dashboard → Workers & Pages → Create → Pages
3. เชื่อม repo → **Build command:** เว้นว่าง · **Output directory:** `/`
4. Deploy → ได้ลิงก์ `ชื่อคุณ.pages.dev`

### 3) Vercel

1. push ขึ้น GitHub
2. vercel.com → Add New → Project → import repo
3. Framework Preset: **Other** → Deploy

### 4) GitHub Pages

1. push ขึ้น repo
2. Settings → Pages → Branch: `main` / root → Save
3. ได้ลิงก์ `username.github.io/repo`

## หมายเหตุ

- ต้องมีไฟล์รูป `ea5cd0023874321878b7c3d2b66163dc.webp` สำหรับรูปอวาตาร์ และ `pourya-gohari-Y6qw1cZL4so-unsplash.jpg` สำหรับพื้นหลัง
- เพลงพื้นหลังเริ่มเล่นหลังผู้ใช้กดปุ่ม "ENTER PORTFOLIO" (ตามนโยบาย autoplay ของเบราว์เซอร์)
- ทุก path เป็น relative จึงใช้ได้ทั้ง root domain และ subpath
