# IoMT Cross Layer Dataset (X-IoMT)

>**Dataset summary:**  
>X-IoMT is a publicly available dataset for anomaly detection research in **Internet of Medical Things (IoMT)** environments. It addresses the limitations of existing datasets that focus on a single layer or narrow attack type by providing cross-layer coverage across the **perception**, **network**, and **application** layers of **IoT architectures**.
>The dataset contains both benign and malicious traffic, including adversarially perturbed samples generated using **Fast Gradient Sign Method (FGSM)** and **Projected Gradient Descent (PGD)** under **L₂** and **L∞** norms. These augmentations enable evaluation of models under common and adversarial attack conditions.
>X-IoMT offers a realistic foundation for **benchmarking** and developing robust, reliable **anomaly detection** models with multi-layer visibility and adversarial resilience. It is fully open to the research community to promote reproducibility and progress toward more secure IoMT systems.

## At a glance
- **Name:** IoMT Cross Layer Dataset (X-IoMT);
- **Version:** ⚑v1.0 (2025-11);
- **Size:** ⚑923 files, ⚑2.8G;
- **Format:** CSV (derived from PCAP with added features);
- **Records:** ⚑Original Dataset *(N = 1.579.704)*, Adversarial Augmented dataset *(N = 12.105.496)*, combine into a Complete dataset *(N =13685200)*;  
- **Labels:** *anomaly.layer* (Perception, Network, Application), *anomaly.name* (each anomaly name), *anomaly.label* (0 = Normal or 1 = Anomaly);
- **Protocols:** IP/TCP/, HTTP, MQTT;
- **Capture scope:** traffic between IoT nodes and servers/MQTT brokers;
- **Intended use:** anomaly detection, traffic classification, IoT/IoMT security research, benchmarking.

## Cite this work
If you use this dataset, please cite the paper and the dataset:

```bibtex
%Article
@INPROCEEDINGS{11261583,
  author={Pinto, Rui P. and Silva, Bruno M. C. and Inácio, Pedro R. M.},
  booktitle={2025 23rd International Symposium on Network Computing and Applications (NCA)}, 
  title={Anomaly Detection in the Internet of Medical Things: Design and Evaluation of a Cross Layer Dataset}, 
  year={2025},
  volume={},
  number={},
  pages={255-262},
  keywords={Performance evaluation;Cross layer design;Internet of Medical Things;Machine learning;Reliability;Labeling;Computer crime;Anomaly detection;Standards;Monitoring;Internet of Medical Things (IoMT);Machine Learning (ML);Anomaly Detection;Cybersecurity;Data Labeling},
  doi={10.1109/NCA67271.2025.00047}}


%Dataset
@dataset{XIoMTDataset,
  title       = {X-IoMT},
  author      = {Rui P. Pinto, Bruno M. C. Silva, Pedro R. M. Inácio},
  year        = {2025},
  publisher   = {GitHub},
  url         = {(https://github.com/RuiPintoUBI/X-IoMTDataset)}
}
```

