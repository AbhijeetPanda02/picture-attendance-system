from docx import Document
from docx.shared import Pt
from docx.enum.text import WD_PARAGRAPH_ALIGNMENT

# Create a new README document
doc = Document()

# Title
title = doc.add_heading('📸 Face Recognition Based Attendance System', 0)
title.alignment = WD_PARAGRAPH_ALIGNMENT.CENTER

# Description
doc.add_paragraph(
    "This project is a Python-based Face Recognition Attendance System that utilizes the power of "
    "the `facenet-pytorch` model for facial recognition. It automates the process of taking attendance "
    "from a group photo by identifying students based on pre-stored images."
)

# Features
doc.add_heading('🚀 Features', level=1)
features = doc.add_paragraph()
features.add_run("• Face detection using MTCNN\n")
features.add_run("• Face embedding using InceptionResnetV1 (VGGFace2)\n")
features.add_run("• Automated matching and attendance marking\n")
features.add_run("• Visual output with bounding boxes and labels\n")

# Installation
doc.add_heading('📦 Installation', level=1)
doc.add_paragraph("Install the required Python packages:")
doc.add_paragraph("pip install facenet-pytorch mtcnn opencv-python numpy scikit-learn", style='Intense Quote')

# Dataset Structure
doc.add_heading('🗂️ Dataset Structure', level=1)
doc.add_paragraph("The `Dataset` folder should be organized as follows:")
doc.add_paragraph("""
Dataset/
├── 2241016042/
│   ├── img1.jpg
│   ├── img2.jpg
├── 2241016043/
│   ├── img1.jpg
│   ├── img2.jpg
""")

# How it works
doc.add_heading('⚙️ How It Works', level=1)
doc.add_paragraph(
    "1. Extract embeddings for each student image in the Dataset folder.\n"
    "2. Save the average embedding per student in a `.npy` file.\n"
    "3. Detect faces in a group image.\n"
    "4. Compare detected faces with saved embeddings and identify present students."
)

# Output
doc.add_heading('🖼️ Output', level=1)
doc.add_paragraph("An image named `output_with_boxes.jpg` will be generated showing detected faces with labels.")

# Author & License
doc.add_heading('👨‍💻 Author & License', level=1)
doc.add_paragraph("Developed by Abhijeet Panda\nLicensed under the MIT License.")

# Save the document
file_path = "/mnt/data/README_Face_Recognition_Attendance.docx"
doc.save(file_path)

file_path
