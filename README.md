# Reto 7: Búsqueda Semántica
**Asignatura:** Inteligencia Artificial Moderna  
**Institución:** Universidad de Boyacá  
**Año:** 2026  

---

## 👥 Integrantes del Equipo
* JHONATAN STEVEN PÉREZ QUIROZ - Código Estudiante: [552...]
* JHON ZHEN'YABSE MARIN CUERVO - Código Estudiante: [55222002]

---

## 📌 Descripción del Proyecto
Este repositorio contiene el desarrollo del **Reto 7: Búsqueda Semántica de Noticias**, enfocado en resolver una problemática real de una sala de redacción periodística (Caso de uso: **BBC News Summary**)

El motor de búsqueda tradicional de la editorial web se limitaba a la coincidencia exacta de palabras clave (*Lexical Search*), imposibilitando la recuperación de artículos relacionados temáticamente (por ejemplo, omitía artículos de "recesión y desempleo" ante una consulta de "crisis económica"). 

Para solucionar esto, implementamos un **pipeline de Inteligencia Artificial** estructurado en las siguientes fases:
1. **Ingesta y Consolidación:** Extracción y ordenamiento de $\approx2,225$ artículos distribuidos en 5 categorías de noticias.
2. **Análisis Exploratorio de Datos (EDA):** Evaluación de balanceo de clases y distribución de longitud de palabras.
3. **Limpieza de Datos:** Eliminación de ruido, unificación mediante Expresiones Regulares (RegEx) y descarte de textos vacíos o irrelevantes.
4. **Preprocesamiento:** Segmentación estratificada de los datos en conjuntos de Entrenamiento (80%), Validación (10%) y Prueba (10%).
5. **Modelado Avanzado:** Implementación de un modelo basado en *Bi-Encoders* utilizando la arquitectura de Transformers pre-entrenada `sentence-transformers/all-MiniLM-L6-v2` de Hugging Face.
6. **Evaluación:** Medición de consistencia temática en el espacio latente vectorizado y documentación del análisis de errores.
7. **Demostración:** Interfaz interactiva de inferencia en vivo para consultas abstractas.

---

## 📂 Estructura del Repositorio
El proyecto mantiene un árbol de directorios organizado y modular:

```text
├── .venv/                         # Entorno virtual de Python con las dependencias aisladas
├── BBC News Summary/              # Dataset original descargado desde Kaggle
├── datos_preprocesados/          # Datasets finales exportados por la fase de 
│   ├── train.csv                  # Set de entrenamiento (80%)
│   ├── val.csv                    # Set de validación (10%)
│   └── test.csv                   # Set de prueba (10%)
├── modelo_sentence_transformer/   # Carpeta local con los pesos y la configuración del 
└── README.md                      # Documentación del proyecto (este archivo)
├── requirements.txt               # Archivo de dependencias del proyecto
├── Reto7_Ingesta_y_Preprocesamiento.ipynb  # Notebook principal con el pipeline completo ejecutado
