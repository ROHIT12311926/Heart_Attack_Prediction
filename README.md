❤️ Heart Attack Early Warning System using ESP32 + ML + IoT

This project is an IoT-based medical emergency prediction system that detects abnormal heart-rate patterns and provides a 1-minute early alert before a possible heart attack.
The system uses ESP32, pulse/SpO2 sensors, and a Machine Learning model trained on real-world heart-rate & oxygen-level datasets to differentiate between:

Normal high heart rate due to exercise/activity

Dangerous patterns that indicate possible cardiac arrest

🔥 Project Motivation

In most heart-attack cases, the patient doesn’t get medical help within time.
This system is designed to predict a potential cardiac emergency early, raise alarms across the home, and notify caregivers so the patient gets immediate help.

🚀 Key Features

📡 Real-time monitoring of Heart Rate & SpO2

🤖 On-device or Cloud-based Machine Learning prediction

📊 Differentiates exercise vs. real heart attack signals

🔊 Home-wide alarm trigger at least 1 minute before predicted attack

📱 Optional: Sends alert to mobile app / cloud dashboard

💾 Save sensor readings to Excel (.xlsx) format

🔌 Works fully on ESP32 (low power + WiFi + IoT)

🧠 How the ML Model Works

The ML model takes continuous real-time inputs:

Heart Rate (BPM)

SpO₂

HR Variability

User Age Group (optional)

Activity Label (Rest/Walk/Run)

Past 30–60 sec HR Trends

It classifies the state into:

0 → Normal

1 → High Activity (exercise etc.)

2 → Potential Heart Attack (trigger alarm)

Model type used (your choice depending on final implementation):

RandomForest / XGBoost / LSTM (if time-series based)

Trained offline using heart datasets that include:

rest HR

post-exercise HR

elderly HR patterns

cardiac-stress behavior

The final trained model is deployed on ESP32 / cloud for predictions.

🏗️ System Architecture
🛠️ Hardware Components
Component	Description
ESP32 DevKit V1	Main microcontroller + WiFi
Pulse Sensor / MAX30102	Measures Heart Rate + SpO₂
Buzzer / Home Alarm System	Triggers alerts
Battery Pack / Power Module	Portable power
Optional: GSM module	For SMS alerts
Optional: OLED Display	Show HR & Prediction
🔄 Working Flow
4

1️⃣ Sensor reads heart rate + SpO2
2️⃣ ESP32 preprocesses data & removes noise
3️⃣ Data goes to ML model → Prediction
4️⃣ If abnormal → Start internal timer
5️⃣ If pattern continues → Trigger alarms
6️⃣ Optionally upload to cloud / notify mobile app

📁 Dataset Details

Dataset includes (or will include):

HR & SpO₂ readings across different age groups

Resting, Walking, Running, Cycling sessions

Sudden HR spikes

Medical-grade cardiac stress signals

Saved in Excel (.xlsx) to match your preference.

Columns example:

HR	SpO2	Age	Activity	Label
82	98	24	Rest	0
155	95	24	Running	1
130	92	60	Rest	2
🧪 Machine Learning Pipeline

Data Cleaning

Noise Filtering (moving average / Butterworth)

Feature Engineering

Train-test split

Model training

Accuracy evaluation

Export model (pickle / tflite)

Deploy on ESP32 or cloud API

🚀 Installation & Setup
1. Clone the Repository
git clone https://github.com/<username>/Heart-Attack-Prediction-IoT.git
cd Heart-Attack-Prediction-IoT

2. Install Required Python Libraries
pip install numpy pandas scikit-learn matplotlib xgboost

3. Flash ESP32 Code

Using Arduino IDE:

Select Board: ESP32 DevKit V1

Install MAX30102 / PulseSensor library

Upload the provided .ino file.

4. Run ML Notebook
jupyter notebook


Open model_training.ipynb.

📊 Results

Prediction accuracy achieved: XX%

Alert time: ~1 minute early warning

False positives minimized using activity differentiation

(Add screenshots/graphs here)

🧱 Challenges Faced

Motion noise in sensor

Missing SpO₂ values during movement

Differentiating exercise vs. attack

ESP32 memory limit for heavy ML models

Dataset availability

🔮 Future Improvement

Add ECG sensor for higher accuracy

Use LSTM neural networks for time-series prediction

Add cloud dashboard + MQTT

Smartwatch integration

SOS SMS service

📜 Conclusion

This project demonstrates a real-time, IoT-based health prediction system capable of detecting dangerous heart-rate patterns and providing early warnings before a possible heart attack.
Combining ESP32, sensors, machine learning, and IoT, it provides a low-cost but highly effective personal safety solution.
