# Portafolio de Ciencia de Datos · Odra Mathison

Transformo datos en decisiones que generan valor real para las empresas y sus usuarios. Este repositorio reúne cinco proyectos sobre problemas típicos de banca y marketing.

> Todos los proyectos usan **datos públicos**. Ninguno contiene información de clientes ni de las empresas donde he trabajado.

## Proyectos

| # | Proyecto | Pregunta de negocio | Técnicas |
|---|---|---|---|
| 1 | [Propensión en campañas bancarias](01-propension-campanas-bancarias/) | ¿A quién llamar primero para vender más con menos llamadas? | Clasificación, curva de ganancia, costo-beneficio |
| 2 | [Riesgo de impago y límites de crédito](02-riesgo-credito-limites/) | ¿A quién aumentar el límite sin subir el riesgo? | Scoring, AUC/Gini/KS, bandas de riesgo |
| 3 | [Segmentación RFM](03-segmentacion-rfm/) | ¿Qué estrategia dar a cada grupo de clientes? | RFM, K-means |
| 4 | [Abandono de tarjetahabientes](04-abandono-tarjetahabientes/) | ¿Quién está por irse y por qué? | Clasificación, umbral óptimo, importancia de variables |
| 5 | [Dashboard de marketing digital](05-dashboard-marketing-digital/) | ¿Qué canal trae ventas y dónde se pierde el embudo? | SQL (BigQuery), Power BI, DAX |

## Cómo ejecutar los notebooks
```bash
git clone https://github.com/TU_USUARIO/portafolio-ciencia-datos.git
cd portafolio-ciencia-datos
python -m venv .venv
source .venv/bin/activate        # En Windows: .venv\Scripts\activate
pip install -r requirements.txt
cd 01-propension-campanas-bancarias
jupyter notebook analisis.ipynb
```
Cada notebook descarga sus datos en `data/raw/` (salvo el proyecto 4, que requiere descarga manual desde Kaggle). Los resultados se guardan en `outputs/`.

## Herramientas
Python · SQL · Pandas · scikit-learn · Matplotlib · Seaborn · BigQuery · Power BI · DAX

## Contacto
contacto@odramathison.com
