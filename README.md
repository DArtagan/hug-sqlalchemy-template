hug-sqlalchemy-template
=======================

Hug project skeleton with working sqlalchemy connections tests and migrations framework already set up.
Basically it's good entry point to develop every kind of sqlalchemy powered api using hug.

## Prerequisites
It runs only with Python 3

## Installation
```
git clone https://github.com/FutureMind/hug-sqlalchemy-template.git
pip install -r requirements.txt
gunicorn --reload api.app:__hug_wsgi__
```
API will be exposed locally to http://127.0.0.1:8000

## Database
Provide SQLALCHEMY_DATABASE_URI and TEST_SQLALCHEMY_DATABASE_URI environment variables.
If TEST_SQLALCHEMY_DATABASE_URI is not provided it will be automatically set to SQLALCHEMY_DATABASE_URI + '_test' suffix

## Migrations
Project uses alembic to manage migrations script
http://alembic.zzzcomputing.com/en/latest/

### Example usage 
Add new migrations with
```
alembic revision --autogenerate -m "migration name"
```
Upgrade your database with
```
alembic upgrade head
```

## Tests
Put your tests into tests module.
Run your tests with
```
python -m pytest
```

## TODO
- Dockerfile
- Example project on side brach
- Turn sqlalchemy connection into library and release it on pip
