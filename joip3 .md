### mysql in statefulset
```
command to create mysqldb container 
 docker container run -d --name mysqldb -e MYSQL_ROOT_PASSWORD=rootroot -e MYSQL_DATABASE=employees -e MYSQL_USER=vinodhreddy -e MYSQL_PASSWORD=rootroot -p 11111:3306 mysql
 * docker container ls
 * docker container exec -it mysqldb mysql --password=rootroot

 *use employees;
 CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
*  Insert into Persons Values (1,'test','test', 'test', 'test');
* Select * from Persons;

 
 ![preview](/ganeshreddy/ganeshreddy/mysql%20inside.png)
 ```

 ### Stateless set
  
  create the volume here:docker volume create vol1
  then run the container :
* docker container run -d --name mysqldb -e MYSQL_ROOT_PASSWORD=rootroot -e MYSQL_DATABASE=employees -e MYSQL_USER=vinodhreddy -e MYSQL_PASSWORD=rootroot -p 11111:3306 mysql


* docker container run -d --name vol1 --mount "source=mysqldb,target=/var/lib/mysql,type=volume" -P -e MYSQL_ROOT_PASSWORD=rootroot
-e MYSQL_DATABASE=employees -e MYSQL_USER=vinodreddy -e MYSQL_PASSWORD=rootroot mysql

*  show databases;
* use employees;
* Select * from Persons;

[preview](/ganeshreddy/ganeshreddy/statelessset.png)
```
