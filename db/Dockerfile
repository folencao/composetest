# using sql server image
FROM microsoft/mssql-server-windows-express:2017-latest

# create directory within SQL container for database files
SHELL ["powershell", "-command"]

#VOLUME C:\\database

RUN mkdir C:\\SQLServer

#copy the database files from host to container
COPY AppVeyorTest.mdf /SQLServer
COPY AppVeyorTest_log.ldf /SQLServer

#RUN dir

# set environment variables
ENV sa_password=admin*123

ENV ACCEPT_EULA=Y
#ENV DB_FOLDER=database
ENV attach_dbs="[{'dbName':'AppVeyorTest','dbFiles':['C:\\\\SQLServer\\\\AppVeyorTest.mdf','C:\\\\SQLServer\\\\AppVeyorTest_log.ldf']}]"
#test attach from volume
#ENV attach_dbs="[{'dbName':'AppVeyorTest','dbFiles':['C:\\\\${DB_FOLDER}\\\\AppVeyorTest.mdf','C:\\\\${DB_FOLDER}\\\\AppVeyorTest_log.ldf']}]"
