
Based On [https://github.com/dternyak/React-Redux-Flask](https://github.com/dternyak/React-Redux-Flask)


### Test Back-End

```sh
$ python test.py --cov-report=term --cov-report=html --cov=application/ tests/
```

# glaas
Good Layoffs As A Service

### Basic Workflow
```
pip install
python manage.py runserver
cd static
npm install
DEV npm start
BUILD npm run build:production
open browser, go to http://localhost:3000/register
```

If you decide on MySQL, install the free community edition of [MySQL](https://dev.mysql.com/downloads/mysql/) and [MySQL Workbench](https://www.mysql.com/products/workbench/)

1. start MySQL from the System Preferences
2. open MySQL Workbench and [create a database](http://stackoverflow.com/questions/5515745/create-a-new-database-with-mysql-workbench) called mydatabase but don't create the tables since python will do that for you
3. Install the MySQL connector for Python, add the DATABASE_URL configuration, and create the database and tables

```
$ sudo pip install mysql-connector-python-rf
$ export DATABASE_URL="mysql+mysqlconnector://username:password@localhost/mydatabase"
$ python manage.py create_db
```

Note: you do not need to run "python manage.py db upgrade" or "python manage.py db migrate" if its your first go at it


### Create DB
```sh
$ export DATABASE_URL="postgresql://username:password@localhost/mydatabase"

or

$ export DATABASE_URL="mysql+mysqlconnector://username:password@localhost/mydatabase"

or

$ export DATABASE_URL="sqlite:///your.db"

More about connection strings in this [flask config guide](http://flask-sqlalchemy.pocoo.org/2.1/config/)

$ python manage.py create_db
$ python manage.py db upgrade
$ python manage.py db migrate
```

To update database after creating new migrations, use:

```sh
$ python manage.py db upgrade
```