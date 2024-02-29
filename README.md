# Oracle_FDW-Installation
An PostgreSQL extension Used to fetch oracle data from postgres

Oracle Client Rpm's Link:- https://www.oracle.com/database/technologies/instant-client/linux-x86-64-downloads.html

Oracle_fdw extension Link :- https://pgxn.org/dist/oracle_fdw/2.4.0/

Downlaod the files from the above links 

Upload the Downloaded files to the server.

Move to the location where you upload the files & follow the below steps.

Unzip the uploaded oracle_fdw-2.4.0.zip file using **unzip oracle_fdw-2.4.0.zip**

Install the Oracle client RPMS 

**sudo yum install oracle-instantclient12.2-devel-12.2.0.1.0-1.x86_64.rpm**

**sudo yum insatll oracle-instantclient12.2-sqlplus-12.2.0.1.0-1.x86_64.rpm**

**sudo yum install oracle-instantclient12.2-basic-12.2.0.1.0-1.x86_64.rpm**

After Installing these Packages move to the unzip oracle_fdw-2.4.0 folder issue make & make install commands

**make**

**if you got the this error means make:pg_config : command not found 
make :*.* no tragets. stop**

Do the below steps :
**sudo vi Makefile
pg_config=/path/to/your/pg_config/file**

then again issue the make commad

**make**

**make install**

Set the LD_LIBRARY_PATH

sudo export LD_LIBRARY=/path/of/your/LD_LIBRARY_PATH/

Set the ORACLE_HOME_PATH 

sudo export ORACLE_HOME=/path/of/your/oracle_home/

start your postgresql cluster 

Create the extension Oracle_fdw by the below Command.

**psql> create extension oracle_fdw;**
if it throws an error 

move to the postgresql.conf file 

on that file set the **shared_preload_libraries='oracle_fdw'**

again try to create the extension using the above command it will work.
