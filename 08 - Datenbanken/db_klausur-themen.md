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
(..., ...)
```
### Update

### Delete

### Join

## Normalisierung
### Erste NF.

### Zweite NF.

### Dritte NF.