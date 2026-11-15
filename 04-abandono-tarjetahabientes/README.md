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
_Completa tras ejecutar el notebook:_
- ROC AUC: … · Recall de abandonos: …%
- Variables más importantes: …
- Valor anual transaccionado por clientes en riesgo: …

## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · scikit-learn · Matplotlib · Seaborn
