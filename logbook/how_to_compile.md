---

## How to Compile This Markdown to PDF

### Method 1: Using VS Code (Recommended)

1. Install the **Markdown PDF** extension in VS Code
2. Open the markdown file
3. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
4. Type `Markdown PDF: Export (pdf)`
5. The PDF will be saved in the same directory

### Method 2: Using Command Line with Pandoc

```bash
# Install pandoc (if not installed)
# macOS: brew install pandoc
# Ubuntu: sudo apt-get install pandoc
# Windows: download from https://pandoc.org/installing.html

# Convert to PDF
pandoc "CL15_Group7_Logbook (2nd).md" -o "CL15_Group7_Logbook (2nd).pdf" --pdf-engine=xelatex -V geometry:margin=1in
```

### Method 3: Using Online Converter

1. Go to https://www.markdowntopdf.com/
2. Paste the markdown content
3. Click "Convert to PDF"
4. Download the PDF

### Method 4: Using Typora (If available)

1. Open the markdown file in Typora
2. Go to File → Export → PDF
3. Save the PDF

---

## Image Placeholder Summary

Before compiling to PDF, insert the following images:

| # | Location | Description |
|---|----------|-------------|
| 1 | Section 2, Phase 2 | MongoDB Atlas collections screenshot |
| 2 | Section 2, Phase 5 | Desktop homepage screenshot |
| 3 | Section 2, Phase 5 | Mobile responsive view screenshot |
| 4 | Section 3, Meeting #1 | Database schema diagram |
| 5 | Section 3, Meeting #3 | Combined classes display in timetable |
| 6 | Section 4, Decision 5 | Class selection UI for combined classes |
| 7 | Section 5, Issue 1 | MongoDB Atlas connection metrics |
| 8 | Section 5, Issue 4 | Gmail App Password generation page |
| 9 | Section 5, Issue 7 | MongoDB Atlas Network Access whitelist |
| 10 | Section 6, Change 5 | All MongoDB collections view |
| 11 | Section 7.3 | Browser dev tools showing API response |
| 12 | Section 7.3 | Mobile device photo showing app |
| 13 | Section 8.2, Step 3 | MongoDB Atlas cluster creation |
| 14 | Section 8.6 | Vercel deployment success log |

---
