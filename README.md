# DocReader

A static, read-only local document reader and optional PDF exporter, adapted from [a3syonline/txt2pdf](https://github.com/a3syonline/txt2pdf).

## Features

- Text: TXT, LOG, MD, JSON
- Delimited tables: CSV, TSV
- Word: DOCX (via bundled Mammoth; HTML cleaned with DOMPurify)
- Spreadsheets: XLSX, XLS, ODS (via SheetJS; worksheet tabs)
- PDFs: browser's native PDF viewer
- Search in the currently displayed text, Word document or worksheet
- A4 / US Letter / A5 and portrait / landscape PDF export
- No login or server-side file upload; selected files are read in the browser

## Important limits

- Large files are limited to 30 MB. Spreadsheet previews are limited to the first 2,000 rows and 100 columns of the used range. PDF export includes the *visible preview* for spreadsheets, not necessarily every row.
- DOCX and spreadsheets are **readers**, not exact reproductions of Microsoft Office formatting. Macros are never executed; Excel formulas are displayed from available cached values, not recalculated.
- PDF export from text/Word/spreadsheets uses the browser's html2pdf/html2canvas pipeline. Its output may be image-based and may not preserve selectable PDF text. For existing PDFs, Export PDF downloads the unchanged original.
- The PDF viewer uses the browser's own built-in PDF support. Document search is not available inside an embedded PDF.
- SheetJS and DOMPurify load from pinned external CDNs. Internet access is required to load these dependencies, although selected document contents are handled locally. The two original libraries (Mammoth and html2pdf) are retained as bundled files.
- CSV/TSV are parsed into display tables only, not edited.
- Drag and drop is supported.

## Repository

All app logic and styles live in `index.html` to avoid unnecessary layering. The source repository remains unchanged.
