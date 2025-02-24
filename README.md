mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| arathtovar$default |
| information_schema |
| performance_schema |
+--------------------+
3 rows in set (0.01 sec)
mysql> use  arathtovar$default;
Database changed
mysql> show tables;
+------------------------------+
| Tables_in_arathtovar$default |
+------------------------------+
| detalle_horario              |
| horario                      |
| plantilla_detalle_horario    |
+------------------------------+
3 rows in set (0.01 sec)
mysql> DESC USUARIOS;
ERROR 1146 (42S02): Table 'arathtovar$default.USUARIOS' doesn't exist
mysql> CREATE TABLE usuarios (
    -> id int(10) not null,
    -> nombre varchar(15) not null,
    -> apellido varchar(15) not null,
    -> departamento varchar(20) not null
    -> primary key(id,nombre)
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '(id,nombre)
)' at line 6
mysql> CREATE TABLE usuarios ( id int(10) not null, nombre varchar(15) not null, apellido varchar(15) not null, departamento varchar(20) not null primary key(id,nombre) );

^C
mysql> 
mysql> CREATE TABLE usuarios (
    -> id int(10) not null,
    -> nombre varchar(15) not null,
    -> apellido varchar(15) not null,
    -> departamento varchar(20) not null,
    -> primary key(id,nombre)
    -> );
Query OK, 0 rows affected, 1 warning (0.03 sec)

mysql> insert into usuarios(id,nombre,apellido,departamento) values
    -> (1,'ricardo','perez','compras'),
    -> (1,'carlos','gutierrez','compras'),
    -> (1,'adrian','tovar','compras'),
    -> (1,'diego','arriaga','compras'),
    -> (1,'saul','chavez','compras'),
    -> (1,'pepe','lomeli','compras'),
    -> (1,'iker','dueñas','compras'),
    -> (1,'valeria','martinez','compras'),
    -> (1,'andrea','correa','compras');
Query OK, 9 rows affected (0.00 sec)
Records: 9  Duplicates: 0  Warnings: 0

mysql> DESC USUARIOS;
ERROR 1146 (42S02): Table 'arathtovar$default.USUARIOS' doesn't exist
mysql> desc usuarios
    -> ;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| id           | int         | NO   | PRI | NULL    |       |
| nombre       | varchar(15) | NO   | PRI | NULL    |       |
| apellido     | varchar(15) | NO   |     | NULL    |       |
| departamento | varchar(20) | NO   |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> show tables;
+------------------------------+
| Tables_in_arathtovar$default |
+------------------------------+
| detalle_horario              |
| horario                      |
| plantilla_detalle_horario    |
| usuarios                     |
+------------------------------+
4 rows in set (0.01 sec)

mysql> select * from usuarios;
+----+---------+-----------+--------------+
| id | nombre  | apellido  | departamento |
+----+---------+-----------+--------------+
|  1 | adrian  | tovar     | compras      |
|  1 | andrea  | correa    | compras      |
|  1 | carlos  | gutierrez | compras      |
|  1 | diego   | arriaga   | compras      |
|  1 | iker    | dueñas    | compras      |
|  1 | pepe    | lomeli    | compras      |
|  1 | ricardo | perez     | compras      |
|  1 | saul    | chavez    | compras      |
|  1 | valeria | martinez  | compras      |
+----+---------+-----------+--------------+
9 rows in set (0.00 sec)

mysql> Insert  into usuarios (nombre,apellido,departamento) values ( 'Lamine', 'Yamal','rh19');
Query OK, 1 row affected, 1 warning (0.00 sec)

mysql> selec * from usuarios;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'selec * from usuarios' at line 1
mysql> 
mysql> select * from usuarios;
+----+---------+-----------+--------------+
| id | nombre  | apellido  | departamento |
+----+---------+-----------+--------------+
|  0 | Lamine  | Yamal     | rh19         |
|  1 | adrian  | tovar     | compras      |
|  1 | andrea  | correa    | compras      |
|  1 | carlos  | gutierrez | compras      |
|  1 | diego   | arriaga   | compras      |
|  1 | iker    | dueñas    | compras      |
|  1 | pepe    | lomeli    | compras      |
|  1 | ricardo | perez     | compras      |
|  1 | saul    | chavez    | compras      |
|  1 | valeria | martinez  | compras      |
+----+---------+-----------+--------------+
10 rows in set (0.00 sec)
