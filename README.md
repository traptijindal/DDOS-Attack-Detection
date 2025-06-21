# 🚨 DDoS Attack Detection Using Machine Learning

This project was built to detect Distributed Denial of Service (DDoS) attacks using network traffic data. It uses a machine learning model trained on key traffic-based features to classify whether the behavior of a source IP is malicious or normal.

---

## 🔍 Problem Statement

DDoS attacks aim to overwhelm a server or network by flooding it with traffic, often from multiple sources. Early detection is crucial to prevent downtime and protect sensitive infrastructure.

---

## ⚙️ How It Works

1. **Capture Network Traffic**  
   Use tools like **Wireshark** to capture live packets while interacting with the website (e.g., login, browse pages).

2. **Export to `.pcap` File**  
   After traffic is captured, export the session as a `.pcap` file from Wireshark.

3. **Feature Extraction**  
   Run the provided Python script to extract key features from the `.pcap` file:
   - `pktcount`: Number of packets
   - `bytecount`: Total bytes transferred
   - `flows`: Number of flows from the IP
   - `dt`: Average time gap between packets
   - `tot_dur`: Total connection duration
   - `dur`: Duration per flow
   - `pktrate`: Packets per second
   - `pktperflow`: Average packets per flow
   - `rx_bytes`: Bytes received
   - `tx_bytes`: Bytes sent

4. **Model Prediction**  
   These extracted features are used as input to a trained **Random Forest Classifier** which outputs whether the source IP is:
   - 🟢 Normal Traffic
   - 🔴 DDoS Attack

---

## 🧪 Dataset

We used a public SDN-based DDoS dataset from **Kaggle**, and also support real-time `.pcap` testing through Wireshark capture.

---


