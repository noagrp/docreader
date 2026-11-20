# DocReader

A static, read-only local document reader and optional PDF exporter, adapted from [a3syonline/txt2pdf](https://github.com/a3syonline/txt2pdf).

## Features

- Text: TXT, LOG, MD, JSON
- Delimited tables: CSV, TSV
- Word: DOCX (via bundled Mammoth; HTML cleaned with DOMPurify)
- Spreadsheets: XLSX, XLS, ODS (via SheetJS; worksheet tabs)
- PDFs: browser's native PDF viewer
- Search in the currently displayed text, Word document or worksheet
- A3 / A4 / A5 / US Letter; portrait / landscape; adjustable margins and text sizes
- PDF preview before downloading; split wide tables or fit all columns to a page\n- Optional first-row repetition as a header (disabled by default, because the first row may contain data)\n- No login or server-side file upload; selected files are read in the browser

## Important limits

- Files are limited to 30 MB. Spreadsheet and CSV previews are limited to 2,000 rows and 100 columns. PDF export includes only those displayed rows and columns.\n- PDF export produces rendered pages (often image-based); selectable or searchable PDF text is not guaranteed. Large or unusually tall table rows may still need different layout settings.\n- Fit-all-columns can produce tiny text on very wide sheets. Split-wide-tables is the recommended default for legibility.
- DOCX and spreadsheets are **readers**, not exact reproductions of Microsoft Office formatting. Macros are never executed; Excel formulas are displayed from available cached values, not recalculated.
- PDF export from text/Word/spreadsheets uses the browser's html2pdf/html2canvas pipeline. Its output may be image-based and may not preserve selectable PDF text. For existing PDFs, Export PDF downloads the unchanged original.
- The PDF viewer uses the browser's own built-in PDF support. Document search is not available inside an embedded PDF.
- SheetJS and DOMPurify load from pinned external CDNs. Internet access is required to load these dependencies, although selected document contents are handled locally. The two original libraries (Mammoth and html2pdf) are retained as bundled files.
- CSV/TSV are parsed into display tables only, not edited.
- Drag and drop is supported.

## Repository

App logic and styling remain in `index.html` without additional helper modules. The original local documents are not modified.
