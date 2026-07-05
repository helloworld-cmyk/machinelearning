# ML Quiz — Ôn tập trắc nghiệm

Ứng dụng web giúp ôn tập câu hỏi trắc nghiệm từ file Markdown. Cách dùng khuyến nghị: **VS Code + extension Live Preview** để mở app, **chụp màn hình từng cụm câu → AI trích xuất → làm lại trên app** để vừa nhập đề vừa tự kiểm tra.

---

## Mục lục

- [Bắt đầu nhanh (5 phút)](#bắt-đầu-nhanh-5-phút)
- [Workflow vừa làm vừa học](#workflow-vừa-làm-vừa-học)
- [Tổng quan](#tổng-quan)
- [Tính năng](#tính-năng)
- [Chạy project](#chạy-project)
- [Cấu trúc thư mục](#cấu-trúc-thư-mục)
- [Format file câu hỏi (.md)](#format-file-câu-hỏi-md)
- [Thêm đề mới](#thêm-đề-mới)
- [Trích xuất câu hỏi từ PDF/ảnh](#trích-xuất-câu-hỏi-từ-pdfảnh)
- [Đóng góp vào project](#đóng-góp-vào-project)
- [Ghi chú kỹ thuật](#ghi-chú-kỹ-thuật)

---

## Bắt đầu nhanh (5 phút)

### 1. Cài VS Code + Live Preview

1. Tải [Visual Studio Code](https://code.visualstudio.com/)
2. Mở **Extensions** (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Tìm và cài **[Live Preview](https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server)** — publisher **Microsoft** (`ms-vscode.live-server`)

> **Quan trọng:** Dùng đúng extension **Live Preview** của Microsoft, không phải "Live Server" (Ritwick Dey). Live Preview tích hợp sẵn trong VS Code, tự chạy HTTP server cục bộ — đủ để load `manifest.json` và ảnh `assets/`.

### 2. Mở project và preview app

1. **File → Open Folder** → chọn thư mục `MachineLearning`
2. Mở `index.html`
3. Nhấn **Show Preview** (icon mắt trên thanh editor) hoặc chuột phải → **Show Preview**

App mở trong panel preview của VS Code (hoặc trình duyệt ngoài). Đề trong `manifest.json` sẽ tự nạp.

### 3. Làm thử đề mẫu

Chọn `2020..2.md` ở sidebar → làm vài câu → bấm **Kiểm tra** để xem đúng/sai.

Tiếp theo: xem [Workflow vừa làm vừa học](#workflow-vừa-làm-vừa-học) — cách tự build ngân hàng câu hỏi từ đề gốc.

---

## Workflow vừa làm vừa học

Đây là quy trình chính mà project được thiết kế để hỗ trợ — **không cần scan cả đề một lần**, làm từng cụm nhỏ rồi tự test ngay.

```
Đề gốc (web/PDF)          VS Code                    Trình duyệt (AI)
      │                        │                              │
      │  Chụp màn 5–10 câu     │                              │
      ├───────────────────────►│  prompt.md + ảnh ───────────►│  AI trích xuất .md
      │                        │                              │
      │                        │  Dán vào file .md, lưu       │
      │                        │◄─────────────────────────────┤
      │                        │                              │
      │                        │  Live Preview → index.html   │
      │  Làm lại từng câu      │◄─────────────────────────────┤  Tự kiểm tra đáp án
      │  (vừa học vừa nhớ)     │                              │
      └────────────────────────┴──────────────────────────────┘
                    Lặp lại cụm câu tiếp theo
```

### Từng bước chi tiết

| Bước | Việc cần làm |
|------|----------------|
| **1. Chụp màn hình** | Mở đề gốc (LMS, PDF, slide…), chụp **5–10 câu một lần** — đủ để AI đọc rõ, không quá dài |
| **2. Gửi AI trên browser** | Mở ChatGPT / Claude / Gemini… Dán nội dung `prompt.md` (hoặc [Prompt ngắn](#trích-xuất-câu-hỏi-từ-pdfảnh)), **đính kèm ảnh chụp màn** |
| **3. Nhận file `.md`** | Copy output của AI, dán vào file `.md` trong VS Code (append sau câu cuối, hoặc tạo file mới) |
| **4. Sửa & lưu** | Kiểm tra nhanh format, sửa lỗi OCR, crop ảnh minh họa vào `assets/` nếu cần |
| **5. Cập nhật manifest** | Thêm đường dẫn file vào `manifest.json` (nếu đề mới) |
| **6. Tự test trên app** | Reload **Live Preview** → chọn đề → **làm lại từng câu vừa nhập** → bấm Kiểm tra |
| **7. Lặp** | Chụp cụm 5–10 câu tiếp theo, append vào cùng file `.md`, reload và làm tiếp |

### Vì sao làm theo cụm 5–10 câu?

- AI đọc ảnh chính xác hơn khi mỗi lần không quá nhiều chữ/bảng
- Bạn **vừa nhập vừa ôn** — làm ngay trên app giúp nhớ đáp án và phát hiện lỗi trích xuất sớm
- File `.md` lớn dần theo tiến độ học, không cần ngồi OCR cả đề trước khi bắt đầu ôn

### Mẹo khi tự test

- Câu có `[suy luận]` hoặc `[không chắc]` — ưu tiên làm trước, đối chiếu với đề gốc hoặc giải tay
- Sai trên app → kiểm tra lại ảnh chụp / dòng `ans:` trong `.md`, không phải lúc nào cũng lỗi app
- Dùng **Làm lại câu sai** trên app để ôn lại các câu vừa làm nhầm
- Giữ **Live Preview** và tab AI mở song song: chụp → dán AI → dán `.md` → reload preview

---

## Tổng quan

Project gồm hai phần chính:

| Thành phần | Mô tả |
|------------|--------|
| **`index.html`** | Giao diện làm bài: import đề, chọn đáp án, kiểm tra, xem kết quả |
| **File `.md`** | Ngân hàng câu hỏi theo format chuẩn (text + ảnh minh họa) |

Công cụ đi kèm:

| Công cụ | Vai trò |
|---------|---------|
| **VS Code + Live Preview** | Mở app, sửa file `.md`, xem kết quả ngay — **cách chạy khuyến nghị** |
| **`prompt.md`** | Prompt gửi AI khi chụp màn hình đề |
| **AI trên browser** | Trích xuất 5–10 câu/lần từ ảnh chụp màn |

Đề mẫu có sẵn: `2020-2/2020..2.md` (4 câu trắc nghiệm CSDL).

---

## Tính năng

- Import file `.md` / `.txt` bằng kéo-thả hoặc chọn file
- Tự động nạp đề từ `manifest.json` khi chạy qua HTTP server
- Hỗ trợ câu **một đáp án** và **nhiều đáp án** (`ans: A,B,D`)
- Hiển thị Markdown trong câu hỏi và đáp án (bảng, code, in đậm…)
- Ảnh minh họa qua dòng `img:` hoặc cú pháp Markdown `![...](...)`
- Lưu tiến trình làm bài vào `localStorage` (theo từng file)
- Điều hướng từng câu, kiểm tra tất cả, làm lại câu sai, reset tiến trình

---

## Chạy project

### Cách 1 — VS Code Live Preview (khuyến nghị)

Đây là cách chính khi làm theo [workflow vừa làm vừa học](#workflow-vừa-làm-vừa-học):

1. Cài extension **Live Preview** (`ms-vscode.live-server`) — xem [Bắt đầu nhanh](#bắt-đầu-nhanh-5-phút)
2. Mở folder project trong VS Code
3. `index.html` → **Show Preview**
4. Sửa file `.md` → reload preview (nút refresh trên preview) → làm lại câu vừa thêm

Live Preview tự chạy server cục bộ, nên:
- `manifest.json` load đề bundled
- Ảnh `assets/` hiển thị đúng
- Không cần cài Python/Node

**Layout gợi ý khi học:** chia màn hình 3 phần — tab đề gốc (chụp màn) | VS Code (`.md` + Live Preview) | tab AI trên browser.

### Cách 2 — HTTP server dòng lệnh

Nếu không dùng VS Code, chạy server tại thư mục gốc project:

```bash
cd MachineLearning

# Python 3
python3 -m http.server 8080

# hoặc Node.js (nếu đã cài npx)
npx serve .
```

Mở trình duyệt: **http://localhost:8080**

### Cách 3 — Mở trực tiếp file (không khuyến nghị)

Double-click `index.html` hoặc kéo thả file `.md` vào vùng import.

> **Hạn chế:** Trình duyệt chặn `fetch()` với `file://` — `manifest.json` và ảnh bundled **không tự load**. Chỉ phù hợp test nhanh đề không có ảnh.

---

## Cấu trúc thư mục

```
MachineLearning/
├── index.html          # Ứng dụng web (HTML + CSS + JS, không build step)
├── manifest.json       # Danh sách đề tự động load khi khởi động
├── prompt.md           # Prompt hướng dẫn AI trích xuất câu hỏi từ PDF/ảnh
├── readmd.md           # Tài liệu này
└── 2020-2/             # Ví dụ một bộ đề
    ├── 2020..2.md      # File câu hỏi
    └── assets/         # Ảnh minh họa của đề đó
        └── image.png
```

**Quy ước đặt tên đề:** mỗi bộ đề nên nằm trong một thư mục riêng, ví dụ `2021-1/`, `2022-final/`, chứa file `.md` và thư mục `assets/` cạnh nhau.

---

## Format file câu hỏi (.md)

Mỗi câu gồm **phần câu hỏi + các lựa chọn + dòng đáp án**. Các câu cách nhau bằng **một dòng trống** (khuyến nghị).

### Mẫu tối thiểu

```markdown
Câu 1: Thuật toán nào thuộc supervised learning?
A. K-Means
B. Linear Regression
C. Apriori
D. PCA
ans: B

Câu 2: Chọn tất cả đáp án đúng về overfitting.
A. Model đúng cao trên train, thấp trên test
B. Regularization có thể giảm overfitting
C. Overfitting do model quá đơn giản
D. Dropout giúp giảm overfitting
ans: A,B,D
```

### Quy tắc chi tiết

| Quy tắc | Chi tiết |
|---------|----------|
| Tiêu đề câu | Bắt đầu bằng `Câu [số]:` — parser tách block theo pattern này |
| Lựa chọn | Mỗi dòng `A.`, `B.`, `C.`, `D.` … (chữ in hoa + dấu chấm) |
| Đáp án | Dòng `ans: A` hoặc `ans: A,B,D` (nhiều đáp án, **không có khoảng trắng** sau dấu phẩy) |
| Một vs nhiều đáp án | App tự nhận diện: có dấu phẩy trong `ans:` → chế độ chọn nhiều |
| Ghi chú đáp án | `ans: B [suy luận]` hoặc `ans: A [không chắc]` — hiển thị cảnh báo trên UI |
| Ảnh (cách 1) | Dòng `img: assets/ten-anh.png` (đặt giữa câu hỏi và các đáp án) |
| Ảnh (cách 2) | Markdown inline: `![mô tả](assets/ten-anh.png)` trong nội dung câu hỏi |
| Markdown | Bảng, code block, **in đậm**, HTML tùy chỉnh đều được render qua thư viện `marked` |
| Nội dung nhiều dòng | Có thể xuống dòng trong câu hỏi hoặc trong từng đáp án (ví dụ bảng trong đáp án A, B, C, D) |

### Ví dụ có ảnh và bảng

Xem file mẫu `2020-2/2020..2.md` — bao gồm bảng quan hệ, code SQL, và ảnh `assets/image.png`.

---

## Thêm đề mới

### Bước 1 — Tạo thư mục và file

```bash
mkdir -p ten-de-moi/assets
# Tạo ten-de-moi/ten-de-moi.md theo format ở trên
# Copy ảnh vào ten-de-moi/assets/ nếu cần
```

### Bước 2 — Đăng ký trong manifest (tùy chọn)

Mở `manifest.json` và thêm đường dẫn file `.md`:

```json
{
  "quizzes": [
    "2020-2/2020..2.md",
    "ten-de-moi/ten-de-moi.md"
  ]
}
```

Mỗi entry có thể là chuỗi đường dẫn, hoặc object `{ "path": "..." }`.

### Bước 3 — Kiểm tra

1. Mở **Live Preview** (xem [Chạy project](#chạy-project))
2. Reload preview — đề mới xuất hiện ở sidebar
3. **Làm lại từng câu vừa thêm** — đây là bước tự test bắt buộc trong workflow
4. Kiểm tra ảnh hiển thị và đáp án đúng/sai

### Import thủ công (không cần manifest)

Kéo file `.md` vào vùng import trên sidebar. File được lưu vào `localStorage` của trình duyệt — không ghi vào repo trừ khi bạn commit file `.md` gốc.

---

## Trích xuất câu hỏi từ PDF/ảnh

File **`prompt.md`** chứa hướng dẫn đầy đủ để gửi AI trên browser. Cách dùng thực tế nhất: **chụp màn hình 5–10 câu**, không upload cả file PDF một lần.

### Quy trình (khớp workflow vừa làm vừa học)

1. **Chụp màn hình** 5–10 câu từ đề gốc (Windows: `Win+Shift+S` · macOS: `Cmd+Shift+4`)
2. Mở AI trên browser (ChatGPT, Claude, Gemini…)
3. Dán nội dung `prompt.md` — hoặc prompt ngắn bên dưới
4. **Đính kèm ảnh chụp màn** (paste trực tiếp hoặc upload)
5. Copy output `.md` → dán vào file trong VS Code
6. Lưu → reload **Live Preview** → **làm lại các câu vừa nhập** để tự test
7. Lặp với cụm câu tiếp theo

### Prompt ngắn (copy-paste nhanh)

```
Trích xuất tất cả câu hỏi trắc nghiệm từ ảnh chụp màn đính kèm theo format:

Câu [số]: [nội dung]
A. ...
B. ...
C. ...
D. ...
ans: [A hoặc A,B,C nếu nhiều đáp án đúng]

Quy tắc:
- Mỗi lựa chọn một dòng (A. B. C. D.)
- ans: một đáp án → ans: B | nhiều đáp án → ans: A,C,D (cách nhau bằng dấu phẩy, không khoảng trắng)
- Giữ nguyên nội dung gốc, sửa lỗi OCR nếu cần
- Nếu không có đáp án trong đề thì giải và ghi ans: ... [suy luận]
- Cách mỗi câu bằng một dòng trống
- Chỉ xuất câu hỏi, không giải thích thêm
```

Chi tiết đầy đủ (ảnh minh họa, câu đặc biệt, bảng…): xem file `prompt.md`.

### Sau khi AI trả kết quả

- Review đáp án — ưu tiên sửa dòng `[suy luận]` / `[không chắc]`
- Ảnh trong câu hỏi: crop lưu vào `assets/`, thêm dòng `img: assets/ten-anh.png`
- Append vào file `.md` hiện có (giữ số câu liên tục)
- **Tự test ngay** trên Live Preview trước khi chụp cụm câu tiếp theo

---

## Đóng góp vào project

Mọi người đều có thể đóng góp theo các hướng sau.

### 1. Thêm / sửa câu hỏi

- Thêm bộ đề mới (thư mục + `.md` + `assets/`)
- Sửa lỗi chính tả, OCR, hoặc đáp án sai trong file `.md` có sẵn
- Bổ sung ảnh minh họa còn thiếu

**Checklist trước khi gửi PR:**

- [ ] Mỗi câu có đủ `Câu N:`, các lựa chọn `A.`–`D.` (hoặc hơn), và `ans:`
- [ ] Đáp án nhiều lựa chọn viết dạng `ans: A,C` (không space sau dấu phẩy)
- [ ] Ảnh nằm trong `assets/` cùng thư mục với file `.md`
- [ ] Đã thêm entry vào `manifest.json` (nếu muốn auto-load)
- [ ] Đã test qua **Live Preview** (hoặc local server) — làm lại từng câu, ảnh hiện, đáp án đúng

### 2. Cải thiện ứng dụng (`index.html`)

Toàn bộ frontend nằm trong một file `index.html`. Khi sửa:

- Giữ tương thích format `.md` hiện tại (không phá parser `parseMarkdown`)
- Không thêm build step trừ khi team thống nhất — ưu tiên giữ project chạy được bằng cách mở file / server tĩnh
- Test trên Chrome/Firefox/Safari nếu thay đổi UI lớn

### 3. Cải thiện `prompt.md`

- Bổ sung ví dụ edge case (câu True/False, câu ghép, công thức toán…)
- Làm rõ quy tắc OCR cho môn học cụ thể

### Quy trình Git gợi ý

```bash
git checkout -b them-de-2021-ky-1
# ... chỉnh sửa ...
git add ten-de-moi/ manifest.json
git commit -m "Thêm đề 2021 kỳ 1 (50 câu CSDL)"
git push origin them-de-2021-ky-1
# Tạo Pull Request trên GitHub
```

**Commit message:** viết tiếng Việt hoặc tiếng Anh ngắn gọn, mô tả *nội dung* đóng góp (ví dụ: `Sửa đáp án câu 12 trong 2020-2`, `Thêm giao diện dark mode`).

---

## Ghi chú kỹ thuật

### Parser câu hỏi

Logic nằm trong hàm `parseMarkdown()` trong `index.html`:

- Tách nội dung theo regex `\n(?=Câu\s+\d+\s*:)`
- Đọc lần lượt: `ans:`, `img:`, `A.`–`Z.`, phần còn lại gộp vào câu hỏi
- Câu không có lựa chọn nào sẽ bị bỏ qua

### Lưu trữ local

| Key | Nội dung |
|-----|----------|
| `ml-quiz-v1-files` | Metadata các file đã import |
| `ml-quiz-v1-content-{id}` | Nội dung `.md` gốc |
| `ml-quiz-v1-progress-{id}` | Tiến trình làm bài (đáp án đã chọn, câu đã kiểm tra…) |

`id` được tạo từ tên file (ký tự đặc biệt thay bằng `_`).

Xóa tiến trình: dùng nút **Reset tiến trình** trên app, hoặc xóa dữ liệu site trong cài đặt trình duyệt.

### Phụ thuộc bên ngoài (CDN)

- [marked.js](https://marked.js.org/) — render Markdown
- Google Fonts (DM Sans, JetBrains Mono)

Cần kết nối mạng lần đầu load trang để tải CDN. Không có npm/package manager trong repo.

### Giới hạn đã biết

- Cần HTTP server để auto-load `manifest.json` và ảnh bundled
- File import thủ công **không** tự resolve ảnh từ `assets/` trên disk (chỉ lưu text vào localStorage) — ảnh chỉ hoạt động đầy đủ với đề load qua `manifest.json` hoặc khi `.md` không cần ảnh
- Không có backend — không đồng bộ tiến trình giữa thiết bị

---

## Liên hệ & hỗ trợ

- Chưa cài Live Preview: xem [Bắt đầu nhanh](#bắt-đầu-nhanh-5-phút) — extension `ms-vscode.live-server`
- Không biết bắt đầu từ đâu: làm theo [Workflow vừa làm vừa học](#workflow-vừa-làm-vừa-học)
- Gặp lỗi parse: kiểm tra format `.md` theo [Format file câu hỏi](#format-file-câu-hỏi-md)
- Ảnh không hiện: dùng Live Preview (không mở `file://` trực tiếp), kiểm tra đường dẫn `assets/...`
- Muốn thêm đề: xem [Thêm đề mới](#thêm-đề-mới) và [Đóng góp vào project](#đóng-góp-vào-project)
