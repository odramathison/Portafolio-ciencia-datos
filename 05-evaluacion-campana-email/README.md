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
- Los tres grupos eran comparables antes de la campaña (mismo tamaño, recencia, gasto previo y perfil), por lo que las diferencias se atribuyen al email.
- **Email hombre:** visitas +72 % (10,6 % → 18,3 %), conversión +119 % (0,57 % → 1,25 %) y gasto por cliente +118 %. Todas significativas (p < 0,001).
- **Email mujer:** visitas +43 %, conversión +54 % y gasto +65 %, también significativas, pero con menor efecto.
- Con los supuestos ilustrativos (0,10 $ por email, 30 % de margen), el email de hombre generó 16.403 $ en ventas incrementales y un ROI del 131 %; el de mujer, un ROI del 27 %.
- El email de hombre funcionó en todos los segmentos; el mayor aumento se dio en clientes multicanal (+1,0 puntos) y con gasto previo de 750–1.000 $ (+2,0 puntos).
- **Limitación:** el modelo de uplift no logró ordenar a los clientes de forma estable (el aumento real por decil no es decreciente). Con una conversión cercana al 1 %, hay pocas compras para estimar efectos individuales. Siguiente paso: probar con más datos o usar el modelo para predecir visitas, que son mucho más frecuentes.


## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · SciPy · scikit-learn · Matplotlib · Seaborn
