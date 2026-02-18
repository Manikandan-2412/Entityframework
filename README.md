# Entityframework
Learning Something very new


Drawbacks of ado.net
===============
1.simple interaction requires very lengthy piece of code.(minimum it takes 40 lines of code)         in ef --> 3 to 4 lines
2.It doesn't support intelliesence                in ef-->  it supports
3.User has manually manage connections and commands       in ef--> sqlconnection is not requried 
                                                                   no need to  type manually
                                                                   no sqlcommand
4. ado.net is not type safe                                in ef--> type safe
   only checks at the runtime                                       checks at compile time
5. difficult to master                                     in ef --> easy to master
   it has too many classes                                           only one 1 class
6. it doesnot supports linq queries                        in ef --> supports linq   
7. it doesn't use the four pillars                         in ef--> we uses 100% oops

Introduction of EF 
===============================================================================
it is introduced in 2008 (3.5)
Entity : tables 
Framework: a set of classes  and methods

a set of classes designed to work with the tables
EF is an ORM tool
ORM --> Object Relation Mapper

diff b/n ado.net and ef:
========
in ado.net we interact with database directly
--> we use a language which sql understands
EG : select * from tablename

in ef we don't interact with database directly
no need to use any quires
--> Instead of sql query we use linq queries
var res = from t customers
          select ;
the job of ef is to convert all linq queries to corresponding sql queries

how the conversion happens
----------------
ORM --> Object Relation Mapper

object --> c# members 
the front end classes and properties (Model)

Relation --> sql server --> table
eg:   Name(int) description (varchar) price(int)

in entity framework instead of working with table directly.
we work with objects 
--> to perform any crud operation we use objects
ef converts all linq queries to corresponding sql queries

==================================================
IN EF THERE ARE THREE APPORACHES:
1.database first 
   the database must be ready first
   1.context.cs
   2. model.edmx
        --> csdl (conceptual schema definition language) --> the front end schema
          stores the details about the front end schema
          eg: classname,propertyname and datatype
          
        --> ssdl (storage schema definition language) --> stores the backend structure
         eg: tablename,column name, datatype,size,validations 
        --> msl (mapping schema language)
           it maps the data with the csdl with corressponding ssdl code 
2.code first
   the code
3.model first


assignment:
=======
https://drive.google.com/file/d/1UezgDrdCNz-DVzm7XBTdEggMfOmpcv9S/view
======
--------------------------------------------------------------------------------------------------
Code first:
-------
No tables, no database no backend features are exisits
we create classes and properties manually. and ef creates tables and columns accordingly.
tables created automatically.


Advantage of using code first
-----------------------------
1. the user don't have to worry about backend.
2. dbfirst is suitable for smaller projects and codefirst is suitable for larger project.
3. in code first apporach you will have complete control over the program since most of things are managed manually.
4. in the code first apporach no edmx file, no designer (all managed using context file and model file).
5. code first approach is easy to migrate compared to database first approach.
6. code first approach is easier to perform unit test compared to database first.
7. code first approach supports commands,db first doesn't supports commands

steps involved in code first
-----------------------
1.create context file.
2.create model file.
3. register the connection string in appsettings.config file
4. create object of context file and initialize the values.

varchar -> doesn't support unicode
nvarchar -> supports unicode


EnableMigrations:
-----
- by default interacting with sql server is disabled.
- u cannot update any changes to sql server
  Enable migration command allows to interact with sql server

AddMigration
- add all the changes.
Update-Migraion
- update the changes to the project

  want to add new column :
  -------
  1. add new change
  2. create new age propert
  3. create migration file
  4. run the update command
Update-Database -TargetMigration migrationfilename
-----------------------------------------------------------
Validations:
-------
1. customer name should be only alphablets
2. 
