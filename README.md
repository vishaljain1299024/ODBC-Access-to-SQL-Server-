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

