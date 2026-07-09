# MediNet-XG: Lightweight CNN for Medicinal Plant Classification

**Final Year Thesis Project** — Md. Nur A Alam
🔗 [GitHub Repository](https://github.com/Md-Nur-A-Alam/MediNet-XG-Final-year-thesis)

---

## 🌿 What Is This Project? (For Everyone)

Imagine you're a farmer, herbalist, or field researcher standing in a garden of medicinal plants. Some of these plants are healthy and valuable. Others are infested with weeds that reduce their quality or make them unsafe to use. Telling them apart quickly — especially at scale — is hard to do by eye alone.

**MediNet-XG** is an AI system, built into a tiny, efficient app-ready model, that looks at a photo of a medicinal plant and instantly tells you whether it is healthy or weed-infested. Think of it as a "plant doctor in your pocket" — no lab equipment, no expert botanist required, just a camera and a phone.

### Why It Matters
- **Accessible**: Runs on ordinary mobile phones and small edge devices (like Raspberry Pi), not just powerful servers.
- **Accurate**: Gets it right about 99 times out of 100.
- **Fast & Lightweight**: The entire "brain" of the system is smaller than a single photo (342 KB) — small enough to load instantly.
- **Practical**: Useful for farmers, agricultural extension officers, herbal medicine producers, and researchers who need quick, reliable plant screening in the field.

---

## 🧠 What Is This Project? (For Technical Readers)

MediNet-XG is a custom-designed, **task-specific lightweight Convolutional Neural Network (CNN)** built for binary/multi-class image classification of medicinal plants, distinguishing healthy specimens from weed-infested ones.

Rather than fine-tuning a large, generic pretrained model (transfer learning), this project designs a CNN **from the ground up**, optimized specifically for this classification task — resulting in a model that is both more accurate and dramatically smaller than heavier transfer-learning baselines.

### Core Technology

| Component | Description |
|---|---|
| **Architecture** | Custom lightweight CNN using **inverted residual blocks** (as popularized by MobileNetV2) — expand → depthwise convolve → project, which reduces computation while preserving representational power |
| **Attention Mechanism** | **Selective channel attention** modules that let the network dynamically emphasize the most informative feature channels (e.g., leaf texture, discoloration, weed patterns) while suppressing irrelevant noise |
| **Optimization Target** | Jointly optimized for **accuracy** and **model size**, rather than accuracy alone — designed explicitly for edge/mobile deployment |
| **Domain** | Computer Vision → Fine-grained image classification → Agricultural/botanical imagery |

### Key Results

- ✅ **98.82% classification accuracy**
- ✅ **98.79% F1-score** (balanced precision & recall — important since misclassifying an infested plant as healthy carries real-world risk)
- ✅ **342 KB model size** — small enough to embed directly in a mobile app or run on microcontroller-class edge hardware
- ✅ **Outperformed heavier transfer-learning models** (e.g., standard pretrained CNNs like ResNet/MobileNet fine-tuned on the same data), proving that a well-designed small model can beat a "bigger but generic" one

### Why Inverted Residuals + Channel Attention?

- **Inverted residual blocks** keep the number of parameters and FLOPs low by working in a low-dimensional "bottleneck" space, only expanding briefly to extract features — this is what keeps the model at 342 KB instead of tens of megabytes.
- **Selective channel attention** compensates for the reduced capacity of a small network by teaching it *where to look* — effectively giving a small model some of the discriminative power of a much larger one, which is why MediNet-XG can match or beat transfer-learning approaches despite its size.

### Deployment Suitability

The combination of high accuracy and extremely small footprint makes MediNet-XG well-suited for:
- **Real-time inference** on mobile devices (Android/iOS)
- **Edge/IoT deployment** (e.g., Raspberry Pi, Jetson Nano, or similar low-power boards)
- **Offline use** in rural/field settings with limited or no internet connectivity

---

## 🎯 Core Features

- 📸 Image-based classification of medicinal plants: **healthy vs. weed-infested**
- ⚡ Extremely low latency due to tiny model size
- 📱 Mobile & edge-device ready — no cloud/server dependency required
- 🎯 High precision suitable for real-world agricultural decision-making
- 🧩 Modular architecture (attention blocks can be tuned/extended for related plant-health tasks)

---

## 🛠️ Tech Stack

- **Language**: Python
- **Domain**: Deep Learning / Computer Vision
- **Model Type**: Custom lightweight CNN (inverted residual blocks + selective channel attention)

---

## 📈 Impact & Use Cases

| Use Case | Beneficiary |
|---|---|
| On-field plant health screening | Farmers, herbal cultivators |
| Quality control before harvest/processing | Herbal medicine manufacturers |
| Agricultural extension & advisory tools | Government/NGO agri-programs |
| Research data collection | Botanists, agri-researchers |

---

## 📚 About This Project

MediNet-XG was developed as a final year thesis project, demonstrating that carefully engineered lightweight architectures can outperform larger transfer-learning models on specialized domains — a valuable lesson for any resource-constrained AI application in agriculture, healthcare, or edge computing.
