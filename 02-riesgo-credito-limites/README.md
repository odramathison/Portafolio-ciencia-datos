# Riesgo de impago y asignación de límites de crédito

**Pregunta de negocio:** ¿qué tarjetahabientes probablemente no pagarán el próximo mes, y a cuáles se les puede aumentar el límite con bajo riesgo?

## Datos
[Default of Credit Card Clients (UCI)](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients): 30.000 clientes de un banco de Taiwán (2005). Licencia CC BY 4.0. El notebook lo descarga automáticamente.

## Enfoque
1. Exploración del impago según historial de pagos y límite.
2. Ingeniería de variables de riesgo: utilización, meses con atraso, atraso máximo y ratio de pago.
3. Modelos de regresión logística y gradient boosting evaluados con AUC, Gini y KS, más calibración.
4. Cinco bandas de riesgo (A a E) con su tasa de impago real.
5. Regla de aumento de límite: bandas A–B, utilización ≥ 60 % y sin atrasos.

## Resultados
_Completa tras ejecutar el notebook:_
- AUC / Gini / KS del mejor modelo: …
- Tasa de impago: banda A …% vs. banda E …%
- Candidatos a aumento: … clientes con tasa de impago de …% (vs. …% de la cartera)

## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · scikit-learn · Matplotlib · Seaborn
