## 🧠 Clasificador de Contenido Político

Este módulo permite entrenar y evaluar clasificadores que analizan el contenido de mensajes políticos en X/Twitter. Utiliza datos previamente recolectados, anotados y preprocesados para entrenar modelos que clasifican los mensajes según **tema** y **tono** del discurso.

---

## 🚀 Funcionalidades

```

### 📊 Análisis y Evaluación
📂 `analisis/`
- `AnalisisBásico.ipynb`: análisis descriptivo de la distribución de etiquetas, estructuras de los datos y patrones iniciales.
- `AnalisisProfundo.ipynb`: evaluación comparativa de modelos, rendimiento y métricas.

### 🧠 Clasificadores por Tema
📂 `clasificador/clasificador_tema/`
- `MejorParams.ipynb`: entrenamiento del modelo que obtuvo mejor rendimiento en la clasificación por tono con comparación entre configuraciones para hallar mejores hiperparámetros
- `Clasificador.ipynb`: visualizador del mejor modelo encontrado.

### 🧠 Clasificadores por Tono
📂 `clasificador/clasificador_tono/`
- Estructura similar a `clasificador_tema`, pero orientada a detectar el tono (positivo, negativo, neutro).
- Incluye variantes: `basico/`, `class_balanced/`, `classweights_crossentropy/`, `classweights_focalloss/`.

### 🧾 Clasificadores Finales
📂 `clasificador/clasificadores_finales/`
- `ClasificacionFinal.ipynb`: script final de clasificación sobre el dataset completo.
- `AdicionEtiquetados.ipynb`: añade etiquetas añadidas a mano a un Excel de entrada.
- `modelo_final_tema/`, `modelo_final_tono/`: almacenamiento de modelos entrenados y tokenizadores exportados.

### 📁 Datasets
📂 `clasificador/datasets_originales/`
- `politicos_final.xlsx`: dataset original con metadatos.
- `temas_dataset.xlsx`, `tonos_dataset.xlsx`: datasets anotados manualmente para entrenamiento y evaluación.

📂 `analisis/datasets/`
- `politicos_etiquetado_actualizado.xlsx`: conjunto actualizado con etiquetas y predicciones para análisis.

```

---

## 📁 Estructura del Proyecto

```
clasificador_analisis/
├── analisis/
│   ├── datasets/
│   ├── Mapas/
│   ├── AnalisisBásico.ipynb
│   └── AnalisisProfundo.ipynb
├── clasificador/
│   ├── clasificadores_finales/
│   ├── clasificador_tema/
│   ├── clasificador_tono/
│   └── datasets_originales/
├── .gitignore
└── README.md
```

---

## ⚙️ Requisitos

```text
- Python 3.10+
- pandas  
- numpy  
- scikit-learn  
- transformers  
- tensorflow o torch (dependiendo del modelo usado)  
- matplotlib / seaborn  
- openpyxl  
- tqdm  
- jupyter
```

> ⚠️ Algunos modelos utilizan Hugging Face Transformers, por lo que puede requerirse descargar modelos previamente mediante `from_pretrained`.

---

## 🖥️ Ejecución

1️⃣ Clonar el repositorio:

```bash
git clone https://github.com/jabado2701/clasificador_analisis.git
cd clasificador_analisis
```

2️⃣ Instalar dependencias:

```bash
pip install -r requirements.txt
```

3️⃣ Ejecutar notebooks en orden:

```text
1. Entrenamiento (tema o tono)
   → clasificador_tema/MejorParams.ipynb
   → clasificador_tono/MejorParams.ipynb

2. Evaluación de modelos
   → Clasificador.ipynb

3. Clasificación final de mensajes nuevos
   → clasificadores_finales/ClasificacionFinal.ipynb

4. Análisis de resultados
   → analisis/AnalisisProfundo.ipynb
```

---

## 📄 Notas adicionales

* Los archivos `.xlsx` han sido excluidos del repositorio por tamaño o privacidad, pero deben colocarse en sus carpetas correspondientes (`datasets_originales/`, `datasets/`).
* Los modelos exportados en `modelo_final_tema/` y `modelo_final_tono/` pueden regenerarse desde los notebooks si se dispone de los pesos y datos originales.
* Este proyecto se integra directamente con el recolector y puede alimentar resultados a la aplicación de visualización.

---
