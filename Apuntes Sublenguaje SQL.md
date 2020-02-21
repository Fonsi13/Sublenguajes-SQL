# Apuntes Sublenguajes SQL

 1. [DDL](#DDL)
 2. 

## DDL()<a name="DDL"></a>
### CREATE TABLE
#### [CONSTRAINT <nombre-de-la-restricción>]
#### [ON DELETE
Tiene cuatro opciones de borrado *NO ACTION*, *CASCADE*, *SET NULL* y *SET DEFAULT*
##### NO ACTION
##### CASCADE
Mediante esta opción lo que se estaría eliminando la tupla que queramos, por lo que a su vez estaríamos eliminando automáticamente todas las tuplas que hacen referencia a ella, eliminando en "cascada" 
##### SET NULL
##### SET DEFAULT
#### [MATCH FULL]
La clave foránea 
#### [MATCH PARTIAL]
#### UNIQUE (< atributos >),
Se aplica sobre las claves candidatas de un objeto,  cuarto tipo de restricción en **CREATE TABLE**
#### CHECK predicado( atributos )
Son restricciones de comprobación, solo se puede modificar(borrado, insercción o modificación) la tupla cuando la comprobación devuelve true. Tiene diferentes opciones **[ NOT DEFERRABLE]** o **[DEFERRABLE]**
##### [[NOT] DEFERRABLE]
Es el valor determinado
Con el **NOT** la comprobación se realiza al momento, no se puede aplazar, antes de realizar la operación
##### ([INITIALLY  INMEDIATE | DEFERRABLE])
Si es **deferrable iniatilly deferrable**, puedes posponer la comprobación
Si es **deferrable iniatilly inmediate**, valor por defecto, con el que obliga a realizar la comprobación antes que nada
### DROP
#### DROP SCHEMA  
La utilizamos para eliminar una base de datos
```SQL
DROP SCHEMA [IF EXISTS] <nome-de-la-bd>;
```
#### DROP TABLE 
La utilizamos para eliminar una tabla
``` SQL
DROP TABLE [IF EXISTS] <nome-de-la-tabla> [CASCADE | RESTRICT];
```
**CASCADE** significa que borras todo, tanto la tabla como las que tienen dependencia con ella
**RESTRICT** significa no deja borrar la tabla si tiene tablas hijas que tienen , cargas el esquema
### ALTER
#### ALTER TABLE
A la hora de alterar una tabla nos referimos a modificar las columnas, añadir o eliminar una, o modificar las restricciones, añadir o eliminar una.
##### ADD [COLLUMN]
Sirve para añadir una columna a la tabla
``` SQL
ALTER TABLE <nombre-da-tabla> ADD [COLLUMN] < atributo > < dominio > + ...;
```
##### DROP [COLLUMN]
Sirve para eliminar una columna de la tabla
``` SQL
ALTER TABLE <nombre-da-tabla> DROP [COLLUMN] < atributo > [CASCADE | RESTRICT];
```
##### ADD < restricción >
Sirve para añadir una restricción a la tabla
##### DROP < restricción >
Sirve para eliminar una restricción de la tabla

En resumen, la estructura de **ALTER TABLE** es la siguiente:
``` SQL
ALTER TABLE <nombre-da-tabla> 
  ADD [COLLUMN] < atributo > < dominio > + ...
| DROP [COLLUMN] < atributo > [CASCADE | RESTRICT]
| ADD < restricción > 
| DROP < restricción >;
```
