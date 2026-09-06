# 🌐 Análisis de Ofertas de Empleo de LinkedIn (EE. UU.)

Proyecto de análisis exploratorio de datos sobre el mercado laboral estadounidense, a partir de más de 123.000 ofertas de empleo publicadas en LinkedIn. El objetivo es entender **dónde están las oportunidades, para quién, y qué habilidades demanda el mercado**, con especial atención a los perfiles junior y a los roles relacionados con datos.

> Proyecto académico realizado en el marco de la asignatura *Fundamentos para el Análisis de Datos y la Inteligencia Artificial* — CUNEF Universidad.


## 🎯 Preguntas que responde el análisis

- ¿En qué regiones de Estados Unidos se concentran las ofertas de empleo?
- ¿Qué industrias tienen más presencia y más visibilidad en LinkedIn?
- ¿Dónde están las oportunidades para perfiles junior (Internship / Entry Level) y qué habilidades piden?
- ¿Dónde están específicamente las ofertas relacionadas con datos, y qué exigen?
- ¿Qué relación hay entre el número de ofertas y el interés (vistas) que generan, por nivel de experiencia y tipo de contrato?
- ¿Qué beneficios laborales son más comunes y cómo varían según el puesto?

## 📊 Fuentes de datos

- **[LinkedIn Job Postings (Kaggle)](https://www.kaggle.com/datasets/arshkon/linkedin-job-postings)** — ofertas de empleo, empresas, industrias y habilidades requeridas (8 tablas relacionales).
- **[US Zip Codes with Lat and Long (Kaggle)](https://www.kaggle.com/datasets/joeleichter/us-zip-codes-with-lat-and-long)** — coordenadas geográficas por código postal, usadas para el análisis regional.

Las tablas utilizadas son: `postings`, `company_industries`, `industries`, `job_industries`, `job_skills`, `skills`, `benefits` y `zip_lat_long`.

## 🛠️ Pipeline del proyecto

1. **Carga y unión de datos** — integración de 8 tablas mediante claves (`job_id`, `company_id`, `industry_id`, `skill_abr`), unificando formatos de tipo entre columnas.
2. **Limpieza de datos** — tratamiento de valores nulos según el tipo de variable (mediana para `views`, imputación manteniendo la distribución en variables categóricas como `formatted_experience_level`).
3. **Tratamiento de outliers** — detección y filtrado de valores atípicos en `views` mediante boxplot y análisis de cuartiles.
4. **Ingeniería de variables** — creación de una clasificación propia de regiones de EE. UU. a partir del primer dígito del código postal, y extracción de ciudad/estado desde la columna de localización.
5. **Análisis exploratorio y visualización** — mapas geográficos interactivos (Plotly), gráficos de barras comparativos y un heatmap de beneficios por puesto, para responder a las preguntas de negocio del proyecto.

## 🔑 Principales hallazgos

- Las ofertas se concentran claramente en las **regiones costeras** de EE. UU. (Atlántico medio y costa del Pacífico); la zona montañosa del oeste y el centro-norte son las menos activas.
- *Staffing and Recruiting*, *Hospitals and Health Care* e *IT Services* son las industrias con más empresas y más visualizaciones en LinkedIn.
- Para perfiles con poca experiencia (Internship / Entry Level), las oportunidades se concentran en sanidad, retail, RR. HH., IT y servicios financieros — con Texas destacando por delante de regiones con más volumen total de ofertas.
- Las ofertas relacionadas con datos se concentran mayoritariamente en **California, Nueva York y Texas**, y demandan sobre todo habilidades de IT, administración, auditoría y análisis.
- Existe una desconexión entre oferta y demanda: algunos puestos con muchas vacantes generan poco interés (vistas), y viceversa.
- El beneficio más común en las ofertas de EE. UU. es el plan de pensiones **401(k)**, seguido del seguro médico.


## 💻 Tecnologías

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Plotly`

