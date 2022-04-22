# Bd Nevera
## Consideraciones a tener presente
! El nombre de las **columnas** de la base de datos aqui disponible se encuentran **encriptadas mediante** una funcion **hash**; la base de datos se encuentra en el **formato .parquet y comprimida mediante brotli** para asi poder reducir su tamaño, tiempo de descarga y tiempos de carga a las diferentes plataformas, tanto Google Colab como GitHub.
## Leer y comprimir de nuevo de la Base de Datos
! Para la explicacion de esta sub-seccion se asumen los siguientes numerales. 

  1. Se hace uso de Python como lenguaje de programacion. 
  2. Se hace uso de la libreria pandas para la lectura y compresion de la Base de Datos. 
  3. Se tiene instalada la libreria pandas en el entorno local o en la pltaforma para su posterior uso. 

### Para la lectura de la Base de Datos haciendo uso de la libreria pandas
<pre><code>import pandas as pd
db = pd.read_parquet("db.parquet.brotli")
db.sample(15) #sacar 15 muestras aleatorias de la Base de Datos
</code></pre>


### Para la compresion de la Base de Datos haciendo uso de la libreria pandas


<pre><code>import pandas as pd

#db.to_parquet(nombre_del_archivo_a_descargar.parquet.brotli, 
#index = False, para no guardar el indice de las filas 
#compression = "brotli") tipo de compresion usada

db.to_parquet("db.parquet.brotli", index = False, compression = "brotli")
</code></pre>
