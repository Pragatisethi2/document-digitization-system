# Document Digitization with Gemini Vision API

This Flask application allows users to upload documents (images/PDFs) and extract specific information using the Gemini Vision API. The extracted data can be viewed in the web interface and is automatically saved to an Excel file.

## Features

- Beautiful, responsive UI built with Tailwind CSS and Vue.js
- Drag-and-drop file upload
- Dynamic field selection for data extraction
- Real-time data preview
- Automatic Excel export
- Support for various file formats (PDF, PNG, JPG, JPEG)

## Prerequisites

- Python 3.8 or higher
- Google Cloud API key with Gemini Vision API access

## Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd <repository-name>
```

2. Create a virtual environment and activate it:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install the required packages:
```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the root directory and add your Google API key:
```
GOOGLE_API_KEY=your_api_key_here
```

## Usage

1. Start the Flask application:
```bash
python app.py
```

2. Open your web browser and navigate to `http://localhost:5000`

3. Use the application:
   - Add fields you want to extract from the document
   - Upload your document by dragging and dropping or using the file browser
   - Click "Process Document" to start the extraction
   - View the results in the web interface
   - Find the extracted data in `uploads/extracted_data.xlsx`

## Supported File Types

- Images: PNG, JPG, JPEG
- Documents: PDF

## Directory Structure

```
.
├── app.py              # Main Flask application
├── requirements.txt    # Python dependencies
├── templates/         
│   └── index.html     # Main template file
├── uploads/           # Directory for uploaded files and Excel output
└── .env               # Environment variables
```

## Error Handling

The application includes error handling for:
- Invalid file types
- Missing files
- API errors
- Data processing errors

## License

This project is licensed under the MIT License - see the LICENSE file for details. 