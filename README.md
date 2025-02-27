# **Automated Face Recognition Attendance System**  

An AI-powered attendance system using **DeepFace** for real-time face recognition. This project automates attendance tracking by detecting and identifying faces from a live camera feed and logging attendance based on accumulated screen time.  

## **Features**  
✅ **Real-time Face Recognition** (DeepFace + Facenet)  
✅ **Automatic Attendance Marking** (10-minute threshold)  
✅ **SQLite Database** for tracking users' attendance  
✅ **Grace Period Handling** (Pauses tracking if absent briefly)  
✅ **Live Camera Feed**  

## **How It Works**  
1. Captures frames from the webcam.  
2. Uses **DeepFace** to identify faces from the `dataset/` directory.  
3. Tracks accumulated time for each detected person.  
4. Marks a person as **PRESENT** after 10 minutes (600s) of cumulative presence.  
5. Attendance data is stored in **SQLite (`attendance.db`)**.  

## **Setup & Installation**  

### **1. Clone the Repository**  
```bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
```

### **2. Install Dependencies**  
Ensure you have Python 3.10+ and install required packages:  
```bash
pip install opencv-python numpy pandas deepface sqlite3
```

### **3. Prepare the Dataset**  
- Create a folder **`dataset/`**  
- Add images of individuals inside subfolders named after them (e.g., `dataset/John_Thomas/`)  

### **4. Run the Script**  
```bash
python attendance.py
```

## **Database Schema (`attendance.db`)**  
| Column          | Type      | Description                             |  
|----------------|----------|-----------------------------------------|  
| `name`        | TEXT     | Person's name (folder name in dataset)  |  
| `accumulated_time` | INTEGER  | Total detected time (in seconds)     |  
| `last_seen`   | DATETIME | Timestamp of last detection             |  
| `marked`      | BOOLEAN  | 1 if marked as **PRESENT**, else 0      |  

## **To-Do / Future Improvements**  
- ✅ Improve recognition accuracy with **MTCNN** detector  
- ✅ Add **GUI for better user interaction**  
- 🔜 Integrate **RFID or QR Code for hybrid attendance**  
- 🔜 Implement **Cloud Sync (Firebase/Google Sheets)**  
