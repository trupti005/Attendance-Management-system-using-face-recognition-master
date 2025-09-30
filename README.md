A sophisticated face recognition-based attendance management system built with Python and Tkinter. This application automates the attendance tracking process using facial recognition technology, making attendance management efficient and contactless.

## 📸 Overview

CLASS VISION is an intelligent attendance system that leverages computer vision and machine learning to automatically identify and mark student attendance. The system provides a modern, dark-themed interface with voice feedback for an enhanced user experience.

## ✨ Key Features

- 🎓 **Student Registration**: Capture and register student faces with enrollment numbers and names
- 🤖 **Face Training**: Train the system to recognize registered students using machine learning
- ✅ **Automated Attendance**: Mark attendance automatically using real-time face recognition
- 📊 **Attendance Management**: View, track, and manage attendance records by subject
- 🔊 **Voice Feedback**: Audio notifications for all user actions and system status
- 🌙 **Modern Dark Theme**: Eye-friendly dark interface with yellow accents
- 📝 **CSV Export**: Export attendance data in CSV format for easy record-keeping
- 🔒 **Validation**: Input validation to ensure data integrity

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **Python 3.x** | Core programming language |
| **OpenCV (cv2)** | Face detection and recognition |
| **Tkinter** | GUI framework |
| **PIL (Pillow)** | Image processing and manipulation |
| **pandas** | Data management and CSV handling |
| **pyttsx3** | Text-to-speech functionality |
| **NumPy** | Numerical computations |
| **Haar Cascade** | Face detection classifier |


### Python Dependencies

Install all required packages using pip:

```bash
pip install opencv-python
pip install pillow
pip install pandas
pip install pyttsx3
pip install numpy
```

Or use the requirements file (create one with these contents):

```bash
pip install -r requirements.txt
```

**requirements.txt:**
```
opencv-python>=4.5.0
Pillow>=8.0.0
pandas>=1.2.0
pyttsx3>=2.90
numpy>=1.19.0
```

## 📁 Project Structure

```
CLASS-VISION/
│
├── attendance.py                    # Main application file (entry point)
├── takeImage.py                     # Module for capturing student images
├── trainImage.py                    # Module for training face recognition model
├── automaticAttedance.py            # Module for automated attendance marking
├── show_attendance.py               # Module for viewing attendance records
│
├── haarcascade_frontalface_default.xml  # Haar Cascade classifier for face detection
│
├── AMS.ico                          # Application icon
│
├── TrainingImage/                   # Directory for captured training images
│   └── (student images organized by ID)
│
├── TrainingImageLabel/              # Directory for trained model
│   └── Trainner.yml                 # Trained face recognition model file
│
├── StudentDetails/                  # Directory for student information
│   └── studentdetails.csv           # Student database (ID, Name, etc.)
│
├── Attendance/                      # Directory for attendance records
│   └── (attendance CSV files by subject and date)
│
├── UI_Image/                        # Directory for UI assets
│   ├── 0001.png                     # Application logo
│   ├── register.png                 # Registration icon
│   ├── attendance.png               # Attendance icon
│   └── verifyy.png                  # Verification icon
│
└── README.md                        # This file
```

## 🚀 Getting Started

### Installation Steps

1. **Clone or Download the Project**
   ```bash
   git clone <repository-url>
   cd CLASS-VISION
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Download Required Files**
   - Download `haarcascade_frontalface_default.xml` from [OpenCV GitHub](https://github.com/opencv/opencv/tree/master/data/haarcascades)
   - Place it in the root directory

4. **Prepare Directories**
   The application will automatically create necessary directories on first run:
   - `TrainingImage/`
   - `TrainingImageLabel/`
   - `StudentDetails/`
   - `Attendance/`

5. **Add UI Images**
   Place all required images in the `UI_Image/` folder

6. **Run the Application**
   ```bash
   python attendance.py
   ```

## 💡 How to Use

### 1️⃣ Registering a New Student

1. Launch the application
2. Click **"Register a new student"** button
3. A new window will open:
   - Enter **Enrollment Number** (numeric only, e.g., 101, 102)
   - Enter **Student Name** (full name)
4. Click **"Take Image"** button
   - Position your face in front of the camera
   - The system will capture multiple images automatically
   - Wait for the "Images Captured Successfully" message
5. Click **"Train Image"** button
   - This trains the model to recognize the new student
   - Wait for the training completion message
6. Student is now registered!

**Tips for Best Results:**
- Ensure good lighting (avoid backlighting)
- Look directly at the camera
- Remove glasses if possible
- Keep a neutral expression
- Stay within the frame boundaries

### 2️⃣ Taking Attendance

1. Click **"Take Attendance"** button
2. Select the subject from the dropdown menu
3. The camera will activate automatically
4. The system will:
   - Detect faces in real-time
   - Recognize registered students
   - Mark attendance automatically
   - Display recognized names on screen
5. Attendance is saved automatically to CSV file
6. Press ESC or close window to stop

**Attendance File Format:**
- Location: `Attendance/[Subject]_[Date]_[Time].csv`
- Columns: Enrollment No, Name, Date, Time

### 3️⃣ Viewing Attendance

1. Click **"View Attendance"** button
2. Select the subject
3. Choose the date/session
4. View attendance records in a new window
5. Export or print as needed

## ⚙️ Configuration

### Default Paths (configurable in code)

```python
haarcasecade_path = "haarcascade_frontalface_default.xml"
trainimagelabel_path = "./TrainingImageLabel/Trainner.yml"
trainimage_path = "./TrainingImage"
studentdetail_path = "./StudentDetails/studentdetails.csv"
attendance_path = "./Attendance"
```

### Customization Options

- **Window Size**: Modify `window.geometry("1280x720")`
- **Theme Colors**: Change `#1c1c1c` (background) and `yellow` (text)
- **Fonts**: Adjust `("Verdana", size, "bold")`
- **Camera Settings**: Modify in respective module files

