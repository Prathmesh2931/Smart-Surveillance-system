# **AI-Based Surveillance System**

An intelligent surveillance solution using **LLaVA-7B**, built for both **pre-recorded** and **live webcam** feeds. The system analyzes visual input, detects abnormal or violent behavior, and sends **real-time alerts via Telegram**, along with storing all flagged data in **MongoDB Atlas**.

---

## ⚙️ **Core Features**

- 🧠 **LLaVA-7B-based Vision-to-Text Analysis**
- 🎥 Pre-recorded video frame analysis
- 📡 Real-time surveillance via phone/webcam (IP stream)
- 📬 Telegram Bot Alerts (triggered only on detected violence/anomaly)
- 🗃️ MongoDB Atlas for storing frame data, timestamps, and captions

---

Ensure you have Python 3.8+ and run:

```bash
pip install -r requirements.txt
```

---

## 📥 **Model Requirement**

Download and set up the **LLaVA-7B model** using [Ollama](https://ollama.com/library/llava).  
Once setup is complete, make sure the model is accessible via:

```bash
ollama run llava
```

---

## 🧪 **1. Pre-recorded Video Analysis**

Run the Jupyter notebook for analyzing a recorded video:

```bash
jupyter notebook llava_prevideo.ipynb
```

### What It Does:
- Extracts frames at every 30-frame interval
- Sends each frame to **Model** for caption generation
- Stores results in **MongoDB Atlas**
- Triggers **Telegram alert only** if a frame contains violence or anomaly

#### 📸 Example Outputs:
- Processed frame 
> ![Violence](https://github.com/user-attachments/assets/33a1195f-1ca4-44d3-8428-e23e8bff7707)
- Output Provided By Model
> ![Screenshot from 2025-04-05 00-53-40](https://github.com/user-attachments/assets/6d42fcc1-eac0-41db-8308-dfe4b4d9e4aa)
- Screenshot of triggered Telegram alert
> ![Telegram_API](https://github.com/user-attachments/assets/e16bd669-fe22-4bea-b165-1a3294e0a0df)


---

## 🔴 **2. Live Webcam Surveillance**

Run the live surveillance script using:

```bash
python llava_multi.py
```

### What It Does:
- Captures frames from live webcam (can use phone camera via IP)
- Sends them to **Model** for real-time analysis
- If violence/anomaly is detected:
  - Triggers **Telegram alert**
  - Includes **frame description**, **timestamp**, and **IP-based location**
- Saves flagged frames and captions to **MongoDB Atlas**

#### 📸 Example Outputs:
- Live flagged frame
> ![Screenshot from 2025-04-05 01-06-25](https://github.com/user-attachments/assets/8d200eb4-7aa5-453a-888a-956b3d0799ab)
- Description of frame
> ![Screenshot from 2025-04-05 01-56-58](https://github.com/user-attachments/assets/2dfad7c0-56e2-464b-a932-a38e31177358)

---
  

## 🛡️ **Conclusion**

This project showcases a powerful and flexible AI-driven surveillance pipeline:

- Processes both offline and live video
- Alerts only when anomalies occur
- Stores event data for traceability and further investigation
- Highly modular: extendable with gesture recognition, facial ID, object detection

---

## ▶️ **How to Run**

```bash
# Install dependencies
pip install -r requirements.txt

# For Pre-recorded Analysis
jupyter notebook llava_prevideo.ipynb

# For Live Webcam Surveillance
python llava_multi.py
```

---
