# Klausur Themen
___
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


## Indices

