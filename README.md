# CryptoEda
Este proyecto realiza un análisis exploratorio de datos para investigar la correlación entre criptomonedas, sentimiento del mercado y sus efectos en los precios.

# Análisis Exploratorio de la Correlación entre Criptomonedas, Sentimiento del Mercado y sus Efectos en los Precios
Este repositorio contiene un Análisis Exploratorio de Datos (EDA) enfocado en investigar las conexiones entre las principales criptomonedas y el índice de "Fear and Greed". El análisis utiliza datos extraídos de la API de CoinGecko y se centra en los valores de apertura diarios desde enero de 2018 hasta diciembre de 2022. Se excluyen los tokens de Ethereum y stablecoins, y se seleccionan las diez criptomonedas con mayor capitalización de mercado en el momento del análisis: Bitcoin, Ethereum, Dogecoin, Ripple, Cardano, Solana, Tron, Polkadot, Litecoin y Avalanche.

## Objetivo
El propósito de este análisis es arrojar luz sobre cómo las emociones y percepciones del mercado pueden influir en el comportamiento de las criptomonedas. El índice de "Fear and Greed" se utiliza para examinar patrones y correlaciones a lo largo del período mencionado. Esta exploración puede ser valiosa tanto para inversores como para aquellos interesados en comprender el mercado de criptomonedas en un nivel más profundo.

## Librerías Utilizadas
Pandas
Tabulate
Datetime
Seaborn
Matplotlib

## Exploración de Datos
### Data Faltante
Se identificó que faltan valores para el período del 14 al 16 de abril de 2018 en la API del índice "Fear and Greed". Además, la API del índice "Greed and Fear" no proporciona datos previos a febrero de 2018. Estas limitaciones deben ser consideradas al emplear la información del índice. También se destaca que las redes de Solana, Polkadot y Avalanche son más nuevas, lo que resulta en una disponibilidad limitada de datos para estas criptomonedas.

### Valores Duplicados
La mayoría de los valores duplicados en los datos corresponden a nuevas criptomonedas. Se notó un dato duplicado en la categoría de AVAX, lo que resulta curioso ya que este duplicado abarca no solo el precio, sino también el volumen y la capitalización del mercado. Aunque una sola fila no debería afectar significativamente el análisis, se planea sincronizar el conjunto de datos con la API de Binance en el futuro para garantizar mayor precisión. Los valores duplicados en el índice "Fear and Greed" son más comunes, pero no representan una preocupación significativa debido a la limitación de valores posibles en el índice.

### Valores Atípicos (Outliers)
Los histogramas de los valores numéricos muestran una concentración de datos por debajo de la media en todas las criptomonedas. Sorprendentemente, Bitcoin, a pesar de su reputación volátil, carece de valores atípicos, ya que todos los datos se encuentran dentro del rango intercuartil. Se podría esperar que las criptomonedas con menor capitalización de mercado tuvieran más valores atípicos, pero este no parece ser el caso. Polkadot, a pesar de ser más reciente, parece más estable que criptomonedas más establecidas como Cardano, aunque esto puede atribuirse a la disponibilidad limitada de datos para criptomonedas más nuevas.

## Análisis Multivariable
### Correlaciones
En el análisis del mapa de calor, se observa una correlación sólida en los precios de todas las criptomonedas. Solana y Avalanche presentan una correlación relativamente más débil con las demás criptomonedas, pero mantienen una fuerte correlación entre ellas dos. Sin embargo, ninguna criptomoneda muestra una correlación significativa con el índice "Fear and Greed". Si la hipótesis de que este índice es predictivo es válida, esto podría deberse a que la señal de miedo o codicia ocurre días antes del cambio en el precio, ocultando la correlación. Esta hipótesis será evaluada con otros KPIs para obtener una comprensión más completa.

## KPIs (Indicadores Clave de Desempeño)
### Índice de Sharpe
El Índice de Sharpe, fundamental en la evaluación de instrumentos financieros, se utilizó para medir la relación entre rendimiento y riesgo. Aunque algunas criptomonedas mostraron retornos considerables para aquellos que las adquirieron a principios de 2018 y las vendieron a finales de 2022, se observó que el retorno final no compensa suficientemente la alta volatilidad de estos activos. Bitcoin, a pesar de ser considerada segura, muestra el peor Índice de Sharpe en comparación con otras altcoins evaluadas, lo que sugiere que su menor volatilidad no contrarresta los retornos promedios porcentuales superiores de las altcoins.

### Sensibilidad FG
Desarrollamos la Sensibilidad FG, un KPI predictivo que estima el intervalo en el que es probable que el precio experimente un movimiento del 15% en la dirección opuesta al sentimiento actual. Esta métrica ayuda a identificar momentos estratégicos para entrada o salida de inversiones basados en señales de codicia o miedo en el mercado.

### Dominancia Relativa
Creamos el KPI de Dominancia Relativa para evaluar la situación del mercado. Este índice muestra la proporción de la capitalización de mercado total que representa cada criptomoneda. Una mayor dominancia de Bitcoin indica un mercado más conservador, mientras que menor dominancia refleja un mercado más audaz con inversores arriesgados.

## Conclusiones
En resumen, este análisis exploratorio de datos se ha enfocado en profundizar en las relaciones entre las principales criptomonedas y el índice de "Fear and Greed". A través de la utilización de datos extraídos de la API de CoinGecko, hemos examinado detalladamente los valores de apertura diarios abarcando desde enero de 2018 hasta diciembre de 2022. Esta investigación se ha centrado en las diez criptomonedas con mayor capitalización de mercado, incluyendo Bitcoin, Ethereum, Dogecoin, Ripple, Cardano, Solana, Tron, Polkadot, Litecoin y Avalanche.

A pesar de los valiosos insights que hemos obtenido, es importante resaltar que este análisis no es estático, sino un paso hacia la mejora continua. En el futuro, nuestro plan es integrar la API de Binance, una de las principales plataformas de intercambio de criptomonedas, para asegurar una mayor precisión y consistencia en los datos. Esto permitirá abordar de manera efectiva las limitaciones identificadas en cuanto a la calidad y completitud de los datos. Al hacerlo, nuestra tesis se fortalecerá al ofrecer resultados más confiables y respaldados por una fuente adicional de información. Esta expansión de nuestro enfoque se traducirá en una comprensión más profunda y precisa de las interacciones entre las criptomonedas, el sentimiento del mercado y sus efectos en los precios, contribuyendo así al conocimiento y análisis en el emocionante campo de las finanzas digitales.
