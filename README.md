# Test-A-B-marketing
__Proyecto de priorización de hipótesis y desarrollo de test A/B__

<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/banner.png" alt="Collage de gráficos">

_Fragmentos del notebook, para ver proyecto completo hacer click [aquí](https://portfoliodabastianlopez.on.drv.tw/Portafolio/P9.html)_

## Descripción del Proyecto
Junto con el departamento de marketing de la compañía en cuestión, se ha creado una lista de hipótesis que pueden ayudar a aumentar los ingresos. 
Se deben priorizar estas hipótesis, lanzar un test A/B y analizar los resultados.
  
## Herramientas Utilizadas
- __Lenguaje de Programación:__ Python.
- __Entorno de Desarrollo:__ Jupyter Notebook.
- __Bibliotecas:__ Pandas, Matplotlib, Scipy, Numpy, Math, Seaborn, Datetime.

## Proceso del Proyecto
Debido a las caracterísiticas del proyecto, su desarrollo se dividió en dos partes.

__Parte 1. Priorizar hipótesis__

El archivo `hypotheses_us.csv` contiene nueve hipótesis sobre cómo aumentar los ingresos de una tienda en línea con Reach, Impact, Confidence y Effort especificados para cada una.

Acciones a seguir:

- Aplicar el framework ICE para priorizar hipótesis. Ordenarlas en orden descendente de prioridad.
- Aplicar el framework RICE para priorizar hipótesis. Ordenarlas en orden descendente de prioridad.
- Mostrar cómo cambia la priorización de hipótesis cuando utilizas RICE en lugar de ICE. Proporcionar una explicación de los cambios.

__Parte 2. Análisis de test A/B__

Se realizó un test A/B y los resultados están en los archivos `orders_us.csv` y `visitors_us.csv`.

Analizar el test A/B:

- Representar gráficamente el ingreso acumulado por grupo. Hacer conclusiones y conjeturas.
- Representar gráficamente el tamaño de pedido promedio acumulado por grupo. Hacer conclusiones y conjeturas.
- Representar gráficamente la diferencia relativa en el tamaño de pedido promedio acumulado para el grupo B en comparación con el grupo A. Hacer conclusiones y conjeturas.
- Calcular la tasa de conversión de cada grupo como la relación entre los pedidos y el número de visitas de cada día. Representar gráficamente las tasas de conversión diarias de los dos grupos y describir la diferencia. Sacar conclusiones y hacer conjeturas.
- Trazar un gráfico de dispersión del número de pedidos por usuario. Hacer conclusiones y conjeturas.
- Calcular los percentiles 95 y 99 para el número de pedidos por usuario. Definir el punto en el cual un punto de datos se convierte en una anomalía.
- Trazar un gráfico de dispersión de los precios de los pedidos. Hacer conclusiones y conjeturas.
- Calcular los percentiles 95 y 99 de los precios de los pedidos. Definir el punto en el cual un punto de datos se convierte en una anomalía.
- Encontrar la significancia estadística de la diferencia en la conversión entre los grupos utilizando los datos en bruto. Hacer conclusiones y conjeturas.
- Encontrar la significancia estadística de la diferencia en el tamaño promedio de pedido entre los grupos utilizando los datos en bruto. Hacer conclusiones y conjeturas.
- Encontrar la significancia estadística de la diferencia en la conversión entre los grupos utilizando los datos filtrados. Hacer conclusiones y conjeturas.
- Encontrar la significancia estadística de la diferencia en el tamaño promedio de pedido entre los grupos utilizando los datos filtrados. Hacer conclusiones y conjeturas.
- Tomar una decisión basada en los resultados de la prueba. Las decisiones posibles son: 
    - 1. Parar la prueba, considerar a uno de los grupos como líder. 
    - 2. Parar la prueba, concluir que no hay diferencia entre los grupos. 
    - 3. Continuar la prueba.

## Descubrimientos importantes
### Parte 1: Priorizar hipótesis
Framework `ICE`: Su fórmula es $\frac{Impacto * Confianza}{Esfuerzo}$.

<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_31_0.png" alt="Collage de gráficos">

- Hipótesis 8: __Lanzar una promoción que da descuentos a los usuarios en sus cumpleaños.__
- Hipótesis 0: __Añadir dos nuevos canales para atraer tráfico, esto traerá un 30% más de usuarios.__
- Hipótesis 7: __Añadir formularios de suscripción en todas las páginas principales, esto ayudará a crear una lista de mails de clientes.__

<br>

Framework `RICE`: Su fórmula es $\frac{Alcance * Impacto * Confianza}{Esfuerzo}$.

<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_37_0.png" alt="Collage de gráficos">

- Hipótesis 7: __Añadir formularios de suscripción en todas las páginas principales, esto ayudará a crear una lista de mails de clientes.__
- Hipótesis 2: __Añadir bloques de recomendación en la web de la tienda, esto aumentará las conversiones y el tamaño de compra.__
- Hipótesis 0: __Añadir dos nuevos canales para atraer tráfico, esto traerá un 30% más de usuarios.__

La diferencia de resultados entre los framework __se debe al parámetro `Reach` que refiere al alcance que dicha acción tendría entre los usuarios, a diferencia de `ICE`, `RICE` considera esto dentro de la ecuación__. Es por eso que las hipótesis más importantes de este framework son optimizaciones globales a la web, alcanzando a todos los usuarios que interactúen con ella, en cambio las prioridades de `ICE` son potencialmente muy efectivas, como el descuento por cumpleaños y crear nuevos canales de tráfico, pero en alcance quedan por detrás de las anteriores.

Considerando lo anterior es que escogeremos la __Hipótesis 7__ para ser puesta a prueba en el test A/B.

### Parte 2: Análisis de test A/B
En general, el grupo B se muestra superior al A en todos los sentidos:

- Ingresos.

<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_54_0.png" alt="Collage de gráficos">

Se observa que, al finalizar el experimento, los ingresos acumulados del grupo B son ampliamente superiores a los del grupo A.

<br>

- Tamaño de los pedidos.

<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_64_0.png" alt="Collage de gráficos">

Se observa que el grupo B es superior por aproximadamente un 25%.

<br>

- Tasa de conversión.

<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_74_0.png" alt="Collage de gráficos">

Se observa que el grupo B convierte, por lo bajo, un 10% más que el grupo A.

#### Filtrado de outliers

Si nos fijamos en los gráficos mostrados, podemos apreciar variaciones súbitas en los valores relativos, esto es indica la presencia de valores atípicos que pueden afectar severamente el resultado del experimento, por ende estos serán filtrados usando gráficos de dispersión y percentiles extremos (95 y 99). Aquí están los gráficos resultantes:

<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_80_0.png" alt="Collage de gráficos">
<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_85_0.png" alt="Collage de gráficos">
<image src="https://github.com/BastianLQ/Test-A-B-marketing/blob/main/Images/output_85_1.png" alt="Collage de gráficos">

Los resultados de los percentiles extremos son los siguientes:
- __Pedidos por usuario:__ el percentil 95 es 2 y el 99 es 4.
- __Precios de los pedidos:__ el percentil 95 es $435.54 y el 99 es $900.904.

Los valores atípicos serán filtrados de la siguiente manera:
- __Serán filtrados los usuarios que realicen más de tres pedidos y/o que realice al menos un pedido por sobre 600 dólares.__

El total de usuarios filtrados son 40 y representan un 3.88% del total.

#### Pruebas estadísticas
Se realizan cuatro pruebas estadísticas usando el método no paramétrico de Mann-Whitney (debido a que los datos no cumplen con los supuestos para realizar una prueba t). Los resultados son los siguientes:

__Datos sin filtrar__
- Se rechaza la hipótesis nula en favor de la tasa de conversión del grupo B siendo, en promedio, un 13.81% superior a la del grupo A.
- En el caso del tamaño de los pedidos, no se rechaza la hipótesis nula, sin embargo, los pedidos del grupo B son un 25.17% mas grandes que los del grupo A.

__Datos filtrados__
- Se vuelve a rechazar la hipótesis nula en favor de la tasa de conversión del grupo B, esta vez con una diferencia relativa de un 14.3%.
- En el caso del tamaño de los pedidos, la hipótesis nula sigue sin rechazarse, y, esta vez la ventaja del grupo B es de un 5.44%.

#### Decisión final

__Se decide declarar al grupo B como vencedor e implementar el cambio sugerido, en este caso, implementar formularios de suscripción para captar correos electrónicos, ya que, este cambio traería un beneficio de un 14% aproximadamente en la tasa de conversión, además, el tamaño de los pedidos podría verse levemente aumentado también.__

## Ejecuta el proyecto [aquí](https://portfoliodabastianlopez.on.drv.tw/Portafolio/P9.html)
Para ver el diccionario de datos, el desarrollo completo en código, todos los gráficos y las conclusiones, haga click en el enlace de arriba.