## Repository Layout
```text
X-IoMTDataset/
|── OriginalDataset/
│   ├── ApplicationAnomaliesAbnormalBreathing_High_RR.csv			  # Application Anomaly             
│   ├── ApplicationAnomaliesAbnormalBreathing_Low_RR.csv			  # Application Anomaly
│   ├── ApplicationAnomaliesArrhythmia_SignalArtifact.csv			  #  Application Anomaly
│   ├── ApplicationAnomaliesBradycardia.csv						          # Application Anomaly
│   ├── ApplicationAnomaliesClinical.csv							          # Application Anomaly
│   ├── ApplicationAnomaliesHypoxemia.csv						            # Application Anomaly
│   ├── ApplicationAnomaliesTachycardia.csv						          # Application Anomaly
│   ├── NetworkAnomaliesFINFlood_part_001.csv … part_007.csv		# Network Anomaly
│   ├── NetworkAnomaliesMQTTBruteForce.csv						          # Network Anomaly
│   ├── NetworkAnomaliesMQTTDoS_part_001.csv … part_007.csv		  # Network Anomaly
│   ├── NetworkAnomaliesReconAttack_part_001.csv … part_002.csv	# Network Anomaly	
│   ├── NetworkAnomaliesSlowloris_part_001.csv … part_009.csv		# Network Anomaly
│   ├── NetworkAnomaliesSYNFlood_part_001.csv … part_007.csv		# Network Anomaly
│   ├── NormalTrafficHTTP_part_001.csv … part_007.csv				    # Normal Traffic
│   ├── NormalTrafficMQTT_part_001.csv .. part_058.csv				  # Normal Traffic
│   ├── PhysicalAnomaliesHTTP.csv								                # Perception Anomaly
│   └── PhysicalAnomaliesMQTT_part_001.csv … part_003.csv			  # Perception Anomaly
|── AugmentedDataset/
│   ├── adv_out_fgsm_eps0.1_part_001.csv … part_020.csv    			# Adversarial Samples FGSM  ε = 0.1
│   ├── adv_out_fgsm_eps0.2_part_001.csv … part_040.csv    			# Adversarial Samples FGSM ε = 0.2
│   ├── adv_out_fgsm_eps0.05_part_001.csv … part_040.csv    		# Adversarial Samples FGSM ε = 0.05
│   ├── adv_out_pgd_l2_eps0.1_part_001.csv … part_119.csv			  # Adversarial Samples PGD L₂ norm ε = 0.1
|   ├── adv_out_pgd_l2_eps0.2_part_001.csv … part_119.csv			  # Adversarial Samples PGD L₂ norm ε = 0.2
|   ├── adv_out_pgd_l2_eps0.05_part_001.csv … part_119.csv			# Adversarial Samples PGD L₂ norm ε = 0.05
|   ├── adv_out_pgd_linf_eps0.1_part_001.csv … part_119.csv			# Adversarial Samples PGD L∞ norm ε = 0.1
|   ├── adv_out_pgd_linf_eps0.2_part_001.csv … part_119.csv			# Adversarial Samples PGD L∞ norm ε = 0.2
│   └── adv_out_pgd_linf_eps0.05_part_001.csv … part_003.csv		# Adversarial Samples PGD L∞ norm ε = 0.05
```

## Download
```text
git lfs install
git clone https://github.com/RuiPintoUBI/X-IoMTDataset.git
```

