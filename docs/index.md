---
layout: default
title: IoMT Cross Layer Dataset (X-IoMT)
---

# IoMT Cross Layer Dataset (X-IoMT)

## A cross-layer IoMT anomaly detection dataset with adversarial samples (FGSM/PGD) across Perception, Network, and Application layers.

[View on GitHub](https://github.com/RuiPintoUBI/X-IoMTDataset)

- [Overview](#at-a-glance)
- [Download](#download)
- [Schema](#schema)
- [Citation](#citation)
- [Contact](#contact)

# At a glance
- **Version:** v1.0 (2025-11)  
- **Size:** 923 files (~2.8 GB)  
- **Format:** CSV (derived from PCAP with engineered features)  
- **Records:** Original 1,579,704 + Adversarial 12,105,496 = **Total 13,685,200**  
- **Protocols:** IP/TCP, HTTP, MQTT  
- **Labels:** `anomaly.layer`, `anomaly.name`, `anomaly.label`

# Download
```bash
git lfs install
git clone https://github.com/RuiPintoUBI/X-IoMTDataset.git
```

# Schema

# Citation
Article
@INPROCEEDINGS{11261583,
  author    = {Pinto, Rui P. and Silva, Bruno M. C. and Inácio, Pedro R. M.},
  booktitle = {2025 23rd International Symposium on Network Computing and Applications (NCA)},
  title     = {Anomaly Detection in the Internet of Medical Things: Design and Evaluation of a Cross Layer Dataset},
  year      = {2025},
  pages     = {255--262},
  doi       = {10.1109/NCA67271.2025.00047}
}

Dataset
@dataset{XIoMTDataset,
  title     = {X-IoMT},
  author    = {Rui P. Pinto and Bruno M. C. Silva and Pedro R. M. Inácio},
  year      = {2025},
  publisher = {GitHub},
  url       = {https://github.com/RuiPintoUBI/X-IoMTDataset}
}

# Reproducibility

All experiments were conducted using fixed random seeds to ensure repeatability
(NumPy and scikit-learn seed = 42; TensorFlow seed = 42).

Dataset generation and model training were performed on a Linux-based workstation
equipped with an NVIDIA GeForce RTX 5060 Ti GPU and an AMD-class CPU.

The software environment included:

Python 3.10

NumPy 1.26

pandas 2.1

scikit-learn 1.4

TensorFlow 2.21

These settings are reported to facilitate reproducibility and fair comparison in future studies.

# Contact

Maintainer: Rui Pedro Pinto (UBI)
📧 Email: rui.pinto@ubi.pt

# Changelog

v1.0 (2025-11): Initial public release

v1.1 (2026-01): Improved anomalies and added a small explained implementation

# Acknowledgments

This work is funded by national funds through FCT – Fundação para a Ciência e a Tecnologia, I.P.,
and, when eligible, co-funded by EU funds under project/support UID/50008/2025 – Instituto de Telecomunicações,
DOI: https://doi.org/10.54499/UID/50008/2025
