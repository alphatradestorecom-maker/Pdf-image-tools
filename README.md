body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f8f9fa; }
header { background: #007bff; color: white; padding: 20px; text-align: center; }
footer { background: #343a40; color: white; text-align: center; padding: 10px; margin-top: 20px; }
.tool-container { max-width: 800px; margin: 20px auto; padding: 20px; background: white; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
.btn { margin: 5px; }
.ads-placeholder { background: #e9ecef; height: 100px; text-align: center; padding: 20px; margin: 20px 0; } /* For AdSense later */
// Simple navigation toggle for mobile (if needed)
document.addEventListener('DOMContentLoaded', function() {
    // Add any shared logic, e.g., analytics placeholder
    console.log('Page loaded');
});
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Free PDF & Image Tools - Merge, Split, Convert Online</title>
    <meta name="description" content="Free online tools for PDF merging, splitting, compressing, and image resizing, cropping, converting. No downloads needed. Fast and secure.">
    <meta name="keywords" content="PDF tools, image tools, merge PDF, split PDF, compress image">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="css/styles.css">
</head>
<body>
    <header>
        <h1>Free PDF & Image Tools</h1>
        <p>All processing in your browser - no uploads to servers!</p>
    </header>
    <div class="container mt-4">
        <div class="ads-placeholder">AdSense Banner Placeholder</div>
        <h2>PDF Tools</h2>
        <div class="row">
            <div class="col-md-4"><a href="tools/pdf-merge.html" class="btn btn-primary">PDF Merge</a></div>
            <div class="col-md-4"><a href="tools/pdf-split.html" class="btn btn-primary">PDF Split</a></div>
            <div class="col-md-4"><a href="tools/pdf-to-jpg.html" class="btn btn-primary">PDF to JPG</a></div>
            <div class="col-md-4"><a href="tools/jpg-to-pdf.html" class="btn btn-primary">JPG to PDF</a></div>
            <div class="col-md-4"><a href="tools/pdf-compress.html" class="btn btn-primary">PDF Compress</a></div>
        </div>
        <h2 class="mt-4">Image Tools</h2>
        <div class="row">
            <div class="col-md-4"><a href="tools/image-compress.html" class="btn btn-primary">Image Compressor</a></div>
            <div class="col-md-4"><a href="tools/image-resize.html" class="btn btn-primary">Image Resizer</a></div>
            <div class="col-md-4"><a href="tools/jpg-to-png.html" class="btn btn-primary">JPG to PNG</a></div>
            <div class="col-md-4"><a href="tools/png-to-jpg.html" class="btn btn-primary">PNG to JPG</a></div>
            <div class="col-md-4"><a href="tools/image-cropper.html" class="btn btn-primary">Image Cropper</a></div>
        </div>
        <div class="ads-placeholder">AdSense Banner Placeholder</div>
    </div>
    <footer>
        <p>&copy; 2023 Free Tools. <a href="about.html">About</a> | <a href="privacy.html">Privacy</a> | <a href="terms.html">Terms</a> | <a href="contact.html">Contact</a></p>
    </footer>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script src="js/common.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PDF Merge Tool - Free Online PDF Merger</title>
    <meta name="description" content="Merge multiple PDF files into one for free. Upload PDFs, combine them instantly in your browser, and download. No software needed.">
    <meta name="keywords" content="merge PDF, combine PDF, free PDF merger">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="../css/styles.css">
    <script src="https://unpkg.com/pdf-lib@1.17.1/dist/pdf-lib.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/file-saver@2.0.5/dist/FileSaver.min.js"></script>
</head>
<body>
    <header>
        <h1>PDF Merge Tool</h1>
        <a href="../index.html">Back to Home</a>
    </header>
    <div class="tool-container">
        <div class="ads-placeholder">AdSense Banner Placeholder</div>
        <h2>How to Use</h2>
        <p>Upload multiple PDF files. Click 'Merge' to combine them into one PDF. Download the result. All processing is local—no data sent to servers.</p>
        <input type="file" id="pdfFiles" multiple accept=".pdf" class="form-control mb-3">
        <button id="mergeBtn" class="btn btn-success">Merge PDFs</button>
        <div id="status"></div>
        <div class="ads-placeholder">AdSense Banner Placeholder</div>
    </div>
    <footer>
        <p>&copy; 2023 Free Tools. <a href="../about.html">About</a> | <a href="../privacy.html">Privacy</a> | <a href="../terms.html">Terms</a> | <a href="../contact.html">Contact</a></p>
    </footer>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script src="../js/common.js"></script>
    <script>
        // PDF Merge Logic (from tools.js)
        document.getElementById('mergeBtn').addEventListener('click', async () => {
            const files = document.getElementById('pdfFiles').files;
            if (files.length < 2) return alert('Select at least 2 PDFs');
            const mergedPdf = await PDFLib.PDFDocument.create();
            for (const file of files) {
                const pdfBytes = await file.arrayBuffer();
                const pdf = await PDFLib.PDFDocument.load(pdfBytes);
                const pages = await mergedPdf.copyPages(pdf, pdf.getPageIndices());
                pages.forEach(page => mergedPdf.addPage(page));
            }
            const mergedBytes = await mergedPdf.save();
            saveAs(new Blob([mergedBytes]), 'merged.pdf');
            document.getElementById('status').innerText = 'Merged successfully!';
        });
    </script>
</body>
</html>


# Pdf-image-tools
Free online PDF and Image tools built using HTML, CSS and JavaScript.
