## Decisiones del PRACTICO 1 - Análisis y Visualización de Datos
- **ESCALADO DE DATOS**: cambiamos las magnitudes de variables cuyas variables creemos que presentan una multiplicacion por  '1 000 000' -> *(2.1)*
- **ELIMINACION DE VARIABLES REDUNDANTES**: eliminamos 'pedi_sucur', 'boni_impor_ori' y 'iva_percep_impor_ori' -> *para ahorrar espacio pues eran identicas a otras columnas / (2.2)* 
/ **TRATAMIENTO DE OUTLIERS**: eliminamos outliers previos al percentil 1 y posterior al percentil 99 -> para evitar ruido pero conservar datos (2.5)
## Decisiones del PRACTICO 2 - Análisis Exploratorio y Curación de Datos
- **GRANULARIDAD TEMPORAL**: 
para las series temporales involucradas en la estimacion del volumen de venta para PDV elegimos **MENSUAL** -> *(1)*
- **DEPURADO DE LOS DATOS**:
    1.   Vamos a predecir los volumenes de venta de los productos que tengan el **70% de meses completos** -> *Para intentar garantizar una mejor estimación*
    2.   Reduciremos el lapso temporal para aquellos clientes que comenzaron a comprar después -> *Para evitar muchos datos faltantes en las series*
    3.  No tendremos en cuenta a aquellos clientes que hace más de 9 meses no compren -> *Pues no sería confiable para los fines de la estimacion*
    4.   **Imputaremos todas los datos faltantes** representando "que no compraron" -> *Para completar series faltantes sin agregar ruido (usar otras tecnicas de imputacion implicaria agregar compras inexistentes que estropearian las estimaciones)*
- **NORMALIZACION/ESCALADO**:
