# Document Digitization System

This project implements a document digitization system that can extract information from both handwritten and printed documents using various AI models. The system includes a web interface for easy document processing and multiple export formats.

## Project Structure

```
├── datasets/
│   ├──handwritten_forms
    |──handwritten_receipts
    |──printed_forms
    (printed_receipts we can download form kaggle link present in document)



├── notebooks/
│   ├── florence2_and_llama_receipts_printed.ipynb
│   ├── florence2_form_dataset.ipynb
│   ├── florence2_and_llama2_handwritten.ipynb
│   ├── llama2_forms_printed.ipynb
│   └── qwen2_all_dataset.ipynb
    └── paddle_ocr_gemini_code(for all dataset).ipynb

├── metrics/
│   ├──metrics for all models and dataset 
└── working_solution/
    ├── app.py
    ├── requirements.txt
    └── templates/
        └── index.html

|── Document.pdf(comparison of various models)
```

## Datasets

### Handwritten Documents
- **Forms**: Collection of handwritten forms including patient registration, application forms, etc.
- **Receipts**: Various handwritten receipts and invoices
- Location: `datasets/`

## Models Evaluated

1. **Florence-2 Base**
   - Specialized in visual document understanding
   - Excellent performance on printed documents
   - Notebook: -  `notebooks/florence2_form_dataset.ipynb`
                - `notebooks/florence2_and_llama2_handwritten.ipynb`

2. **Llama-2 Vision**
   - Strong performance on complex document layouts
   - Good at handling mixed content (text + images)
   - Notebooks: 
     - `notebooks/llama2_forms_printed.ipynb`
     - `notebooks/florence2_and_llama2_handwritten.ipynb`

3. **Qwen-2-VL**
   - Best overall performance across different document types
   - Superior handling of handwritten text
   - Notebook: `notebooks/qwen2_all_dataset.ipynb`

4.  **Paddle OCR and Gemini**
   - Best overall performance across different document types
   - Superior handling of handwritten text
   - Notebook: `notebooks\paddle_ocr_gemini_code(for all dataset).ipynb`

## Performance Metrics

Detailed performance metrics for each model are available in the `metrics/` folder:


Key metrics measured:
- OCR Accuracy
- Field Extraction Accuracy
- Processing Time
- Memory Usage

## Web Application

The working solution implements a Flask-based web application for document processing.

### Features
- Upload document images (PDF, PNG, JPG)
- Specify fields to extract
- Multiple export formats (PDF, DOCX, TXT, Excel)
- Real-time processing
- Drag-and-drop interface

### Setup and Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd <repository-name>
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
cd working_solution
pip install -r requirements.txt
```

4. Set up environment variables:
```bash
# Create a .env file with your API keys
GEMINI_API_KEY=your_api_key_here
```

5. Create required directories:
```bash
mkdir uploads exports
```

### Running the Application

1. Start the Flask server:
```bash
python app.py
```

2. Open your browser and navigate to:
```
http://localhost:5000
```

3. Using the application:
   - Enter the fields you want to extract
   - Upload or drag-and-drop your document
   - Click "Process Document"
   - Download results in your preferred format

### Export Formats
- **PDF**: Formatted table with extracted data
- **DOCX**: Microsoft Word document with formatted table
- **TXT**: Simple text format with key-value pairs
- **Excel**: Spreadsheet format with structured data


## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Google Gemini API for document processing
- Various open-source libraries and frameworks
- Dataset contributors and maintainers
