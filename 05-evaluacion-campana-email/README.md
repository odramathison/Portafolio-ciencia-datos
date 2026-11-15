# ¿Funcionó la campaña? Evaluación de una campaña de email marketing

**Pregunta de negocio:** una tienda envió dos campañas de email (productos de hombre y de mujer) y dejó un grupo sin email como control. ¿Las campañas aumentaron de verdad las visitas, las compras y las ventas? ¿Fueron rentables? ¿A quién conviene enviar el email la próxima vez?

## Datos
Kevin Hillstrom: MineThatData E-Mail Analytics Challenge (2008). 64.000 clientes asignados al azar a tres grupos (email hombre, email mujer y sin email), con su comportamiento durante las dos semanas siguientes. El notebook descarga los datos automáticamente.

## Enfoque
1. Verificación de que los grupos son comparables antes de la campaña.
2. Tasa de visita, conversión y gasto por grupo.
3. Pruebas estadísticas contra el grupo de control: prueba z de proporciones, t de Welch e intervalos bootstrap.
4. Ventas incrementales, ganancia neta y ROI con supuestos de costo y margen ajustables.
5. Efecto de la campaña por segmento (zona, canal, cliente nuevo, nivel de gasto).
6. Modelo de uplift de dos modelos (T-learner) para elegir a qué clientes enviar el email, validado con la curva de ganancia incremental.

## Resultados
_Completa tras ejecutar el notebook, por ejemplo:_
- La campaña … aumentó la conversión en … puntos (+…%), con diferencia significativa.
- Ventas incrementales: … · ROI con los supuestos usados: …%
- Enviando el email solo al …% de clientes con mayor uplift se obtiene el …% de las compras incrementales.

## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · SciPy · scikit-learn · Matplotlib · Seaborn
