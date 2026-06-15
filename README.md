# SIHAC: Sistema Inteligente de Homologación y Análisis Competitivo de Inventario Hotelero

> **Sync.AI** — *"Conectando tu oferta con el mercado global a través de precisión artificial."*

![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)
![Framework](https://img.shields.io/badge/pipeline-CRISP--DM-emerald)
![Academic](https://img.shields.io/badge/UNIR-Maestría%20en%20IA-red)

Este repositorio contiene el núcleo algorítmico y la arquitectura de datos para el proyecto **SIHAC** (*Sistema Inteligente de Homologación y Análisis Competitivo de Inventario Hotelero*), desarrollado por **Sync.AI** como propuesta técnica de licitación comercial para **Best Day Travel Group**.

El sistema mitiga el fallo sistémico de las herramientas de extracción tradicionales (RPA de coincidencia exacta) en el sector turístico mediante el uso de Procesamiento de Lenguaje Natural (PLN) y clustering multidimensional heterogéneo.

---

## 🎓 Descargo de Responsabilidad Académica (Disclaimer)

**Aviso de Confidencialidad y Fines Académicos:** El presente repositorio y el código asociado constituyen un proyecto de carácter estrictamente ficticio, desarrollado de forma exclusiva con fines educativos, de investigación y evaluación dentro de la asignatura **MODAM: Investigación en Inteligencia Artificial** de la *Maestría en Inteligencia Artificial* en la **Universidad Internacional de La Rioja (UNIR)**. Los nombres de las corporaciones, marcas comerciales, datos financieros simulados y escenarios de negocio aquí citados son empleados con el único propósito de ilustrar el ejercicio práctico de la materia.

---

## 🛠️ Arquitectura del Pipeline Tecnológico (CRISP-DM)

El procesamiento de datos de inventario competitivo e ingeniería de características se ejecuta a través de cinco etapas secuenciales e integradas de forma nativa:

1. **Recolección (Data Collection):** Ingesta paralela y distribuida desde HTML/APIs de competidores (Expedia, Despegar, Booking, Price Travel). Almacenamiento directo en crudo dentro del Data Lake corporativo en formato JSON.
2. **Preparación (Data Preparation):** Limpieza estructural profunda, tipado de variables, normalización matemática de precios y parseo de strings lingüísticos junto con metadatos geoespaciales (Latitud/Longitud).
3. **Procesamiento de Lenguaje Natural (PLN):** Extracción de embeddings vectoriales continuos y semánticos utilizando arquitecturas basadas en Transformers (*Sentence-BERT / SBERT*) y modelos supervisados de lenguaje turístico para capturar el contexto real de los descriptores de marcas ("Spa", "Resort", "All Inclusive").
4. **Modelado de Distancia Multidimensional:** Aplicación síncrona de algoritmos de clustering y vecindad ($K$-Means y $K$-NN) parametrizados bajo pesos ponderados heterogéneos (semántica de texto, distancia euclidiana física, brecha de precio y calificación de la OTA). Un umbral matemático de distancia espacial $< 0.15$ valida la equivalencia analítica (`Match = TRUE`).
5. **Evaluación y Despliegue:** Ingestión automatizada de los registros homologados y limpios hacia la base de datos productiva para detonar alertas inteligentes de disparidad tarifaria directamente en la interfaz del Dashboard de Revenue Management.

---

## 📈 Objetivos del Sistema y Métricas de Éxito

* **OE1 (Automatización):** Recolección diaria del 100% de la oferta hotelera disponible en destinos clave (Cancún y Riviera Maya).
* **OE2 (Homologación):** Alcanzar una tasa de emparejamiento automático superior al 95% del inventario recolectado mediante métricas de *Precision*, *Recall* y auditoría controlada de falsos positivos.
* **OE3 (Inteligencia Competitiva):** Descubrimiento e identificación mensual de al menos un 10% de nuevos hoteles de alta rentabilidad ofertados por la competencia con los que Best Day aún no cuenta con convenio de contratación.

---

---

## 📁 Estructura General del Repositorio

```text
├── data/                  # Datasets simulados y muestra controlada (50k registros)
├── src/                   # Código fuente del Pipeline
│   ├── extraction/        # Scripts de ingesta y Web Scrapers de OTAs
│   ├── preprocessing/     # Limpieza y estructuración geoespacial/matemática
│   ├── nlp_models/        # Configuración de embeddings vectoriales (SBERT)
│   └── clustering/        # Algoritmos K-Means/K-NN y cálculo de umbrales
├── notebooks/             # Jupyter Notebooks de experimentación y validación cruzada
├── docs/                  # Documentación técnica, manual de usuario y propuesta comercial
├── main.tex               # Código fuente oficial de la propuesta comercial para Overleaf
├── requirements.txt       # Dependencias y librerías del entorno virtual
└── README.md              # Presentación del proyecto
