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
- El mejor modelo (gradient boosting) obtuvo AUC 0,78, Gini 0,56 y KS 0,42, frente a una tasa de impago del 22,1 %.
- Las bandas de riesgo ordenan bien a los clientes: la tasa de impago real va del 5,3 % en la banda A al 56,8 % en la banda E.
- La regla de aumento de límite (bandas A–B, utilización ≥ 60 % y sin atrasos) seleccionó 914 de 9.000 clientes de prueba, con una tasa de impago del 10,8 %: la mitad que la cartera completa.

## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · scikit-learn · Matplotlib · Seaborn
