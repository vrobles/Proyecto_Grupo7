# Proyecto_Grupo7
Marketing Digital - Grupo 7

# Análisis de Comportamiento de Clientes con Tarjetas de Crédito por Antigüedad

## Introducción

### El Problema
Actualmente, en el sector financiero, es fundamental entender el comportamiento de los clientes para poder ofrecerles servicios personalizados y anticiparse a sus necesidades. Las tarjetas de crédito generan una gran cantidad de datos que pueden revelar patrones de comportamiento que permitan a las instituciones financieras optimizar sus estrategias de marketing y retención de clientes. Este análisis busca aprovechar dichos datos para identificar grupos de clientes con comportamientos similares, con el objetivo de aplicar estrategias específicas para cada grupo.

### La Solución
La solución técnica se basa en la segmentación de clientes mediante el uso de algoritmos de machine learning, específicamente el algoritmo de clustering KMeans. Este método permite agrupar a los clientes en clusters o segmentos según su comportamiento de uso de tarjetas de crédito. El objetivo es identificar segmentos diferenciados para proponer estrategias de marketing personalizadas. Existen soluciones similares en el mercado que aplican machine learning para analizar comportamientos financieros, como el uso de modelos de clustering para segmentación en análisis de riesgos, crédito y optimización de campañas de fidelización.

## Metodología

![image](https://github.com/user-attachments/assets/ba25f979-e078-40bf-a10b-670e35237a76)


### Análisis Exploratorio
Para llevar a cabo este análisis, utilizamos un dataset con características de uso de tarjetas de crédito. Las variables incluyen datos demográficos y de uso financiero, tales como la antigüedad de la cuenta, el número de transacciones, y el saldo promedio. Durante la exploración, observamos patrones iniciales que sugerían la presencia de distintos perfiles de uso. Estos hallazgos fueron determinantes para seleccionar las características más relevantes y dirigir el enfoque de segmentación.

![image](https://github.com/user-attachments/assets/1af0f57a-9766-415f-b955-3b905ca238f6)


![image](https://github.com/user-attachments/assets/39625132-1ade-4c23-8578-dcab4763be90)

Muchas de las variables, como BALANCE, PURCHASES, CASH_ADVANCE, CREDIT_LIMIT, PAYMENTS y MINIMUM_PAYMENTS, tienen distribuciones sesgadas a la derecha. Esto significa que la mayoría de los clientes tienen valores bajos en estas variables, pero hay algunos con valores muy altos. Ejemplos de lo que podemos inferir:

La mayoría de los clientes tienen un balance bajo.
Hay pocos clientes que hacen compras o avances en efectivo de montos muy elevados.
Pocos clientes tienen límites de crédito extremadamente altos.
Variables como BALANCE_FREQUENCY, PURCHASES_FREQUENCY, CASH_ADVANCE_FREQUENCY, PURCHASES_INSTALLMENTS_FREQUENCY y ONEOFF_PURCHASES_FREQUENCY parecen tener una tendencia a valores cercanos a 1. Esto sugiere que muchos clientes realizan transacciones con bastante frecuencia, probablemente en cada ciclo.

En particular, BALANCE_FREQUENCY y PURCHASES_FREQUENCY muestran una concentración fuerte en valores cercanos a 1, lo que podría implicar que la mayoría de los clientes revisan sus balances y realizan compras de manera regular.

La variable TENURE está altamente concentrada en los valores más altos, lo que podría significar que muchos clientes tienen una relación larga con la institución (aproximadamente 12 meses).

![image](https://github.com/user-attachments/assets/a34da250-e54b-470f-803c-7709ad17afb9)

Se propone las 4 nuevas características:

- Ratio de compras en efectivo a compras totales.
- Promedio de compras por transacción.
- Categoria de Saldo
- Categoria antiguedad

### Procesamiento de Datos
El procesamiento incluyó la limpieza de datos para eliminar outliers y valores nulos, así como la normalización de los datos numéricos para garantizar una escala uniforme, lo cual es esencial para el funcionamiento de KMeans. Esta preparación permitió mejorar la precisión del modelo y asegurar que cada variable contribuya de manera equitativa al clustering.

### Entrenamiento y Tuneo de Hiperparámetros
Entrenamos el modelo utilizando el algoritmo KMeans, experimentando con diferentes valores de `k` para determinar el número óptimo de clusters mediante el método del codo. Se realizaron ajustes de hiperparámetros para obtener una buena estabilidad y coherencia en la segmentación. La decisión final sobre `k` se sustentó en la capacidad de cada grupo de ofrecer un valor significativo en términos de comportamiento y de negocio.

### Interpretación de los Clusters
El modelo resultante identificó al menos cuatro clusters, cada uno con características de comportamiento financiero distintas. Mediante visualizaciones como gráficos de barras y dispersión, analizamos cómo cada variable (como el volumen de transacciones y la antigüedad de la cuenta) impacta a cada cluster. Esto proporciona una base para entender a cada grupo en términos de probabilidad de retención, necesidad de incentivos, o riesgo de abandono.

![Distribución de Clusters](path/to/cluster_distribution.png)
![Análisis de Variables por Cluster](path/to/variable_analysis_by_cluster.png)

## Implementación en el Negocio
La implementación del modelo permitiría a la empresa desarrollar estrategias de marketing personalizadas, tales como ofertas y recompensas dirigidas, según el cluster al que pertenezca cada cliente. Esto no solo aumentaría la retención de clientes, sino que también permitiría identificar oportunidades para cross-selling y up-selling. Empresas similares han aplicado clustering en sus departamentos de CRM para mejorar la personalización y la experiencia del cliente, logrando resultados positivos en retención y satisfacción.

## Limitaciones
Entre las limitaciones del proyecto se incluyen:
- **Limitaciones computacionales**: Para grandes volúmenes de datos, el modelo KMeans puede requerir un procesamiento significativo.
- **Falta de variables adicionales**: Variables adicionales, como historial de pagos o patrones de consumo específicos, podrían mejorar la discriminación de clusters y hacer que los resultados sean más precisos.

## Conclusiones y Recomendaciones
La segmentación de clientes en función de su comportamiento con tarjetas de crédito fue exitosa, proporcionando insights valiosos para la empresa. Recomendamos a futuros analistas considerar técnicas de feature engineering para enriquecer aún más los datos. Al negocio, le recomendamos mantener un registro exhaustivo y detallado de las transacciones de los clientes, pues esta información es vital para mejorar la segmentación y personalización de las ofertas.

## Future Work
Para mejorar este proyecto, proponemos los siguientes desarrollos futuros:
- Experimentar con algoritmos de clustering avanzados, como DBSCAN, para manejar mejor los outliers.
- Incluir nuevas variables que reflejen el comportamiento de pago de los clientes.
- Automatizar el proceso de actualización del modelo con nuevos datos de clientes en tiempo real para una adaptación continua.

