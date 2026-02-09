---
title: IoMT Cross Layer Dataset (X-IoMT)
---

# IoMT Cross Layer Dataset (X-IoMT)

**X-IoMT** is a publicly available cross-layer dataset for anomaly detection research in Internet of Medical Things (IoMT) environments.  
It provides **perception, network, and application layer coverage**, including **benign traffic, real attacks, and adversarially perturbed samples**.

---

## 📌 At a glance
- **Version:** v1.0 (2025-11)  
- **Size:** 923 files (~2.8 GB)  
- **Format:** CSV (derived from PCAP with engineered features)  
- **Records:**  
  - Original: 1,579,704  
  - Adversarial: 12,105,496  
  - **Total:** 13,685,200  
- **Protocols:** IP/TCP, HTTP, MQTT  
- **Labels:** `anomaly.layer`, `anomaly.name`, `anomaly.label`

---

## 📥 Download
```bash
git lfs install
git clone https://github.com/RuiPintoUBI/X-IoMTDataset.git

