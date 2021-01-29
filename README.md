# django_install

## Install 

### Install conda envirionment 

``` Shell 
 conda env create -f django.yml
 source activate django
```
### Set up database 

``` Shell
# 1. init db
pg_ctl -D /Users/frank/pgsql/data -l logfile init

# 2. start db 
pg_ctl -D /Users/frank/pgsql/data -l logfile start

# 3. create db
createdb django_data

# 4. enter db
psql -d django_data
```

## Run 

* put deploy.ini file under folder epigen_ucsd_django/, change DATABASE_USER,DATABASE_PASSWORD(if you have set one),DATABASE_NAME in the file deploy.ini
* Before makemigrations and migrate, replace file form.py under setqc_app and singlecell_app with the one in dropbox respectively
* run makemigraions and migrate:
``` Shell
python manage.py makemigrations
python manage.py migrate
```
* change file form.py under setqc_app and singlecell_app back to the origin one
* (optional)run command to create superuser who could login to django-admin:
``` Shell
python manage.py createsuperuser
```
* runserver:
``` Shell
python manage.py runserver 
```

