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
_Completa tras ejecutar el notebook:_
- El …% de los clientes (Campeones + Leales) genera el …% de los ingresos.
- … clientes valiosos están "En riesgo": oportunidad de recuperación.

## Cómo ejecutarlo
```bash
pip install -r requirements.txt
jupyter notebook analisis.ipynb
```

## Herramientas
Python · Pandas · scikit-learn (K-means) · Matplotlib · Seaborn
