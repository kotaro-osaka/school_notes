# Klausur Themen
___


## Excel → ERD
![](99%20-%20misc/Pasted%20image%2020260309112147.png)

![](99%20-%20misc/Pasted%20image%2020260309112005.png)
## ERD → Relationen
![](99%20-%20misc/Pasted%20image%2020260309112242.png)
## SQL
### Create Table
```mysql
CREATE TABLE _Tabellenname_ (
_Attribut1_ INT PRIMARY KEY AUTO_INCREMENT,
_Attribut2_ VARCHAR(50),
_Attribut3_ VARCHAR(50),
CONSTRAINT C_Attribut3 CHECK (LENGTH(_Attribut3_ > 1)),
CONSTRAINT fk_Attribut2 FOREIGN KEY(_Attribut2_) REFERENCES Tabelle2(_Attribut2_)
    ON UPDATE NO ACTION
    ON DELETE NO ACTION)
ENGINE = INNODB
COLLATE = UTF8_GERMAN2_CI
CHARSET = UTF8;
```
### Insert
```mysql
INSERT INTO _Tabellenname_ VALUES
(..., ...),
...;
```
### Update
```mysql
UPDATE table_name SET
column1 = value1, column2 = value2,
...
WHERE ...;
```
### Delete
```mysql
DELETE FROM table_name WHERE ...;
```
### Selects
```mysql
SELECT DISTINCT ... FROM ...;
```
### Joins
```mysql
SELECT ... FROM ...
INNER/LEFT/RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```
## Normalisierung
### Erste Normalform
> Die erste Normalform ist gegeben, wenn alle Daten atomar sind.
### Zweite Normalform
> Die zweite Normalform ist gegeben, wenn die erste erfüllt ist und wenn alle Nicht-Schlüsselattribute vollfunktional von einem Primärschlüssel abhängig sind.
### Dritte Normalform
> Die dritte Normalform ist gegeben, wenn die zweite erfüllt ist und wenn alle Daten transitiv voneinander abhängig sind.
## Anomalien

## Indices