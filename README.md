# Final Course Project
- Federal University of Roraima
- Bachelor's Degree in Computer Science
- Author: Natália Ribeiro de Almada
- Advisor: Professor Dr. Herbert Oliveira Rocha

## Elderly Fall Detection Project

This project aims to use two existing models (YOLO-NAS and YOLOv8) to compare their performance, first with the original dataset provided with the models and then with adaptations for an author-created dataset, enabling performance evaluation.
# Author-Created Dataset:
> [!WARNING]
> **Legal Disclaimer:** This dataset consists of frames extracted from videos and made available from publicly accessible YouTube videos, compiled exclusively for non-commercial academic research and the development of computer vision systems for elderly fall detection. By using it, you expressly agree that:

> All visual material comes from public videos, but intellectual property remains with the original rights holders (creators, institutions, or individuals), according to [YouTube](https://www.youtube.com/t/terms) Terms of Service and copyright law;

> Frame extraction does not authorize commercial use, redistribution, or applications outside health research, elderly safety, or data science;

> Commercial use or publication of the images requires explicit permission from the rights holders;

- The creator of this dataset is not responsible for:

> Copyright or image rights violations committed by users,

> Clinical accuracy or bias in the compiled data,

> Consequences of misuse (unauthorized surveillance, algorithmic discrimination, etc.).


```bash

├── 156 videos                  ← Training/validation/test images
│   ├── 53 videos of elderly people labeled as "No Fall"/
│   └── 103 videos of elderly people labeled as "Fall"
│ └── 648 frames total          ← Split: training=70% / validation=20% / test=10%
10 videos were kept fully separate and never used in training, for final testing.
Classes: "fall" and "person"
````
> [Dataset Organized for v8](https://github.com/nataliaalmada/projects/tree/main/visionfall/Modelo_YOLOv8_Dataset_Autoral/dataset)

> [Dataset Organized for NAS](https://github.com/nataliaalmada/projects/tree/main/visionfall/Modelo_YOLO_NAS_Dataset_Autoral/datasetNAS)

> [Videos Separated for Final Testing](https://github.com/nataliaalmada/projects/tree/main/visionfall/Modelo_YOLOv8_Dataset_Autoral/videos_teste)
## YOLOv8 with Author-Created Dataset:
Project executed on Windows 11

P2_YOLOv8
   ```bash

│
├── dataset/                 ← Training/validation/test images
│   ├── images/
│   └── data.yaml
│
├── videos_testes_validacao/← Validation videos
├── videos_teste/           ← Test videos (never used in training at any stage)
├── runs/
│   └── detect/
│       └── predict/        ← Inference outputs
│           ├── queda/
│           └── naoQueda/
│
├── treinamento_yolo_com_relatorio.ipynb ← Notebook with full pipeline
└── requirements.txt         ← Project dependencies

```


### 🚀 Features

- YOLOv8 model training and validation with custom data.
- Evaluation with external videos.
- Automatic classification of test videos:
  - Videos with **fall** detection → `videos_saida/queda/`
  - Videos **without fall** detection → `videos_saida/naoQueda/`
- Automatic **Telegram** alert delivery with attached video.
- Chart generation (IoU, Loss, Accuracy, Histograms, etc.) saved as PNG.

---

### 🛠️ Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/colocaroresto.git
   cd VisionFall
2. Use the notebook available at [Notebook on Colab](https://colab.research.google.com/drive/1Z2qt6rKFA-6tgDqdjNlNJybMGVslDUxy
).


## Execution
1. Create and activate a virtual environment (Windows):
    ```bash
    python -m venv venv
    .\venv\Scripts\activate

3. Install dependencies:
   ```bash
   pip install -r requirements.txt

3. Start the notebook:
   ```bash
   jupyter notebook

5. Run the cells.

## YOLO-NAS with Author-Created Dataset:
Project executed in WSL2 on Windows 11

P2_YOLO_NAS
   ```bash

│
├── datasetNAS/ # Custom dataset
│ ├── train/
│ ├── valid/
│ └── test/
│
├── videos_teste/ # Videos for testing with the trained model
├── videos_saida/
│ ├── queda/ # Videos where falls were detected
│ └── naoQueda/ # Videos with no fall detection
│
├── checkpoints/ # Saved trained model weights
└── fall-detection-yolo-nas-train-predict.ipynb
```


### 🚀 Features

- YOLOv8 model training and validation with custom data.
- Evaluation with external videos.
- Automatic classification of test videos:
  - Videos with **fall** detection → `videos_saida/queda/`
  - Videos **without fall** detection → `videos_saida/naoQueda/`
- Automatic **Telegram** alert delivery with attached video.
- Chart generation (IoU, Loss, Accuracy, Histograms, etc.) saved as PNG.

---
### ✅ Prerequisites

### WSL2 on Windows
Follow the official [Microsoft](https://learn.microsoft.com/pt-br/windows/wsl/install) guide.

You must install:
- **Ubuntu**
- **WSL2 as default**
- Install Miniconda in WSL, accept the terms, and allow it to be added to PATH.

### 🛠️ Installation

1. Create the Conda environment for the project:
   ```bash
conda create -n yolonas_env python=3.10 -y
conda activate yolonas_env
```
3. Clone the repository:
   ```bash
   cd /mnt/c/Users/YOUR_USER/Desktop
git clone https://github.com/YOUR_USER/P2_YOLO_NAS.git
cd P2_YOLO_NAS
````
4. Install dependencies:
   ```bash
   pip install -r requirements.txt
📓 How to run the notebook
5. Start Jupyter in WSL2:
 ```bash

conda activate yolonas_env
jupyter notebook
 ```
It will show a URL such as:

http://localhost:8888/?token=...
Copy and paste it into your Windows browser.

2. Open the notebook
Open the file:

 ```bash
fall-detection-yolo-nas-train-predict.ipynb
 ```
2. Run the cells.

📦 Training with your own dataset
Make sure your dataset is in YOLOv5/v8 format:

📹 Video Tests
Place up to 10 elderly-fall videos (.mp4) in:

videos_teste/
-After testing, the system will create:

````bash
videos_saida/
├── queda/
├── naoQueda/
````
### 📲 Telegram Integration (optional for both models)
### ✅ Prerequisites

### Have at least one [Telegram](https://web.telegram.org) account
1. Create an app at [Telegram](https://my.telegram.org)
configure the following information in the code:
```bash
api_id = 'YOUR_API_ID'
api_hash = 'YOUR_API_HASH'
phone = '+55xxxxxxxxx'
dest_user_id = YOUR_ID
dest_access_hash = YOUR_ACCESS_HASH
```

# YOLOv8 Reference Model
- Available on [GitHub](https://github.com/Tech-Watt/Fall-Detection)
following the tutorial by: [YouTube](https://youtu.be/wrhfMF4uqj8?si=bgvQIP8dlM2cwJRm) - Tech Watt

# YOLO-NAS Reference Model
- Model available on [Kaggle](https://www.kaggle.com/code/stpeteishii/fall-detection-yolo-nas-train-predict) by [@stpeteishii](https://www.kaggle.com/stpeteishii), or with small modifications required to run on WSL2 available on [Colab](https://drive.google.com/file/d/1k1Nu0BolRzG4UkjND6e6O2NIybvUXsCc/view?usp=sharing)
- Dataset available on [Kaggle](https://www.kaggle.com/datasets/elwalyahmad/fall-detection) by [@selwalyahmad](https://www.kaggle.com/elwalyahmad)
- COCO pre-trained weights available on [Hugging Face](https://huggingface.co/bdsqlsz/YOLO_NAS/blob/main/yolo_nas_l_coco.pth)
----------------------------------------------

@misc{supergradients,
  doi = {10.5281/ZENODO.7789328},
  url = {https://zenodo.org/record/7789328},
  author = {Aharon,  Shay and {Louis-Dupont} and {Ofri Masad} and Yurkova,  Kate and {Lotem Fridman} and {Lkdci} and Khvedchenya,  Eugene and Rubin,  Ran and Bagrov,  Natan and Tymchenko,  Borys and Keren,  Tomer and Zhilko,  Alexander and {Eran-Deci}},
  title = {Super-Gradients},
  publisher = {GitHub},
  journal = {GitHub repository},
  year = {2021},
}

@software{yolov8_ultralytics,
  author = {Glenn Jocher and Ayush Chaurasia and Jing Qiu},
  title = {Ultralytics YOLOv8},
  version = {8.0.0},
  year = {2023},
  url = {https://github.com/ultralytics/ultralytics},
  orcid = {0000-0001-5950-6979, 0000-0002-7603-6750, 0000-0003-3783-7069},
  license = {AGPL-3.0}
}
