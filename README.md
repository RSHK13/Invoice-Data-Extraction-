## Invoice Data Extraction 
This project aims to extract critical information (e.g., invoice numbers, total amounts, item descriptions) from invoices in both native and scanned PDFs. It outputs structured data as CSV files.
# Methods Used
Method 1: Traditional Extraction
This method extracts text using pdfplumber for native PDFs and pytesseract for scanned PDFs. The extracted text is cleaned and processed using regular expressions to identify key invoice fields. The code performs the following tasks:

Text Extraction:

Native PDFs: pdfplumber extracts text directly.

Scanned PDFs: pytesseract performs OCR to extract text from images.

Text Cleaning: Removes extra whitespace to improve extraction accuracy.

Pattern Matching: Uses regular expressions to extract key fields such as:

- Invoice Number
- Total Amount
- GSTIN
- Customer Details
- Item-wise information (name, rate, quantity, tax, etc.)
  
CSV Generation: Stores the extracted data in structured CSV files.

Method 2: Using Gemini-1.5-Flash Model
The second method leverages the Gemini-1.5-Flash model for improved extraction, especially for:

- Noisy, handwritten, or poorly scanned documents.
- Complex layouts that might confuse traditional methods.
- This model enhances:

Accuracy in field identification (e.g., mismatched invoice dates or tax information).
Handling of various languages and formatting styles.
Itemized extraction when tables are poorly aligned or split across lines.

# Outputs
The project generates the following output files:

invoice_data.csv: Contains invoice-level summary fields

items_data.csv: Contains detailed information for each item in the invoices, along wiht the inovice_id
