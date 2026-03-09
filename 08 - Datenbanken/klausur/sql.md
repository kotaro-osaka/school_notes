# SQL
## Create Table
*With check & foreign key*

```mysql
CREATE TABLE table_name (
column_1 INT PRIMARY KEY AUTO_INCREMENT,
column_2 VARCHAR(50),
column_3 VARCHAR(50),
CONSTRAINT c_column3 CHECK (LENGTH(column_3 > 1)),
CONSTRAINT fk_column2 FOREIGN KEY(column_2) REFERENCES table2_name(column_2)
    ON UPDATE NO ACTION
    ON DELETE NO ACTION)
ENGINE = INNODB
COLLATE = UTF8_GERMAN2_CI
CHARSET = UTF8;
```