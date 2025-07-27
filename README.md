
# SEGUIMIENTO 1 – BIOINFORMÁTICA 🧬
## Organismo: *Astatotilapia calliptera* 🐟
### Mariana Aguirre Llano



## 1. 📑 DESCRIPCIÓN DEL FORMATO GFF3 (GENERIC FEATURE FORMAT VERSION 3)

#### El formato GFF3 (General Feature Format versión 3) es un estándar usado para describir anotaciones genómicas. Cada línea representa una característica biológica (feature) en el genoma, como genes, exones, ARN, regiones regulatorias, etc. Las columnas están separadas por tabulaciones (\t), y cada línea sigue el mismo orden estructurado.

 | Nº | Campo          | Descripción                                                                       |
| -- | -------------- | --------------------------------------------------------------------------------- |
| 1  | **seqid**      | El nombre de la secuencia, como un cromosoma o un andamiaje.                      |
| 2  | **source**     | Fuente de la anotación (nombre de la base de datos o del proyecto).               |
| 3  | **type**       | Tipo de característica anotada (gene, exon, CDS, mRNA, region, etc.).             |
| 4  | **start**      | Posición inicial de la característica en la secuencia (base 1).                   |
| 5  | **end**        | Posición final de la característica.                                              |
| 6  | **score**      | Puntuación, valor de punto flotante (por ejemplo, confianza en la predicción)     |
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

##### *Astatotilapia calliptera* es un pez de agua dulce que pertenece a la familia de los cíclidos. Habita principalmente en lagos y ríos del sudeste africano, como el lago Malawi. Es una especie muy estudiada porque presenta gran diversidad genética, lo que la hace útil para investigaciones en evolución, genética del desarrollo y adaptación (Naturalista., sf).

### b. Preguntas

#### i. ¿Cuántos features contiene el archivo?
##### Un "feature" es una línea de datos, así que contaremos las líneas que no son comentarios.
##### El siguiente código nos arroja un resultado de **2307837 features**
``` bash
# Contar líneas que no sean comentarios (líneas que inicien con #)
grep -v "^#" Astatotilapia_calliptera.fAstCal1.3.114.gff3 | wc -l  
```

#### ii. ¿Cuántas regiones de la secuencia (cromosomas) contiene el archivo?
##### El siguiente código nos arroja un resultado de **248**
``` bash
# Contar cuántas regiones genómicas están anotadas (columna 3 = region)
grep -P "\tregion\t" Astatotilapia_calliptera.fAstCal1.3.114.gff3 | wc -l
```
#### iii. ¿Cuántos genes están listados en el organismo?
##### El siguiente código nos arroja un resultado de **25714**
``` bash
# Contar cuántos genes están anotados (columna 3 = gene)
grep -P "\tgene\t" Astatotilapia_calliptera.fAstCal1.3.114.gff3 | wc -l
```
#### iv. ¿Cuál es el top 10 de tipo de features (columna 3) más anotados en el genoma?
##### El siguiente código nos arroja lo siguiente:
| Feature             | Frecuencia   |
|---------------------|--------------|
| exon                | 1,054,286    |
| CDS                 | 1,002,359    |
| mRNA                | 76,105       |
| five_prime_UTR      | 71,961       |
| three_prime_UTR     | 58,786       |
| ### (posible error) | 33,589       |
| gene                | 25,714       |
| lnc_RNA             | 9,679        |
| ncRNA_gene          | 7,440        |
| miRNA               | 418          |
``` bash
# Top 10 de tipos de features más anotados en la columna 3
cut -f3 Astatotilapia_calliptera.fAstCal1.3.114.gff3 | sort | uniq -c | sort -nr | head -10
```


