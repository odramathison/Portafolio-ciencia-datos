# Predicción de abandono de tarjetahabientes

**Pregunta de negocio:** ¿qué clientes están por cancelar su tarjeta, por qué, y cuánto valor está en juego?

## Datos
[Credit Card Customers (Kaggle)](https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers): ~10.000 clientes con perfil, uso y estado (activo o perdido). Licencia CC0.

Kaggle pide iniciar sesión: descarga el dataset y coloca `BankChurners.csv` en `data/raw/`. Con la API de Kaggle:
```bash
kaggle datasets download -d sakshigoyal7/credit-card-customers -p data/raw --unzip
```

## Enfoque
1. Exploración del abandono por nivel de transacciones, saldo rotativo, productos e inactividad.
2. Regresión logística y gradient boosting (ROC AUC, PR AUC).
3. Umbral elegido por F1 y matriz de confusión.
4. Importancia por permutación para explicar qué anticipa el abandono.
5. Lista de clientes en riesgo ordenada por monto transaccionado (valor en riesgo).

## Resultados
## Resultados
- El mejor modelo (gradient boosting) obtuvo ROC AUC 0,994 y PR AUC 0,969, frente a una tasa de abandono del 16 %.
- Con el umbral óptimo (0,21) detecta el 92 % de los clientes que abandonan, con un 91 % de precisión.
- Las señales más fuertes son el número y el monto de transacciones, seguidas por el cambio de gasto entre trimestres y la cantidad de productos con el banco. Los datos demográficos pesan muy poco.
- 411 de 2.532 clientes de prueba quedan marcados en riesgo; juntos transaccionan $1,28 M al año, el valor que una campaña de retención podría proteger.

## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · scikit-learn · Matplotlib · Seaborn
