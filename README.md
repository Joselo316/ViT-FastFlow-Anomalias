# ViT + FastFlow para Detección de Anomalías en Placas MDP

Este proyecto implementa un sistema de **detección de anomalías** en tableros **MDP** utilizando **Vision Transformer (ViT)** combinado con **FastFlow**.  
Además de detectar defectos, el modelo también **clasifica el tipo de tablero** y genera **heatmaps** para visualizar las áreas más relevantes.

---

## Características

- **Entrenamiento solo con imágenes buenas** → el modelo aprende qué es "normal".
- **Clasificación automática** del tipo de tablero (extraído del nombre del archivo).
- **Detección de defectos** usando FastFlow y puntuación de anomalía.
- **Visualización con heatmaps** para identificar regiones críticas.
- **Evaluación cuantitativa** (accuracy, F1, matrices de confusión).
- **Checkpoint automático** → evita reentrenar si el modelo ya existe.

---

## Estructura del Dataset

```
Dataset_fastflow/
├── train/          # Imágenes buenas (entrenamiento)
├── val/            # Imágenes buenas (validación)
└── test/           # Imágenes buenas y defectuosas

defectos/           # Imágenes defectuosas adicionales (opcional)
```

**Nomenclatura de archivos**  
- `20241012_125852_0.jpg` → Clase 0  
- `aug_00014_2.jpg` → Clase 2  

El último número en el nombre define la **clase**.

---

## Requisitos

Instalar dependencias principales:

```bash
pip install torch torchvision transformers scikit-learn matplotlib seaborn pillow opencv-python tqdm
```

---

## Uso

1. Clona este repositorio:

```bash
git clone https://github.com/USERNAME/ViT-FastFlow-Anomalias.git
cd ViT-FastFlow-Anomalias
```

2. Abre el notebook:

```bash
jupyter notebook ViT_FastFlow_Completo.ipynb
```

3. Edita la variable `image_path` en la sección de **Inferencia** para analizar una imagen específica y generar su **heatmap**.

---

## Ejemplo de Resultados

- **Clasificación de tablero**: predicción de la clase (0, 1, 2, …).  
- **Defecto**: indica si la placa es defectuosa o no.  
- **Heatmap**: visualización superpuesta en la imagen original.

![example](https://user-images.githubusercontent.com/0000000/example-heatmap.png)

---


