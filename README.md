Organist Terminal
=================

Organist Terminal (organist-term) is written in node.js and can be used in any web
application where you need a real-time terminal in the browser to monitor execution
of some shell command. Typical workflow would be to ask the user for some parameters,
which will result in a command that is stored in MySQL after which the user will be
redirected to the exection page which will show the realtime exection.

Its use case is very specific for the Organist deployment tool, but should be usable
on its own.


Key Features
============

 - Read only terminal, except for the Ctrl-C signal which will abort execution
 - Command provisioned from MySQL
 - Output log is stored in MySQL
 - Multiple monitoring instances supported (multiple users can view same execution)


Installation
============

    npm install organist-term


Configuration
=============

Default configuration is stored in ``package.json``. And can be overwritten by using the default
configuration override method which is described at https://docs.npmjs.com/misc/scripts#special-packagejson-config-object.

Default values:

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


Description:

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

![alt tag](https://raw.github.com/markri/organist-term/master/terminal.png)
