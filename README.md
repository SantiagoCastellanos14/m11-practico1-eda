# Análisis Exploratorio de Datos - Ventas

## Objetivo
Este proyecto realiza un análisis exploratorio de datos (EDA) sobre un dataset de ventas para comprender patrones, tendencias y comportamientos relevantes que puedan orientar futuros análisis y modelos predictivos.

## Requisitos
Para ejecutar el notebook es necesario tener instalado:
- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- plotly

Instalación de dependencias:
```bash
pip install pandas numpy matplotlib seaborn plotly
```

## Estructura del Proyecto
```
practico_1_eda/
│
├── data/
│   └── ventas.csv
├── practico_1_eda.ipynb
├── img/
└── README.md
```

## Principales Hallazgos

**Estructura y Volumen del Dataset**
*   **Dimensiones**: 310,217 transacciones registradas con 52 variables numéricas (35) y categóricas (17).
*   **Período temporal**: 3-ene-2022 al 29-jun-2024 
*   **Sucursales**: 3 sucursales operativas (códigos 1, 9, 12)
*   **Catálogo**: 3,808 productos únicos distribuidos heterogéneamente entre sucursales

    
**Calidad de los Datos**
*   **Completitud alta**: Solo 3 columnas superan 10% de nulos (`depo`, `orden_compra_nume`, `origen_pedido`)
*   **Escalas normalizadas**: Variables monetarias y de cantidad fueron deflactadas y normalizadas (división por 1M)
*   **Cobertura temporal consistente**:  Campos fecha, entre\_fecha, fecha\_regis, fecha\_alta muestran rangos de 908-911 días sin huecos evidentes; la serie es apta para modelos de demanda.    
*   **Tratamiento de outliers**: Se aplicó filtrado por percentiles (P1-P99) en variables numéricas clave (`total`, `iva1`, `canti_venta`, `precio_uni`) para remover valores extremos que podrían sesgar el análisis. Esta estrategia conserva el 98% de las observaciones mientras elimina anomalías potenciales. La política es revisable según los objetivos específicos de modelado futuro.
*   **Variables redundantes** Campos \_ori, \_precio, linea\_nume\_auxi, secuen tienen correlación 1 : 1 con sus equivalentes y pueden eliminarse, reduciendo el tamaño del dataset ~35 %.


**Patrones de Negocio Identificados**
*   **Concentración de productos**: Solo 131 productos (3.44% del catálogo) representan el 80% del volumen de ventas.
*   **Diferencias por sucursal**: 
    - Sucursal 1 domina en facturación
    - Distribución desigual de productos entre puntos de venta
*   **Tendencia temporal**: Crecimiento sostenido con aceleración marcada desde 2024
*   **Patrones estacionales**: Potencial ciclo mensual/quincenal, ausencia de estacionalidad anual marcada.
*   **Método de pago dominante**: `condi_venta='00'` (contado) en ~78% de transacciones (posible asimilación de frecuenci).


**Estructura del negocio**       
*   **Facturación total:** $452,332,265
*   **Ticket promedio:** $11,054
*   **Ticket mediano:** $4,807
*   **Clientes únicos:** 566 clientes
*   **Promedio de transacciones por dí:** 42.5 transacciones/día
*   **Ventas Mayoristas (A):** 86.91%
*   **Ventas Minoristas (B):** 13.09%

*   **Método de pago dominante** condi\_venta='00' (contado) representa 78 % de transacciones; ventas financiadas (07, mp, 14) muestran tickets 18 % mayores, oportunidad para impulsar cuotas.
    
*   **Concentración de productos por sucursal:** 

                Sucursal 9:
                • Productos que explican 80 % de unidades: 105
                • Porcentaje de SU catálogo: 6.78%

                Sucursal 1:
                • Productos que explican 80 % de unidades: 134
                • Porcentaje de SU catálogo: 4.00%

                Sucursal 12:
                • Productos que explican 80 % de unidades: 127
                • Porcentaje de SU catálogo: 10.13%
    


## Ejecución
1. Clonar el repositorio
2. Instalar dependencias
3. Abrir y ejecutar el notebook `practico_1_eda.ipynb`

## Control de Versiones
Para guardar los cambios en GitHub:

1. Inicializar el repositorio (primera vez):
```bash
git init
git add .
git commit -m "Commit inicial"
```

2. Conectar con GitHub (primera vez):
```bash
git remote add origin <URL_DEL_REPOSITORIO>
git branch -M main
git push -u origin main
```

3. Para actualizaciones posteriores:
```bash
git add .
git commit -m "Descripción de los cambios"
git push
```
