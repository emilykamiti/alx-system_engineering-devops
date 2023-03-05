# Postmorterm

![](https://miro.medium.com/v2/resize:fit:1200/format:webp/1*FzISQlkPm2rNKPCKjp4DUA.png)

The README for project 0x19-postmortem located within the holberton-system_engineering-devops repo is actually a postmortem based off multiple past projects. It is an issue that rises all the time.

# issue summary
Project issue started on Dec 12th 2022, at 12:35 EAT and ended on Dec 14th 2022, at 15:02 EST.

The impact this issue had was that the project was not able to be tested on. Data in the SQL database was not able to be accessed.

The root cause of this issue was that the MySQL service was never started. This issue was found by running the command:

HBNB_MYSQL_USER=hbnb_dev HBNB_MYSQL_PWD=hbnb_dev_pwd HBNB_MYSQL_HOST=localhost HBNB_MYSQL_DB=hbnb_dev_db HBNB_TYPE_STORAGE=db ./test_get_count.py

This issue was resolved by running the command:

# sudo service mysql start
This may be prevented in the future by checking if the MySQL service is running before using it in anyway. This can also be applied to any other services that may be used, such as nginx.

# Timeline
Issue occurred after running a command with a test file that interacted with the MySQL database.
Issue detected when error message appeared.
Actions taken was to investigate the test file.
Misleading investigation of test file as the issue wasn't there.
Incident escalated to asking fellow cohort 10 student, Ezra Nobrega, to take a look at the error message.
Nobrega told me the MySQL service needed to be started before being able to interact with it.


