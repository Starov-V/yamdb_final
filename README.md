![Workflow status](https://github.com/Starov-V/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
# Api_yamdb
##### Description
Main function of api_yamdb is adding reviews of works. Works have some properties, like genre. Also api_yamdb has system of comments, which users can add to any review. In Yamdb`s community you should be polite.
# .env file
```
DB_ENGINE=<specify your DBMS>
DB_NAME=<name of your database>
POSTGRES_USER=<login to connect to the database>
POSTGRES_PASSWORD=<password to connect to the database>
DB_HOST=<name of service>
DB_PORT=<port to connect to the database>
```
# How to launch

1. Clone image api_yamdb from ```DockerHub``` with command ```docker run <api_yamdb_image>```
2. Open Docker Desktop
3. In directory ```.../infra_sp2/infra``` type command ```docker-compose up``` in bash console
4. Make migrations with command ```docker-compose exec web python manage.py migrate```
5. Make superuser with command ```docker-compose exec web python manage.py createsuperuser```
6. Collect static with command ```docker-compose exec web python manage.py collectstatic --no-input```
7. Load data from fixtures with command ```loaddata <name_db>.json```
8. Enjoy :)
9. If you need close click ```Ctrl + C```

# Examples
```get``` /titles/ - get all works
```
{
"count": 0,
"next": "string",
"previous": "string",
"results": []
}
```

```post``` /titles/ - add work
```
{
"name": "string",
"year": 0,
"description": "string",
"genre": [],
"category": "string"
}
```

```get``` /titles/{titles_id}/ - get advanced info about work
```
{
"id": 0,
"name": "string",
"year": 0,
"rating": 0,
"description": "string",
"genre": [],
"category": {}
}
```

```patch``` /titles/{titles_id}/ - partial updating of information about the work
```
{
"name": "string",
"year": 0,
"description": "string",
"genre": [],
"category": "string"
}
```

```delete``` /titles/{titles_id}/ - delete work
# Some words from author
This is last work before my graduated work. README file today is props. You can look on the top of file. That`s all.