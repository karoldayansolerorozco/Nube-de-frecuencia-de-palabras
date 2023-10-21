# Nube-de-frecuencia-de-palabras
Nube de palabras en KNIME
Instrucciones 
Preparación inicial
1.	Busque e instale la extensión para análisis de texto Knime TextProcessing.
-	Ve a "File" (Archivo): Haz clic en "File" en la barra de menú en la parte superior izquierda de la ventana de KNIME.
-	Selecciona "Install KNIME Extensions" (Instalar extensiones de KNIME): En el menú desplegable de "File", selecciona "Install KNIME Extensions". Esto abrirá la ventana de instalación de extensiones

2.	Busque e instale la extensión para visualizar taggs Knime JavaScript Views (labs).

3.	Cargue el conjunto de datos Frases.xlsx con el nodo Excel Reader. Explore el archivo en la visualización.

 

4.	Usando el nodo Strings to document convierta los textos en formato documento. Luego seleccione la columna Documents con el nodo Column Filter.

Identificación de POS y NER
5.	Con el nodo POS Tagger identifique el tipo de palabras en cada documento. Visualice los resultados con el nodo Taggered Document Viewer. La lista de tags la encuentra en este link: https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html 

6.	Para reconocer entidades nombradas (NER) se puede utilizar el nodo StanfordNLP NE Tagger. Este nodo permite identificar nombres de personas, organizaciones, lugares y otros. Puede visualizar los resultados utilizando el nodo Taggerd Document Viewer.
Limpieza de texto
7.	Elimine lo signos de puntuación con el nodo Punctuation Erasure.

8.	Elimine los caracteres numéricos con el nodo Number Filter.

9.	Elimine StopWords en idioma inglés usando el nodo Stop Word Filter. Se puede utilizar una lista de Stop words que trae KNIME o utilizar una lista propia. En este caso, y solo para ilustrar, lea el archivo de stop words proporcionado (use el nodo File Reader) y conéctelo al nodo de limpieza.

10.	Convierta todo el texto a minúsculas usando el nodo Case Converter.

11.	Pruebe el nodo Snowball Stemmer sobre los datos. Analice la salida. Remuévalo. 
Creación del bag of words y de la matriz estructurada
12.	Mediante el nodo Bag of Words Creator genere la bolsa de palabras de las frases.

13.	Con el nodo Document Vector cree la matriz de frecuencias por documento y palabra. En KNIME a la matriz se le llama vector.
Visualización en nube de palabras
14.	Al nodo de Bag of Words conéctele el nodo TF para calcular la frecuencia relativa de cada palabra dentro de cada documento. Esta frecuencia será el insumo para el color y el tamaño en la nube de palabras.

15.	Usando el nodo Color Manager configure la columna TF rel para la asignación de color en la nube de palabras. 

16.	Conecte el nodo Tag Cloud y visualice los resultados.
Matriz TF-IDF
17.	Al nodo TF conecte el nodo TDF y calcule la matriz IDF en su variante normalized.

18.	Agregue el nodo Math Formula y con la expresión $TF rel$*$IDF$ calcule la matriz TF-IDF.