## 🎨 User Interface

### Color Scheme
- **Primary Background**: `#1c1c1c` (Dark gray)
- **Secondary Background**: `#333333` (Medium gray)
- **Primary Text**: `Yellow` (High contrast)
- **Accent**: `Green` (Success states)

### Layout
- **Resolution**: 1280x720 pixels (responsive)
- **Font Family**: Verdana (consistent throughout)
- **Button Style**: Raised relief with border
- **Input Fields**: Dark background with yellow text

## 🔊 Voice Feedback Features

The system provides audio feedback for:
- ✅ Successful image capture
- ✅ Training completion
- ✅ Attendance marking confirmation
- ⚠️ Error notifications
- ℹ️ System status updates

Voice feedback can be customized in the `text_to_speech()` function.

## 📊 Data Management

### Student Details Format (studentdetails.csv)
```csv
Enrollment No,Name
101,John Doe
102,Jane Smith
```

### Attendance Record Format
```csv
Enrollment No,Name,Date,Time,Subject
101,John Doe,2025-09-30,09:30:45,Mathematics
102,Jane Smith,2025-09-30,09:31:12,Mathematics
```

## ⚠️ Important Notes

### Best Practices
- ✅ Capture at least 100-200 images per student for accurate recognition
- ✅ Train the model after adding each new student
- ✅ Ensure consistent lighting conditions
- ✅ Keep the camera clean and at eye level
- ✅ Maintain a database backup regularly

### Limitations
- ⚠️ Requires good lighting conditions
- ⚠️ May struggle with significant appearance changes (glasses, beard, etc.)
- ⚠️ Performance depends on camera quality
- ⚠️ Requires training for each new student

## 🐛 Troubleshooting

### Common Issues and Solutions

**1. Camera not detected**
```
Error: Cannot access camera
Solution: 
- Check if camera is properly connected
- Close other applications using the camera
- Try a different USB port (for external cameras)
- Check camera permissions in OS settings
```

**2. Face not recognized**
```
Error: Face detection failed or low accuracy
Solution:
- Retrain the model with more image samples
- Ensure proper lighting (avoid shadows)
- Position face directly in front of camera
- Clean camera lens
- Remove accessories (glasses, caps)
```

**3. Module import errors**
```
Error: ModuleNotFoundError
Solution:
- Verify all packages are installed: pip list
- Reinstall dependencies: pip install -r requirements.txt
- Check Python version: python --version
- Use virtual environment to avoid conflicts
```

**4. Haar Cascade file not found**
```
Error: File not found - haarcascade_frontalface_default.xml
Solution:
- Download from OpenCV GitHub repository
- Place in root directory
- Check file name spelling
```

**5. Training fails**
```
Error: Training process failed
Solution:
- Ensure at least one student is registered
- Check if TrainingImage folder has images
- Verify folder permissions
- Clear old training data and retrain
```

## 🔒 Security Considerations

- Student images are stored locally
- No data is transmitted over network
- Access control can be added as needed
- Regular backups recommended
- Comply with local privacy regulations

## 🚀 Future Enhancements

- [ ] Multi-camera support
- [ ] Cloud storage integration
- [ ] Mobile app companion
- [ ] Real-time analytics dashboard
- [ ] Email notifications for attendance
- [ ] Batch student registration
- [ ] Advanced reporting features
- [ ] Face mask detection
- [ ] Temperature screening integration

## 👥 Credits

**Developer:** Trupti Savale  
**Company:** NEWGEN TECH PVT. LTD.  
**Support:** NEWGEN TECH PVT. LTD.

## 🙏 Acknowledgments

- OpenCV community for face detection algorithms
- Python community for excellent libraries
- NEWGEN TECH PVT. LTD. for project support

---

Supported by:- NEWGEN TECH PVT. LTD.

*Developed with ❤️ by Trupti Savale*
