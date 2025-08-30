# Solosapp – Data Fetcher for Smart Glasses

**Solos** is a lightweight and efficient Android-based app designed for **smart glasses**. It collects sensor data (accelerometer, gyroscope, magnetometer) directly from the glasses and streams it to a **RabbitMQ server** for real-time **Human Activity Recognition (HAR)**.

---

## 🚀 Features

* 👓 Real-time **smart glasses sensor data transmission**
* 🧠 Seamless integration with activity recognition pipelines
* 🐇 **RabbitMQ** message brokering for reliable streaming
* 💻 Java-based backend consumer for data handling

---

## 📦 How to Use

1. Configure the RabbitMQ server’s **IP address** and **port** in the Solos app.
2. Select the sensors available on the smart glasses.
3. Tap **Start** to begin streaming data in real time.

> ⚠️ **Important**: Ensure proper setup of RabbitMQ and consumer scripts before starting.

---

## 🛠 Platform Setup Guide

### 1. RabbitMQ Installation

* Download from [RabbitMQ Downloads](https://www.rabbitmq.com/download.html)
* Enable management UI:

  ```bash
  cd "C:\Program Files\RabbitMQ Server\rabbitmq_server-{version}\sbin"
  rabbitmq-plugins enable rabbitmq_management
  ```
* Access UI at: `http://localhost:15672`

### 2. Create User

* Username: `test`
* Password: `test`
* Tags: `administrator`
* Note: Guest users cannot connect remotely.

### 3. Java Consumer Setup

**Required files:**

* `SensorDataConsumer.java`
* `amqp-client-5.21.0.jar`
* `slf4j-api-2.0.13.jar`
* `slf4j-simple-2.0.13.jar`

**Run steps:**

```bash
javac SensorDataConsumer.java
java SensorDataConsumer
```

### 4. Firewall

Open ports **15672** and **5672** in Windows Firewall.

---

### **📱 5. Solos Smart Glasses App Setup**

Install the Solos mobile app on your smartphone (via Android Studio or APK).

Pair your Solos smart glasses with your smartphone via Bluetooth.

Inside the app, configure the following settings:

RabbitMQ Server IP

Port: 5672

Username: test

Select which sensors from the glasses you want to stream.

Check sendDataService.java for credential configurations.

---

## ✅ Testing

* Start RabbitMQ and the Java consumer
* Launch the Solos app on your glasses and begin streaming
* Monitor logs and RabbitMQ UI (`Queues`, `Connections` tabs)

---

## 🤝 Contributing

Contributions are welcome! Fork, submit PRs, or report issues to help improve **Solos**.

---

Do you want me to also **differentiate Solos from MotionIQ** in the README (like highlighting that it’s optimized for **wearable sensors on glasses**) or keep it **fully parallel** to MotionIQ?
