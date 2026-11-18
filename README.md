# 🏋️ SmartFit Studio — Fitness Management System

> Smart gym management powered by computer vision: face-based access, AI rep counting, and member progress tracking.

Built for the **INNOVERSE Hackathon** (ISET Kairouan × JCI Kairouan).
Desktop application written in **Python** (Tkinter) with **OpenCV** and **MediaPipe**, designed to run on a laptop or a **Raspberry Pi with a camera**.

---

## ✨ Features

### 👨‍🏫 Coach Space
-  **Login screen** protecting coach features
-  **Dashboard** with live statistics (total members, today's sessions, members active this week)
-  **New member registration**: first name, last name, date of birth, phone number, and **webcam photo capture**
-  **Member list** with a detail panel (identity, registration date, last activity, session history)
-  **Performance tracking**: pick a member from a dropdown to see their training sessions and recorded weights
-  **Weight progression chart** per member (Matplotlib)

### 🧑‍🎓 Member Space
- **Face authentication** through the webcam (Haar cascade face detection + template matching against the stored photo)
-  **Exercise selection** (push-ups, sit-ups, squats)
- **Weight entry** with each session
- **AI push-up counter** using MediaPipe Hands, with live camera preview and real-time counter
- **Automatic session saving** (timestamp, exercise, weight, repetition count)

---

## 🧰 Tech Stack

Language: Python 3.9 - 3.11
GUI: Tkinter
Computer Vision: OpenCV, MediaPipe
Image Handling: Pillow
Charts: Matplotlib
Storage: JSON file and image folder
Hardware: Webcam or Raspberry Pi with camera

---

## 📁 Project Structure

```
SmartFit-Studio/
├── main.py              # Main application (all modules)
├── members_data.json     # Created automatically: member records
├── member_photos/        # Created automatically: member photos
└── README.md
```
---

## ⚙️ Installation

### 1. Clone / copy the project
```bash
git clone https://github.com/houdaghalmi/SmartFit.git
cd SmartFit-Studio
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux / macOS / Raspberry Pi
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install opencv-python mediapipe pillow matplotlib
```

> **Linux / Raspberry Pi:** Tkinter may need to be installed separately:
> ```bash
> sudo apt install python3-tk
> ```

### 4. Connect a webcam (or the Raspberry Pi camera)

---

## ▶️ Usage

```bash
python main.py
```

### Coach workflow
1. Click **Coach Space** and log in.
2. Open **Member Management** → **➕ New Member**.
3. Fill in  cin ,name, date of birth, phone, then click **Photo capture** and take a clear, front-facing photo.
4. Save. The member now appears in the list and can be recognized in Member Space.
5. Use **Performance Tracking** or **Weight Tracking** to follow member progress.

### Member workflow
1. Click **Member Space**. The camera opens.
2. Face the camera and capture. If matched, your dashboard opens.
3. Choose an exercise, enter your weight, then start.
4. For **push-ups**, the counter window opens: perform your reps with both hands visible to the camera, then finish to save the count.

> ⚠️ **Default coach credentials in the code are `admin` / `admin`.

---


## 🍓 Raspberry Pi Notes

- Install Tkinter and OpenCV system dependencies first (`sudo apt install python3-tk libatlas-base-dev`).
- MediaPipe availability depends on the Pi OS (64-bit recommended). If installation fails, check for a compatible wheel for your Python version.
- Lower the camera resolution and frame rate to keep rep counting real-time.

