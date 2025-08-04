## 📸 Face Recognition Based Attendance System

This project is a Python-based Face Recognition Attendance System that utilizes the power of facenet-pytorch for facial recognition. It automates the process of taking attendance from a group photo by identifying students based on pre-stored images.

## 🚀 Features 

🔍 Face Detection using MTCNN

🧠 Face Embedding using InceptionResnetV1 (VGGFace2)

✅ Automated Attendance from a group image

🖼️ Visual Output with bounding boxes and student registration numbers

## 📦 Installation 
Install all required Python libraries using pip:

pip install facenet-pytorch mtcnn opencv-python numpy scikit-learn 

## 🗂️ Dataset Structure 
Organize your dataset folder like this:

Dataset/
├── 2241016042/
│   ├── img1.jpg
│   ├── img2.jpg
├── 2241016043/
│   ├── img1.jpg
│   ├── img2.jpg


Each subfolder should be named after a student's registration number, and contain multiple clear face images of the student.

## ⚙️ How It Works 
🔧 Extracts face embeddings from all student images using a pretrained FaceNet model.

🧠 Averages multiple embeddings per student to create a single representative embedding.

📷 Loads a group photo and detects faces using MTCNN.

🔁 Compares each detected face with stored embeddings and identifies students based on embedding similarity.

🟩 Annotates recognized students and marks them present.

## 🖼️ Output 
#### A visual output image (output_with_boxes.jpg) is generated with:

✅ Green boxes and labels for recognized students

❌ Red boxes labeled "Unknown" for unrecognized faces

## 📁 Files 
### File Description 
#### Dataset_creation.py 
Extracts and saves face embeddings for students
#### train.py
make the model and help in generating the embeddings of the Dataset 
#### student_embeddings.npy
Stores average embeddings for each student
#### mark_attendance.py
Detects and recognizes students from group photo 
