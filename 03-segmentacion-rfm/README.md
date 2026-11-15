# Segmentación de clientes con RFM y K-means

**Pregunta de negocio:** ¿cómo agrupar a los clientes para dar a cada grupo una estrategia comercial distinta?

## Datos
[Online Retail II (UCI)](https://archive.ics.uci.edu/dataset/502/online+retail+ii): más de un millón de líneas de factura de un comercio en línea del Reino Unido (2009–2011). Licencia CC BY 4.0. El notebook lo descarga automáticamente; la primera lectura del Excel tarda unos minutos.

## Enfoque
1. Limpieza: clientes sin ID, facturas canceladas, cantidades o precios no válidos y duplicados.
2. Cálculo de Recencia, Frecuencia y Monto por cliente.
3. Segmentos por reglas RFM (Campeones, Leales, En riesgo, Hibernando…).
4. K-means sobre RFM en escala logarítmica, con método del codo y silueta.
5. Tabla de estrategia comercial por segmento y exportación de clientes segmentados.

## Resultados
- Tras la limpieza se analizaron 779.425 líneas de factura de 5.878 clientes (dic. 2009 – dic. 2011).
- Los Campeones (25 % de los clientes) generan el 69 % de los ingresos; junto con los Leales, el 46 % de los clientes concentra el 84 %.
- 354 clientes valiosos están "En riesgo": compraban con frecuencia pero llevan casi un año sin volver. Suman el 6,3 % de los ingresos (≈ £1,09 M) y son la mejor oportunidad de recuperación.
- K-means confirma la estructura: el grupo "Alto valor" (20 % de los clientes) aporta el 70 % de los ingresos.
- El 26 % de los clientes está "Hibernando" y solo aporta el 3,8 %: conviene reactivarlos con acciones de bajo costo.


## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · scikit-learn (K-means) · Matplotlib · Seaborn
