Browser Terminal
================

Browser Terminal (written in node.js) can be used in any web application where you need a real-time terminal in the browser to monitor 
execution of some shell command. Typical workflow would be to ask the user for some parameters, which will result in a command that is 
stored in MySQL after which the user will be redirected to the exection page which will show the realtime exection

 
Key Features
============

 - Read only terminal, except for the Ctrl-C signal which will abort execution
 - Command provisioned from MySQL
 - Output log is stored in MySQL
 - Multiple monitoring instances supported (multiple users can view same execution) 


Installation
============

Clone repository and do:

    npm install

 
Configuration
=============

There is a configuration file in the root ``config.json``. Default configuration is

    {
      "port" : 8080,
      "dbhost" : "localhost",
      "dbname" : "organist",
      "dbuser" : "root",
      "dbpassword" : "vagrant",
      "table" : "CommandLog",
      "idField": "id",
      "commandField" : "command",
      "logField": "log"
    }


Parameters:

 - port: on which port the node application is running
 - dbhost: MySQL host
 - dbname: MySQL database
 - dbuser: MySQL user
 - dbpassword: MySQL password
 - table: MySQL table which provides commands to be executed and where output is stored
 - idField: primary key column name for command table (int)
 - commandField: column name for the command (varchar(255) / text)
 - logField: column name where output is stored (text)


Screenshot
==========

![alt tag](https://raw.github.com/markri/browser-terminal/master/terminal.png)
