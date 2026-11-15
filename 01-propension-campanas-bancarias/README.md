# ¿A quién llamar primero? Propensión en campañas bancarias

**Pregunta de negocio:** en una campaña telefónica para vender depósitos a plazo, ¿cómo ordenar a los clientes para conseguir más ventas con menos llamadas?

## Datos
[Bank Marketing (UCI)](https://archive.ics.uci.edu/dataset/222/bank+marketing): 41.188 contactos de campañas de un banco portugués (2008–2010). Licencia CC BY 4.0. El notebook lo descarga automáticamente.

## Enfoque
1. Exploración de la tasa de conversión por mes, canal y resultado de campañas anteriores.
2. Eliminación de `duration` para evitar fuga de información (solo se conoce después de la llamada).
3. Comparación de regresión logística y gradient boosting (ROC AUC y PR AUC).
4. Curva de ganancia, *lift* por deciles y análisis costo-beneficio para decidir hasta dónde llamar.
5. Exportación de una lista priorizada de contactos.

## Resultados
- El mejor modelo (gradient boosting) obtuvo un ROC AUC de 0,815 y un PR AUC de 0,492, frente a una tasa base de conversión del 11,3 %.
- Contactando al 20 % de clientes con mayor probabilidad se captura el 66 % de las ventas; con el 30 %, el 74 %.
- Con los supuestos ilustrativos (costo por llamada 5, margen por venta 100), llamar al 34 % mejor puntuado deja un beneficio de 72.040, frente a 64.515 llamando a todos: un 12 % más con 6.765 llamadas menos.

## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · scikit-learn · Matplotlib · Seaborn
