1) We shouls log in to an interactive Postgres session usin the following command: 
sudo -iu postgres psql

2) Create a database for your project with such command:
postgres=# CREATE DATABASE flask_db;

3) Create a database user for our project.
postgres =# CREATE USER max WITH PASSWORD 'password';

4) Then you should give new user 'max' access to administer your new database:
postgres=# GRANT ALL PRIVILEGES ON DATABASE flask_db to max

5) To confirm the database was created, get the list of databaes by typing the following command

postgres=# \l

6) Then exit out of PostgreSQL

postgres=# \q


7) For the database connection to be established, set the DB_USERNAME and DB_PASSWORD environment variables by running the following commands. Remember to use your own username and password:

export DB_USERNAME="max"
export DB_PASSWORD="password"

8) Now, run your init_db.py file in the terminal using the python command:

python init_db.py

9) Log in to an interactive Postgres session to check out the new books table.

sudo -iu postgres psql

10) Connect to the flask_db database using the \c command:

\c flask_db

11) Then use a SELECT statement to get the titles and authors of books from the books table:

SELECT title, author FROM books;

12) In this step, you’ll create a Flask application with an index page that retrieves the books that are in the database, and display them.

While in your flask_app directory with your virtual environment activated, tell Flask about the application (app.py in this case) using the FLASK_APP environment variable. Then set the FLASK_ENV environment variable to development to run the application in development mode and get access to the debugger. For more information about the Flask debugger, see How To Handle Errors in a Flask Application. Use the following commands to do this:

export FLASK_APP=app
export FLASK_ENV=development

Make sure you set the DB_USERNAME and DB_PASSWORD enviroment variables if you haven't already:
export DB_USERNAME="sammy"
export DB_PASSWORD="password"

13)Run the app
flask run

14) Finally visit the followinf URL using your browser:
http://127.0.0.1:5000/
