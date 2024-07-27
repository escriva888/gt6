# CREATE DATAFILE PATH ONCE LOGGED AS ORACLE AND GRANT THE PRIVILEDGES.
mkdir -p /u01/app/oracle/oradata/ORCL
chown -R oracle:oinstall /u01/app/oracle/oradata
chmod -R 755 /u01/app/oracle/oradata
# CREATE TABLESPACE
-- Create the tablespace
CREATE TABLESPACE license_data (license data is the DB NAME)
DATAFILE '/u01/app/oracle/oradata/ORCL/license_data01.dbf'
SIZE 100M
AUTOEXTEND ON
NEXT 10M MAXSIZE 1000M;
# CREATE THE USER
CREATE USER license_user IDENTIFIED BY "W411#567isCool"
DEFAULT TABLESPACE license_data
TEMPORARY TABLESPACE temp
QUOTA UNLIMITED ON license_data;
-- Grant required privileges to the user
GRANT CONNECT, RESOURCE, DBA TO SIDIAN_USER;(Grants all the priviledges)
