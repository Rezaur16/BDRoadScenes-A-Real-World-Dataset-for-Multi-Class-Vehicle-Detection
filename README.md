# BDRoadScenes: A Real-World Dataset for Multi-Class Vehicle Detection

BDRoadScenes is a real-world road scene dataset designed for **multi-class vehicle detection** research.  
It focuses on traffic scenarios commonly found on roads in Bangladesh and can be used to train and evaluate computer vision models for object detection.

---

## 📌 Why this dataset matters

Many public traffic datasets are collected in different countries and may not represent local road conditions in Bangladesh (e.g., mixed traffic patterns, vehicle diversity, and challenging road environments).  
**BDRoadScenes** helps researchers and developers build models that are more suitable for these real-world local scenarios.

---

## 🎯 Main objective

The dataset is intended for:

- Detecting multiple types of vehicles in road images
- Training object detection models
- Benchmarking and comparing detection performance
- Supporting research in intelligent transportation and traffic monitoring

---

## 🚗 Vehicle categories (multi-class)

The dataset is organized for **multi-class detection**, meaning each detected object belongs to a specific vehicle class (for example: car, bus, truck, motorcycle, etc., depending on the annotation schema used in the project).

> If you use this dataset in a model pipeline, make sure your class names exactly match the annotation labels.

---

## 🗂️ Dataset structure (general)

The project notebook (`BDRoadScenes.ipynb`) demonstrates dataset usage and processing workflow.  
A typical object detection dataset structure is as follows:

```text
BDRoadScenes/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
├── labels/
│   ├── train/
│   ├── val/
│   └── test/
├── data.yaml (or equivalent config)
└── BDRoadScenes.ipynb
```

### What each folder means

- **images/**: Road scene image files  
- **labels/**: Annotation files containing object class + bounding box information  
- **train/ val/ test/**:
  - **train** → used to teach the model  
  - **val** → used to tune model performance during training  
  - **test** → used for final unbiased evaluation

---

## 🧪 Workflow shown in the notebook

The notebook is used as the main working file for the project pipeline.  
Typical steps include:

1. Loading dataset paths and files  
2. Reading image-label pairs  
3. Verifying class annotations  
4. Preparing data splits (train/validation/test)  
5. Training or testing a detection model  
6. Evaluating model performance

---

## ⚙️ How to use this project

1. Clone this repository
2. Open `BDRoadScenes.ipynb` in Jupyter Notebook / JupyterLab / Google Colab
3. Update dataset paths if needed
4. Run cells step by step
5. Train/evaluate your detection model

---

## ✅ Recommended environment

- Python 3.8+
- Jupyter Notebook
- Common ML libraries (depending on notebook code), such as:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - deep learning framework packages used in the notebook

If dependency errors appear, install missing packages with:

```bash
pip install <package-name>
```

---

## 📈 Suggested evaluation metrics

For multi-class vehicle detection, commonly used metrics include:

- **mAP (mean Average Precision)**
- **Precision**
- **Recall**
- **Per-class AP**

These metrics help measure both overall detection quality and class-wise performance.

---

## 🤝 Who can use this dataset?

This dataset is useful for:

- Researchers in computer vision and transport AI
- University students working on thesis/projects
- Developers building smart traffic systems
- Anyone interested in real-world vehicle detection in South Asian road conditions

---

## 📜 License

This repository includes a license file:

- [LICENSE](./LICENSE)

Please check license terms before redistribution or commercial use.

---

## 📚 Citation

If you use this dataset in your research, please cite this repository and acknowledge the authors appropriately.

---

## 🙌 Acknowledgment

Thanks to everyone involved in collecting, preparing, and organizing real-world road scene data for advancing traffic AI research.
