
## Human Movement and Pose Recognition using OpenCV

````markdown
# 🕺 Human Pose Detection & Movement Recognition

> A real-time pose estimation pipeline using OpenCV and keypoint tracking — built as a self-driven computer vision project during my 5th semester to understand the dynamics of body motion, alignment, and classification.

---

## 📌 About the Project

This project started as a personal experiment during my **Computer Vision coursework** in Fall 2024. I wanted to go beyond static image detection and dive into how machines perceive human movement in live video.

I explored real-time **pose detection** using OpenCV and MediaPipe, mapped **keypoints to skeletal structures**, and then layered on **posture classification** logic based on joint angles and body orientation.

After several weekends of debugging laggy video feeds and weird arm angles, I finally got a working system that tracks skeletons, analyzes motion patterns, and classifies body activity with reasonable accuracy — all on medium-spec laptops at ~30 FPS.

---

## 🎯 What I Set Out to Build

- Detect human body pose in real-time using keypoint tracking
- Build a skeleton structure from keypoints
- Track temporal movement patterns
- Align and normalize poses across frames
- Classify activities like "standing", "sitting", "walking", etc.
- Deploy a lightweight app to test on different devices

---

## ✅ What I Achieved

- 📸 Pose detection using **MediaPipe + OpenCV**
- 🧍 Keypoint-to-skeleton mapping and tracking
- 🧠 Implemented **motion vector analysis** for temporal tracking
- 🧬 **Affine alignment** to standardize poses across scale and angle
- ⚙️ Achieved **92.4% keypoint accuracy**
- 🖥️ Real-time performance at **30 FPS** on a basic laptop
- 🌐 Deployed frontend to **GitHub Pages** for live testing
- 🧪 Created activity classifier (rule-based prototype) for posture labeling

---

## 🔍 Technical Details

- Used **MediaPipe Pose** to extract 33 body landmarks in real-time
- Extracted joint angles (e.g. elbow, knee) using `arccos(dot product)`
- Applied **affine transformation** to normalize skeleton position/scale
- Used **vector movement** of joints across frames to detect motion patterns
- Designed rule-based classifier for simple actions:
  - If knee angles < threshold → "Sitting"
  - If head/torso position oscillates → "Walking"
- Optimized for real-time detection (video buffer + FPS limiter)
- Built using pure Python and OpenCV, no GPU dependencies

---

## 🛠️ Tech Stack

| Purpose            | Tools Used                              |
|--------------------|------------------------------------------|
| 💻 Language         | Python                                   |
| 👁️ CV & Detection   | OpenCV, MediaPipe                        |
| 📊 Visualization    | Matplotlib, Skeleton Overlay             |
| 🌐 Frontend         | HTML, CSS, JS                            |
| 🖥 Hosting (UI)     | GitHub Pages                             |

---

## 📁 File Structure

```bash
📦Pose-detection-cv
├── 📂 src/
│   ├── pose_estimator.py        # Keypoint extraction and processing
│   ├── classifier.py            # Simple rule-based activity classifier
│   ├── visualizer.py            # Draw skeleton overlays
│   └── video_stream.py          # Capture video, run main loop
├── 📂 frontend/
│   ├── index.html               # Web UI with info
│   └── style.css
├── 📂 sample_videos/            # Demo clips
├── README.md
├── requirements.txt
└── run.py                       # Main entry point
````

---

## 🌐 Try It Live

> ⚡ Web Interface & Overview:
> [🔗 Live Pose Estimation Frontend](https://nish941.github.io/Pose-detection-cv)

⚠️ Live webcam detection must be run locally due to browser security — but you can see **video samples**, **classification examples**, and project logic here.

---

## 🧪 Example Outputs

* ✅ Skeletons with joint overlay and landmark labels
* 🔁 Temporal pose smoothing across frames
* 🧠 Classifications: `"Standing"`, `"Sitting"`, `"Walking"` based on limb angles and keypoint shifts

*(Screenshots omitted for now — coming soon!)*

---

## 🚀 Run Locally (Real-Time Detection)

### 1. Clone and Install

```bash
git clone https://github.com/nish941/Pose-detection-cv.git
cd Pose-detection-cv
pip install -r requirements.txt
```

### 2. Run the Pose Detector

```bash
python run.py
```

Make sure your webcam is active. Skeleton should appear on-screen with live classification.

---

## 🧠 Learning Outcomes

* Understood how **2D keypoints → postural logic** works in real-time
* Applied vector math + OpenCV transformations to analyze motion
* Gained hands-on experience with **temporal smoothing, affine alignment**, and skeleton tracking
* Learned to manage **video stream buffers** and ensure high FPS

---

## 🔮 Future Improvements

* Replace rule-based classifier with a small LSTM model (pose → action)
* Add **multi-person tracking** (currently 1-person only)
* Integrate body-part velocity tracking
* Export final pose sequences as JSON for external use (e.g., games, physical therapy)

---

## 🙏 Acknowledgements

* [Google MediaPipe](https://mediapipe.dev/) for pose landmark detection
* OpenCV Docs and CVZone tutorials
* Friends who volunteered to walk, sit, and wave at my webcam during testing 🙃

  