## Schema
Dataset features obtained from packet capture conversion and curated labeling:
| **#** | **Feature**            | **Description**                                                     | **Categories**              |
|-------|------------------------|---------------------------------------------------------------------|-----------------------------|
| 1     | frame.time             | Timestamp of packet capture (Unix epoch time)                       | Packet and Network Features |
| 2     | ip.src_host            | Source IP address                                                   | Packet and Network Features |
| 3     | ip.dst_host            | Destination IP address                                              | Packet and Network Features |
| 4     | tcp.srcport            | Source TCP port number                                              | Packet and Network Features |
| 5     | tcp.dstport            | Destination TCP port number                                         | Packet and Network Features |
| 6     | tcp.seq                | TCP sequence number                                                 | Packet and Network Features |
| 7     | tcp.ack                | TCP acknowledgment number                                           | Packet and Network Features |
| 8     | tcp.flags.syn          | TCP control flag (boolean)                                          | Packet and Network Features |
| 9     | tcp.flags.ack          | TCP control flag (boolean)                                          | Packet and Network Features |
| 10    | tcp.flags.fin          | TCP control flag (boolean)                                          | Packet and Network Features |
| 11    | tcp.flags.reset        | TCP control flag (boolean)                                          | Packet and Network Features |
| 12    | tcp.flags.push         | TCP control flag (boolean)                                          | Packet and Network Features |
| 13    | tcp.flags.urg          | TCP control flag (boolean)                                          | Packet and Network Features |
| 14    | tcp.len                | Length of TCP segment                                               | Packet and Network Features |
| 15    | http.request.method    | HTTP request method (e.g., GET, POST)                               | HTTP Protocol Features      |
| 16    | http.request.full_uri  | Full URI requested                                                  | HTTP Protocol Features      |
| 17    | http.request.version   | HTTP protocol version                                               | HTTP Protocol Features      |
| 18    | http.request.uri.query | Query string of the request                                         | HTTP Protocol Features      |
| 19    | http.referer           | Referring page                                                      | HTTP Protocol Features      |
| 20    | http.content_length    | Content length of request/response                                  | HTTP Protocol Features      |
| 21    | http.file_data         | Content in the HTTP request                                         | HTTP Protocol Features      |
| 22    | http.response          | Status code HTTP response                                           | HTTP Protocol Features      |
| 23    | mqtt.msgtype           | Type of MQTT message                                                | MQTT Protocol Features      |
| 24    | mqtt.msg               | Raw message payload                                                 | MQTT Protocol Features      |
| 25    | mqtt.topic             | MQTT topic name                                                     | MQTT Protocol Features      |
| 26    | mqtt.topic_len         | Length of topic string                                              | MQTT Protocol Features      |
| 27    | mqtt.conflags          | Connection flags                                                    | MQTT Protocol Features      |
| 28    | mqtt.conflag.cleansess | Clean session flag (boolean)                                        | MQTT Protocol Features      |
| 29    | mqtt.len               | Length of MQTT message                                              | MQTT Protocol Features      |
| 30    | mqtt.proto_len         | Protocol name lenght                                                | MQTT Protocol Features      |
| 31    | mqtt.protoname         | Protocol name (e.g., "MQTT")                                        | MQTT Protocol Features      |
| 32    | mqtt.ver               | Protocol version number                                             | MQTT Protocol Features      |
| 33    | mqtt.msg_decoded_as    | Decoded type of message                                             | MQTT Protocol Features      |
| 34    | mqtt.conack.flags      | Connection acknowledgment flags                                     | MQTT Protocol Features      |
| 35    | mqtt.hdrflags          | Header flags of MQTT packet                                         | MQTT Protocol Features      |
| 36    | mqtt.qos               | Quality of Service level                                            | MQTT Protocol Features      |
| 37    | mqtt.retain            | Retain flag                                                         | MQTT Protocol Features      |
| 38    | mqtt.dupflag           | Duplicate delivery flag                                             | MQTT Protocol Features      |
| 39    | ip.ttl                 | Time-To-Live                                                        | Packet and Network Features |
| 40    | tcp.window_size        | Advertised TCP receive window size                                  | Packet and Network Features |
| 41    | http.user_agent        | Client application generating the request                           | HTTP Protocol Features      |
| 42    | http.host              | Host header of the HTTP request                                     | HTTP Protocol Features      |
| 43    | mqtt.clientid          | Identifier of MQTT client                                           | MQTT Protocol Features      |
| 44    | frame.len              | Size of the frame (in bytes)                                        | Packet and Network Features |
| 45    | frame.protocols        | Protocols involved in the packet (e.g., eth:ip:tcp:http)            | Packet and Network Features |
| 46    | Temperature            | Body temperature                                                    | Device/Patient Telemetry    |
| 47    | Memory                 | Memory usage on the device (in \%)                                  | Device/Patient Telemetry    |
| 48    | In_Temperature         | Internal device temperature sensor reading                          | Device/Patient Telemetry    |
| 49    | CPU                    | CPU clock rate of the device (in MHz)                               | Device/Patient Telemetry    |
| 50    | RSSI                   | Received Signal Strength Indicator (dBm)                            | Device/Patient Telemetry    |
| 51    | MAC_extracted          | Device MAC address                                                  | Device/Patient Telemetry    |
| 52    | HR                     | Heart rate measurement (bpm)                                        | Device/Patient Telemetry    |
| 53    | Pulse                  | Pulse value                                                         | Device/Patient Telemetry    |
| 54    | RESP                   | Respiration rate                                                    | Device/Patient Telemetry    |
| 55    | SpO2                   | Blood oxygen saturation (\%)                                        | Device/Patient Telemetry    |
| 56    | anomaly.layer          | Layer of anomaly (0=Normal, 1=Perception, 2=Network, 3=Application) | Labels                      |
| 57    | anomaly.name           | Type of anomaly (e.g., DoS, overheating, abnormal clinical data)    | Labels                      |
| 58    | anomaly.label          | Ground truth label (Normal = 0,  Anomaly = 1)                       | Labels                      |

## Changelog
v1.0 (2025-11): Initial public release. 

## Contact
Maintainer: ⚑Rui Pedro Pinto (UBI) — ⚑rui.pinto@ubi.pt

## Issues 
Please use GitHub Issues for bug reports and questions.

## Acknowledgments
This work is funded by national funds through FCT – Fundação para a Ciência e a Tecnologia, I.P., and, when eligible, co-funded by EU funds under project/support UID/50008/2025 – Instituto de Telecomunicações, with DOI identifier <https://doi.org/10.54499/UID/50008/2025>
