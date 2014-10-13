Requirements
=====================================================
In order to run Cyclos, you will need a Java Runtime Environment (JRE), which can be downloaded at
http://www.java.com. Java 1.6 (aka 6.0) is required.
To test if Java is installed, or which version of java you have, open a terminal (linux / bsd) or click on the
start menu, select Run and type 'cmd' (sans quotes), and type 'java -version' (sans quotes).

Run Cyclos
=====================================================
* Run the start_cyclos.bat script (windows) or start_cyclos script (linux / bsd)  (for languages other than english, 
  please refer to the language section below)
* When you see the message "Cyclos standalone server started at http://localhost:8080/", 
  open a web browser and go to that url (http://localhost:8080/)
* Login as user: admin and password: 1234 
  (if you want to login as you member you will need to create a member first on the administration section)
* To shutdown Cyclos, press Ctrl+C on the Cyclos shell

Backup / Restore Database
=====================================================
* To backup: copy the data folder (under Cyclos) and all files in it.
* To restore: put the data directory and the files back.

Logs
=====================================================
The log files are written in the cyclos/logs directory

Switch to MySQL database
=====================================================
For Cyclos production use, recommend the (open source) MySQL database.
These are the steps to switch to MySQL.
* Download and install MySQL http://www.mysql.com/
* Create a database on MySQL (for example, with the command 
  'create database cyclos'). You may use another database name
* Open the file cyclos\web\WEB-INF\classes\cyclos.properties
* Comment the HSQL entries by putting a # sign in front of each entry and 
  un-comment the msyql entries (delete the first # sign)
* Configure the database name you created (cyclos on the example) on the 
  property 'hibernate.connection.url'
* When starting Cyclos, an initial database will be created

Languages other than English
=====================================================
If you want the default database in an other language you will need to make
some changes to the file: \WEB-INF\classes\cyclos.properties and change the 
'cyclos.embedded.locale' property value to the one of the following values: 
en_US, fr_FR, nl_NL, de_DE, pt_BR, es_ES, zh_CN, it_IT, ru_RU, el_GR, or ja_JP.

Tips
=====================================================
The default database only comes with an admin and not with a member. You can
create a member by going to "Users & Goups - Manage Members" and select the
Full member group from the "Create Member" drop down. This will open a 
registration form that need to be submitted (Select and open profile). In this
page you set the password with the "Manage login password" function. Cyclos
has an option to send an invitation mail to new members with a temporary 
password that needs to be changed on the first login, this function is disabled
by default but can be enabled in the member group configuration.