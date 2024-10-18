## Table Text Extraction from Images Using PaddleOCR and TableTransformer

This project allows you to extract text from table images by detecting rows and columns using the TableTransformerForObjectDetection model and then applying OCR to extract the text within each cell. The extracted text is saved in CSV format.

### Features
Detects table rows and columns using a pre-trained model (TableTransformerForObjectDetection).
Extracts text from each cell in the table using PaddleOCR.
Organizes extracted text into rows and columns.
Exports the table data to a CSV file.

### Requirements
Ensure you have the following installed:

Python 3.7+
Required Python libraries (detailed in the next section)

### Installation
Clone the repository (or download the project files):

bash
Copy code
git clone https://github.com/your-username/table-text-extraction.git
cd table-text-extraction
Install dependencies:

You can install the required Python packages using the following command:

bash
Copy code
pip install torch transformers pillow paddleocr

### Dependencies:

torch for using PyTorch models.
transformers for loading and using the TableTransformerForObjectDetection model.
Pillow for image manipulation.
paddleocr for text recognition (OCR) from images.

###Usage

1. Prepare the Images
Place your table images in a folder (e.g., images/). The images should be in one of the supported formats: .png, .jpg, or .jpeg.

2. Run the Script
The main script extracts text from tables in images and saves it as a CSV file. You can run the script as follows:

bash
Copy code
python extract_table_text.py
Make sure to modify the script with the path to your images folder (images_path) and your desired output CSV file path (output_csv_path).

3. Example Directory Structure
graphql
Copy code
table-text-extraction/
│
├── extract_table_text.py  # Main script
├── images/                # Directory with table images
│   ├── table1.jpg
│   ├── table2.png
│   └── ...
└── extracted_table_data.csv  # Output CSV file (generated after running the script)
4. Customization
You can adjust the ts_thresh parameter inside the script to set the detection threshold for table rows and columns.
Modify the output_csv_path variable in the script to specify where the CSV output should be saved.
How It Works
Detecting Table Structure:

The TableTransformerForObjectDetection model detects rows and columns in the table image.
Extracting Cell Bounding Boxes:

The row and column boxes are combined to calculate the bounding boxes for individual cells.
OCR for Text Extraction:

Each cell image is cropped, and PaddleOCR is used to extract text from the cell.
Saving as CSV:

The extracted text is organized into a table (2D list) and saved as a CSV file.
