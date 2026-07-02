# 📄 Skripsi Page Numbering & Footer Tool

An interactive, client-side web application designed to automatically format page numbers and department footers on PDF drafts according to the official guidelines of **Politeknik Negeri Jakarta (PNJ)**.

🚀 **Live Deployment:** [https://tamatimtam.github.io/skripsi-formatter/](https://tamatimtam.github.io/skripsi-formatter/)

---

## ✨ Features

- **📂 Local Processing:** PDF files are processed entirely in the browser using `pdf-lib`. No files are uploaded to any server, keeping your draft confidential and secure.
- **🔢 Custom Page Configurations:**
  - Separate start pages for front matter (Roman numerals: `i, ii, iii...`) and main body (Arabic numerals: `1, 2, 3...`).
  - Ability to hide page numbers on specific pages (e.g., Cover, Lembar Pengesahan).
- **📘 Smart Chapter (BAB) Detection:**
  - Auto-hides the department footer on BAB opening pages.
  - Automatically shifts page numbers to the **bottom-center** on BAB opening pages, and keeps them at the **top corners** (alternating left/right for even/odd pages) on other main body pages.
- **🖊️ Department Footer Placement:**
  - Automatically draws: `"Jurusan Teknik Informatika dan Komputer – Politeknik Negeri Jakarta"` right-aligned at the bottom of standard pages.
  - Prevents overlap by placing the bottom-center page number clearly below the department footer.
- **🎯 Pixel-Level Calibration:** Real-time adjustable sliders/inputs to fine-tune offsets for margins (X/Y) to fit any custom document layout.
- **👀 Real-Time Preview:** Includes a built-in interactive PDF viewer to instantly preview layout changes before saving.

---

## 🛠️ Technology Stack

- **Frontend Framework:** Vanilla HTML5 & JavaScript
- **CSS Styling:** [Tailwind CSS](https://tailwindcss.com) (CDN-loaded)
- **PDF Manipulation:** [pdf-lib](https://pdf-lib.js.org/) (for client-side drawing and PDF rendering)
- **Font Rendering:** [@pdf-lib/fontkit](https://github.com/Hopding/pdf-lib) (used to register custom TrueType fonts)
- **Typography:** Arial Bold (`ArialBold.ttf`) local font asset embedded dynamically for high-fidelity rendering.

---

## 🚀 How to Run Locally

Since this tool is entirely serverless and client-side, you can run it on your local machine with ease:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Tamatimtam/skripsi-formatter.git
   cd skripsi-formatter
   ```
2. **Serve the project:**
   Simply double-click `index.html` to open it in your browser, or run a simple local server:
   ```bash
   # Using Python 3
   python3 -m http.server 8000
   
   # Using Node.js (http-server)
   npx http-server
   ```
3. Open your browser and navigate to `http://localhost:8000`.

---

## 📜 Usage Guidelines

1. **Upload Draft:** Click **Choose File** and select your draft PDF.
2. **Configure Ranges (Physical Pages):**
   - **Front Matter Start Page:** The page number where Roman numerals should begin (typically page 2, assuming page 1 is the cover).
   - **Hide Roman Page Numbers:** Enter page numbers to hide (e.g., Cover page).
   - **Main Body Start:** The physical page number where the main body starts (usually Bab 1).
   - **Chapter Pages:** List all physical page numbers containing Chapter (BAB) openings, separated by commas (e.g., `10, 25, 42`).
3. **Set Footer Ranges:** Specify the start and end physical pages for the department footer text.
4. **Apply Changes:** Click **Apply & Update Preview** to generate and view the updated document.
5. **Download:** Click **Download Final PDF** to save your styled file.

---

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.
