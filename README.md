# mysql_recover-_tables_from_ibd_format
Way to Rebuild mysql database table after xamp or wamp server change 

Delete database

then create old table for example this
CREATE TABLE IF NOT EXISTS sms(id INTEGER PRIMARY KEY, status text CHARACTER SET utf8mb4, sender TEXT, receiver TEXT , date_time timestamp,status TEXT,extra TEXT);

remove link between ibd & mysql server
ALTER TABLE sms DISCARD TABLESPACE;

replace ibd files in database folder

rebuild link between mysql & database tables
ALTER TABLE sms IMPORT TABLESPACE;
