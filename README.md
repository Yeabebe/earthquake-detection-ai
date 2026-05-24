# Earthquake Detection and Analysis System using AI & TinyML

An intelligent earthquake monitoring and vibration analysis system built using Machine Learning, Deep Learning, TinyML, ESP32 sensor data, and real earthquake datasets.

This project combines:

* Real earthquake data from IRIS
* Real-time ESP32 vibration sensor data
* Deep Learning (LSTM)
* TinyML for Edge AI
* TensorFlow Lite deployment
* REST API integration

---

# Project Architecture

```text
                    +----------------------+
                    |   IRIS Earthquake    |
                    |      Dataset         |
                    +----------+-----------+
                               |
                     +---------v---------+
                     |   AI Training     |
                     |                   |
                     |  1. Dense Model   |
                     |  2. LSTM Model    |
                     +---------+---------+
                               |
                 +-------------+-------------+
                 |                           |
        +--------v--------+        +---------v---------+
        | TinyML Model    |        | LSTM Model        |
        | TensorFlow Lite |        | Sequence Analysis |
        +--------+--------+        +---------+---------+
                 |                           |
                 |                           |
         +-------v-------+          +--------v--------+
         | ESP32 Device  |          | Cloud / Backend |
         +---------------+          +-----------------+


                    +-----------------------+
                    | ESP32 Sensor Backend  |
                    | REST API Integration  |
                    +-----------+-----------+
                                |
                     +----------v----------+
                     | Vibration TinyML    |
                     | Real-Time Detection |
                     +---------------------+
```

---

# Project Structure

```text
earthquake-detection-ai/
│
├── datasets/
│   ├── IEB_export.csv
│   └── esp32_sensor_data.csv
│
├── notebooks/
│   ├── earthquake_tinyml_model.ipynb
│   ├── earthquake_lstm_model.ipynb
│   └── esp32_vibration_tinyml_model.ipynb
│
├── models/
│   ├── earthquake_model.tflite
│   ├── earthquake_lstm.tflite
│   └── esp32_vibration_model.tflite
│
├── README.md
└── requirements.txt
```

---

# Models in This Project

## 1. Earthquake TinyML Model

A lightweight Dense Neural Network trained on IRIS earthquake data.

### Features

* Latitude
* Longitude
* Depth
* Magnitude

### Purpose

* TinyML deployment
* Earthquake classification
* TensorFlow Lite conversion
* ESP32 compatibility

---

## 2. Earthquake LSTM Model

A Deep Learning sequential model for temporal earthquake analysis.

### Features

* Time-series earthquake analysis
* Sequential learning
* Better temporal understanding
* Advanced prediction

### Purpose

* Cloud AI
* Backend AI analysis
* Sequential earthquake prediction

---

## 3. ESP32 Vibration TinyML Model

A completely separate TinyML model trained using real ESP32 sensor vibration data from the backend API.

### Features

* x-axis acceleration
* y-axis acceleration
* z-axis acceleration
* magnitude
* PGA (Peak Ground Acceleration)

### Purpose

* Real-time vibration detection
* Edge AI inference
* Embedded TinyML deployment
* ESP32 real-time monitoring

---

# Backend API Integration

This project integrates with a live backend earthquake monitoring API.

## API Endpoint

```text
https://apiearthquake.yonasproject.cloud/api/samples?page=1
```

## Sample Sensor Data

```json
{
  "x": 0.02,
  "y": 0.01,
  "z": 0.98,
  "magnitude": 0.98,
  "pga": 0.019
}
```

---

# Technologies Used

## Artificial Intelligence

* TensorFlow
* Keras
* Scikit-learn
* NumPy
* Pandas

## TinyML

* TensorFlow Lite
* TensorFlow Lite Micro
* Edge AI

## Hardware

* ESP32
* Accelerometer Sensor

## Backend & API

* REST API
* Swagger API
* JSON Data Integration

## Visualization

* Matplotlib

---

# Installation

## Clone Repository

```bash
git clone https://github.com/Yeabebe/earthquake-detection-ai.git
```

---

## Navigate to Project

```bash
cd earthquake-detection-ai
```

---

## Install Requirements

```bash
pip install -r requirements.txt
```

---

# Running the Notebooks

Open Jupyter Notebook or Google Colab.

Run:

```text
earthquake_tinyml_model.ipynb
```

or

```text
earthquake_lstm_model.ipynb
```

or

```text
esp32_vibration_tinyml_model.ipynb
```

---

# TensorFlow Lite Conversion

Models are converted into `.tflite` format for TinyML deployment.

Example:

```python
converter = tf.lite.TFLiteConverter.from_keras_model(model)

tflite_model = converter.convert()

with open("model.tflite", "wb") as f:
    f.write(tflite_model)
```

---

# TinyML Deployment

The generated `.tflite` models can be deployed on:

* ESP32
* TensorFlow Lite Micro
* Edge AI devices
* Embedded systems

---

# Sample Prediction

```python
result = predict_vibration(
    0.02,
    0.01,
    0.98,
    0.98,
    0.019
)

print(result)
```

Output:

```text
Possible Earthquake
```

---

# Future Improvements

* Real earthquake early warning system
* Live streaming sensor analysis
* Multi-device ESP32 network
* Cloud dashboard integration
* GPS integration
* Advanced anomaly detection
* Federated learning
* Mobile app integration

---

# Research & Educational Purpose

This project was developed for:

* AI research
* TinyML experimentation
* Earthquake analysis
* Embedded AI learning
* IoT + AI integration
* Educational demonstrations

---

# Author

Yeabsera Abebe

* Electrical and Computer Engineering Student
* AI Engineer
* Full-Stack Developer
* Business Developer

---

# License

This project is licensed under the MIT License.

---

# Acknowledgements

* IRIS Earthquake Dataset
* TensorFlow
* Google Colab
* ESP32 Community
* Open Source AI Community
