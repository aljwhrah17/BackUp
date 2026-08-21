# BackUp System 🦾🚨

An IoT-based healthtech prototype for real-time posture monitoring and feedback.

## 📌 About the Project
BackUp is an interactive hardware prototype designed to monitor sitting habits and reduce back strain in real-time. When poor posture is detected, the system triggers a physical feedback alert using a vibration motor, helping users maintain a healthy posture throughout the day.

## 🛠️ Hardware & Components
* Microcontroller: ESP32
* Sensor: MPU6050 (Accelerometer & Gyroscope)
* Actuator: Vibration Motor
* Development Environment: Arduino IDE (C/C++)

## ⚙️ How It Works
1. Calibration: The MPU6050 sensor establishes a baseline angle for the user's correct upright sitting posture upon startup.
2. Real-time Monitoring: The ESP32 continuously reads acceleration and angle data from the sensor.
3. Alert Mechanism: If the user slouches or deviates from the baseline beyond a predefined threshold for a specific duration, the system activates the vibration motor to alert them to correct their posture.

## 💻 Code Snippet
Here is a glimpse of the core logic implemented on the ESP32:

```cpp
// Sample logic for threshold checking
if (abs(currentAngle - baselineAngle) > threshold) {
    digitalWrite(vibrationPin, HIGH); // Trigger alert
} else {
    digitalWrite(vibrationPin, LOW);  // Safe posture
}
