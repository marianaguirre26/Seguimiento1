
# SEGUIMIENTO 1 – BIOINFORMÁTICA 🧬
## Organismo: *Astatotilapia calliptera* 🐟
### Mariana Aguirre Llano



## 1. 📑 DESCRIPCIÓN DEL FORMATO GFF3 (GENERIC FEATURE FORMAT VERSION 3)

#### El formato GFF3 (General Feature Format versión 3) es un estándar usado para describir anotaciones genómicas. Cada línea representa una característica biológica (feature) en el genoma, como genes, exones, ARN, regiones regulatorias, etc. Las columnas están separadas por tabulaciones (\t), y cada línea sigue el mismo orden estructurado.

 | Nº | Campo          | Descripción                                                                       |
| -- | -------------- | --------------------------------------------------------------------------------- |
| 1  | **seqid**      | Identificador de la secuencia (por ejemplo, el cromosoma o contig).               |
| 2  | **source**     | Fuente de la anotación (herramienta, base de datos o pipeline que la generó).     |
| 3  | **type**       | Tipo de característica anotada (gene, exon, CDS, mRNA, region, etc.).             |
| 4  | **start**      | Posición inicial de la característica en la secuencia (base 1).                   |
| 5  | **end**        | Posición final de la característica.                                              |
| 6  | **score**      | Puntuación (por ejemplo, confianza en la predicción); puede ser "." si no aplica. |
| 7  | **strand**     | Hebra de ADN: "+" (sentido) o "−" (antisentido).                                  |
| 8  | **phase**      | Solo para CDS: 0, 1 o 2; indica dónde comienza el primer codón completo.          |
| 9  | **attributes** | Información adicional en formato clave=valor, separada por punto y coma (;).      |


## 2. 📁 DESCARGA DEL ARCHIVO 
```bash
# Creamos una carpeta nueva donde guardaremos todos los documentos necesarios para este ejercicio y accedemos a ella
mkdir -p seguimiento1
cd seguimiento1

# Descargamos la información usando el comando wget que nos permite descargar archivos de Internet
wget http://ftp.ensembl.org/pub/current_gff3/astatotilapia_calliptera/Astatotilapia_calliptera.fAstCal1.3.114.gff3.gz

# Descomprimimos el archivo 
gunzip Astatotilapia_calliptera.fAstCal1.3.114.gff3.gz
```

## 3. 🎯 ANÁLISIS DEL ARCHIVO

### a. Descripción del organismo

### 

### b. Preguntas

#### i. ¿Cuántos features contiene el archivo?
``` bash
# Contar líneas que no sean comentarios (líneas con anotaciones)
grep -v "^#" Astatotilapia_calliptera.fAstCal1.3.114.gff3 | wc -l
```
##### Esto nos arroja un resultado de 2307837 features

#### ii. ¿Cuantas regiones de la secuencia (cromosomas) contiene el archivo?
``` bash

```
#### iii. ¿Cuántos genes están listados en el organismo?
``` bash

```

#### iv. ¿Cuál es el top 10 de tipo de features (columna 3) más anotados en el genoma?
``` bash

```


