# ODBC-Access-to-SQL-Server
ODBC Access to SQL server through IBM informix driver in R and Extracting dump of Tables

We require library "ibmdbR","ODBC"

ibmdbR: IBM in-Database Analytics for R
Functionality required to efficiently use R with IBM(R) Db2(R) Warehouse offerings (formerly IBM dashDB(R)) and IBM Db2 for z/OS(R) in conjunction with IBM Db2 Analytics Accelerator for z/OS.

ODBC: Open Database Connectivity (ODBC) drivers. 
This allows for an efficient, easy to setup connection to any database with ODBC drivers available, including SQL Server, Oracle, MySQL, PostgreSQL, SQLite and others.

In addition we require below said details on SQL server.
1) HostName
2) PortNumber (50000 if not using SSL or 50001 if using SSL)
3) User name
4) Password
5) DSNName
6) Database Name
7) Protocol Used
8) Driver Name

In addition you need IBM Informix ODBC driver (32 Bit or 64 Bit depends on your system)

##CODE##

library(ibmdbR)
library (ODBC)
driver.name <- "{IBM INFORMIX ODBC DRIVER (64-bit)}" 
db.name <- "PlaceHolderForYourDatabseName"   
host.name <- "PlaceHolderForYourHostName"
port <-"PlaceHolderForPortNumber"
user.name <-"PlaceHolderForYourusername"
pwd <- "PlaceHolderForYourPassword"
con.text <- paste("PlaceHolderForYourDSNName";DRIVER=",driver.name,
                  ";Database=",db.name,
                  ";Host=",host.name,
                  ";Port=",port,
                  ";PROTOCOL=PlaceHolderForYourProtocolName",  
                  ";UID=", user.name,
                  ";PWD=",pwd,sep="",
                  ";CLIENT_LOCALE=en_US.UTF8",
                  ";DB_LOCALE=en_US.57372")

# Connect to using a odbc Driver Connection string to a remote database
con <- idaConnect(con.text)

# Extract Tablelist from Database
Tablelist = sqlTables(con, schema = character)

# Make a copy of tables in your local system
list = Tablelist1$TABLE_NAME
for (table in list){
  data <- sqlQuery(con, paste("SELECT * FROM (",table,")"))
  name = paste("PlaceholderForYourLocalDesktopPath",table,".csv")
  write.csv(data,paste("PlaceholderForYourLocalDesktopPath",table,".csv", sep=""))}


