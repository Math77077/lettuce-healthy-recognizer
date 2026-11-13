# Contributing Guide

Thank you for your interest in contributing to the **Lettuce Disease Detection** project! This repository contains a Deep Learning-based computer vision pipeline to identify health conditions in lettuce crops using YOLO11 and RT-DETR.

Follow the steps below to contribute efficiently and safely.

## What’s in this repository?
- **Jupyter Notebook (`01_lettuce_disease_detection.ipynb`)**: The core pipeline for dataset downloading, rebalancing, model training, and qualitative video inference.
- **Python Setup**: Environment dependencies via `requirements.txt`.
- **Documentation**: Bilingual instructions and theoretical background.

## Requirements
Before contributing, make sure you have:
- Python 3.12+
- PyTorch with CUDA support (e.g., PyTorch 2.14.0 as tested in our benchmark).
- Jupyter Lab or VS Code with Jupyter extension.
- Ultralytics library (v8.4.208).
- Sufficient GPU memory for training (min 6GB VRAM, RTX 4050 tested).

## How to contribute

1. **Fork the repository** (GitHub UI).
2. **Clone your fork**
   ```bash
   git clone [https://github.com/Math77077/lettuce-healthy-recognizer.git](https://github.com/Math77077/lettuce-healthy-recognizer.git)
   cd lettuce-healthy-recognizer
   ```
3. **Create a new branch**
    Use a descriptive name and prefix:
    ```bash
    git checkout -b feature/add-new-model
    # or
    git checkout -b bugfix/fix-eval-protocol
    # or
    git checkout -b docs/update-readme

    ```

4. **Make your changes**
    * Keep dataset and modeling changes modular.
    * Do not commit large datasets, model weights (`.pt`), or cache files. Ensure they remain ignored by `.gitignore`.

5. **Commit your changes**
    Write clear commit messages (using Conventional Commits format):
    ```bash
    git commit -m "feat(model): integrate YOLOv10 baseline comparison"
    ```

6. **Push your branch and Open a Pull Request**

## Best practices (Machine Learning)

* **Reproducibility:** If you change model hyperparameters, document the seed and configuration to ensure reproducibility.
* **Memory Management:** Ensure memory clearing blocks (`gc.collect()`, `torch.cuda.empty_cache()`) remain intact when adding new training cells.
* **Dataset Integrity:** Do not change the 80/20 split logic for the main benchmark unless explicitly opening a discussion for a new protocol.

## Good contribution ideas

* Add a script for K-Fold Cross Validation.
* Implement robust tracking algorithms for continuous video inference.
* Expand data augmentation tests to improve model generalization.
* Integrate an explainable AI (XAI) tool like Grad-CAM.