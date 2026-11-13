# Detecção de Doenças em Alfaces com YOLO11 e RT-DETR

[![Language: English](https://img.shields.io/badge/Language-English-red.svg)](README.md)

Este repositório contém um pipeline de visão computacional baseado em Deep Learning projetado para identificar e classificar condições de saúde em lavouras de alface. O projeto compara o desempenho da arquitetura **YOLO11** com o Real-Time Detection Transformer (**RT-DETR**) para fornecer uma solução robusta voltada à agricultura de precisão.

## 📌 Visão Geral do Projeto

A identificação precoce de doenças foliares é fundamental para o manejo de cultivos. Este projeto implementa um fluxo automatizado para:
- **Aquisição de Dados:** Integração com a API do Roboflow para carregamento de dados.
- **Engenharia de Dados:** Rebalanceamento automatizado dos conjuntos de treino e teste (divisão 80/20) para garantir a generalização do modelo.
- **Treinamento de Modelos:** Análise comparativa de treinamento e validação entre **YOLO11l** e **RT-DETR-l**.
- **Inferência e Validação:** Processamento em tempo real de imagens e vídeos em alta resolução obtidos em hortas locais.

## 🛠️ Tecnologias Utilizadas

- **Framework:** [Ultralytics](https://github.com/ultralytics/ultralytics) (YOLO11 & RT-DETR)
- **Gerenciamento de Dataset:** API Roboflow
- **Linguagem:** Python 3.12+
- **Deep Learning:** PyTorch com aceleração CUDA (testado em NVIDIA RTX 4050)
- **Visão Computacional e Utilitários:** OpenCV, Matplotlib, PyYAML, Pillow

## 📂 Estrutura do Repositório


```text
├── 01_lettuce_disease_detection.ipynb   # Notebook principal do pipeline
├── requirements.txt                     # Dependências do Python
├── .gitignore                           # Regras de ignorar do Git
├── README.md                            # Documentação principal (Inglês)
└── README.pt-BR.md                      # Documentação em Português

```

## 📊 Detalhes do Dataset

O dataset (`disease-lettuce-h69zb`) contém imagens classificadas em diversas categorias, incluindo:
- Saudável (Healthy)
- Mancha de Septoria (Septoria Blight)
- Míldio (Downy Mildew)
- Infecção Bacteriana (Bacterial)
- Vírus do Mosaico da Alface (Lettuce Mosaic Virus)
- Antracnose (Lettuce Anthracnose)

As imagens são pré-processadas na resolução de **640x640** para treinamento e até **1280x1280** para inferência em vídeos de alta precisão.

## 🚀 Configuração de Treinamento e Desempenho

| Modelo | Tarefa | Resolução | Batch Size | Hardware |
| :--- | :--- | :--- | :--- | :--- |
| **YOLO11l** | Detecção | 640 | 8 | RTX 4050 |
| **RT-DETR-l** | Detecção | 640 | 8 | RTX 4050 |

### Principais Resultados
Os modelos são validados em conjuntos de teste e vídeos reais de hortas locais, demonstrando taxa elevada de quadros por segundo (FPS) durante a inferência e alto mAP (mean Average Precision) entre as classes.

## ⚙️ Instalação e Uso

### 1. Clonar o Repositório
```bash
git clone [https://github.com/Math77077/lettuce-healthy-recognizer.git](https://github.com/Math77077/lettuce-healthy-recognizer.git)
cd lettuce-healthy-recognizer
```

### 2. Instalar Dependências

```bash
pip install -r requirements.txt

```

### 3. Executar o Pipeline

Abra o `01_lettuce_disease_detection.ipynb` no Jupyter Lab ou VS Code e execute as células sequencialmente para baixar o dataset, rebalancear os splits, treinar os modelos e rodar as avaliações qualitativas.

### 4. Exemplo Rápido de Inferência em Vídeo

```python
from ultralytics import YOLO

# Carregar pesos treinados
model = YOLO('treinamento_lettuce_results/YOLO11/weights/best.pt')

# Executar predição no vídeo
results = model.predict(source='videos/exemplo.mp4', save=True, imgsz=1280, conf=0.25)

```

## 📊 Avaliação Qualitativa

O pipeline inclui scripts de inspeção visual que comparam as anotações reais (**Ground Truth**) com as **Predições do Modelo** lado a lado para analisar o comportamento do detector em diferentes condições de iluminação.

---

### 🤝 Contribuição e Manutenção

Mantido como parte de um grupo de pesquisa em Inteligência Artificial focado em tecnologia agrícola e agricultura de precisão.
