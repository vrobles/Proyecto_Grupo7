# Proyecto_Grupo7
Marketing Digital - Grupo 7

Introducción

El problema: aquí se plantea el problema y se lo contextualiza. Para esto pueden basarse en información que encuentren en internet. Pueden tratar de encontrar oportunidades de negocio en base a los datos que tienen disponibles, tal como pasa en su diario vivir.


La solución: aquí se plantea la solución, que aunque es altamente técnica, en este punto de la presentación no se debe profundizar aún en ese tipo de detalles. Mencionen la solución técnica (segmentación de clientes) y cuál es su objetivo. Aquí también pueden mencionar soluciones existentes similares (machine learning-like) que hayan sido usadas en problemas similares.


Metodología

![image](https://github.com/user-attachments/assets/ba25f979-e078-40bf-a10b-670e35237a76)

Análisis exploratorio. Utilicen este espacio para explicar a su audiencia el dataset con el que cuentan y los descubrimientos relevantes que realizaron sobre él durante la exploración. Dar preferencias a la descripción de columnas/descubrimientos que luego serán relevantes como sustentación de decisiones técnicas (limpieza de datos, feature engineering, etc).

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

Ratio de compras en efectivo a compras totales.
Promedio de compras por transacción.
Categoria de Saldo
Categoria antiguedad


Procesamiento de datos. Expliquen aquí todo el procesamiento que le realizaron a sus datos y justifíquenlo.
Entrenamiento y tuneo de hiperparámetros. Expliquen aquí la metodología que siguieron para el entrenamiento y tuneo. Expliquen y sustenten sus decisiones.
Interpretación de los clusters: Expliquen la relación de las variables del modelo con los clusters (al menos 4) en el sentido del negocio, utilicen visualizaciones para poder ver el comportamiento de las variables en cada uno de los clusters.
Implementación en el negocio
Expliquen cómo implementarían el modelo en el negocio y justifíquenlo. La justificación puede ser basada en cómo otras empresas implementan soluciones similares o puede ser basada en su humilde entendimiento del negocio.
