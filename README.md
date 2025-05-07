# Voice-Centric AI Assistant 🚗🗬

A Python-based voice UI assistant that:

* Detects objects using YOLOv5
* Fetches real-time weather from OpenWeatherMap
* Speaks out alerts contextually (macOS native voice)
* Shows live webcam feed with bounding boxes
* Highlights UI background color based on risk level

---

## 📦 Requirements

Ensure you have **Python 3.9 to 3.12** installed. Use Anaconda or a virtual environment for easier package management.

### ✅ Install Required Libraries

Open your terminal and run:

```bash
pip install torch torchvision opencv-python pillow requests
```

> 💡 No need to install `pyttsx3` — macOS uses the built-in `say` command for voice output.

---

## 📂 Project Structure

```
voice_ui_app/
├── main_app.py              # Main detection + UI + voice script
├── inference_output.json    # Runtime detection data (auto-generated)
├── latest_frame.jpg         # Webcam preview image (auto-generated)
└── README.md                # This file
```

---

## 🔑 Setup Instructions

### 1. Download or Clone the Project

Clone via Git:

```bash
git clone https://github.com/your-username/voice-ui-assistant.git
cd voice-ui-assistant
```

Or download the ZIP file and extract it manually.

---

### 2. Set Your Weather API Key

Open `main_app.py` and replace this line:

```python
API_KEY = 'your_api_key_here'
```

with your actual key from [OpenWeatherMap](https://openweathermap.org/api).

---

## 🛠️ Running the Application

Run the app from your terminal:

```bash
python main_app.py
```

It will:

* Open your webcam
* Detect objects like `person`, `stop sign`, etc.
* Fetch live weather
* Speak alerts such as:

```
"Severe fog detected. Turn on high beams."
"Pedestrian detected. Please slow down."
```

---

## 🧠 Smart Features

* 🔍 Real-time object detection (YOLOv5s)
* ☁️ Weather awareness via OpenWeatherMap
* 🔊 Speaks alerts using macOS native `say`
* 💡 Avoids repeating alerts — only speaks once per condition
* 🎨 Changes background color:

  * **Red**: Danger (e.g., fog + pedestrian)
  * **Yellow**: Moderate caution (e.g., fog)
  * **Green**: Safe conditions

---

## 📝 Notes

* This version is tested for **macOS**.
* If using **Windows or Linux**, you can replace the `speak()` function with `pyttsx3` or another TTS engine.
* Ensure your webcam is working and Python has permission to access it.

---

## ✅ Example Output

Terminal preview:

```
Weather API Response: {'weather': [{'main': 'Fog'}], ...}
Speaking: Severe fog detected. Turn on high beams.
Speaking: Pedestrian detected. Please slow down.
```

App preview:

```
Weather: Fog
Detected: person
```

---

## 📸 Screenshot (Optional)

You can add a screenshot by saving one as `screenshot.png` and adding this line:

```markdown
![UI Screenshot](./screenshot.png)
```

---

## 📃 License

MIT – Free to use, learn, and modify.

---

Made with ❤️ by **Your Name**
