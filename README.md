# api_yamdb
![yamdb_workflow](https://github.com/Contrigra/yamdb_final/workflows/yamdb_workflow/badge.svg)

**REST API** for **YaMDb** service - *movie, book* and *music* reviews
 database. Team project of [Praktikum  students by Yandex](https://praktikum.yandex.ru/)



## Docker Instructions
*All of the following commands should be made directly from the project folder*

### Starting docker-compose:
```
docker-compose up
```
### First Start Tutorial
**For the first launch**, since we're taking a clear PostgreSQL image, we
 need to make our Django models into the database schema. 
 
 More: https://docs.djangoproject.com/en/3.1/topics/migrations/: 
```
docker-compose exec web python manage.py migrate
```
**Command to create a supersuer**
```
docker-compose exec web python manage.py createsuperuser
```
**Load fixtures, to test proper DB work:**
```
docker-compose exec web python manage.py loaddata fixtures.json
```
**If you obtain the ```the input device is not a TTY``` error**, please add to previous commands in the beginning ```winpty```

*Example:*
```
winpty docker-compose exec web python manage.py migrate
```

# API for YaMDb service allows to run the following functions:
For the more detailed information you can use the built-in api reference. 
 
To do so: 

* Start the project
* Open the api reference page in your browser: 
```
http://localhost:port/redoc/
```

### Reviews
* Get a list of all reviews;
* Create a new review. User may post only one review per object;
* Get a review by id;
* Partially update the review by id;
* Delete review by id.

### Comments
* Get a list of all comments to the review by id;
* Create a new comment for the review;
* Get a comment for a review by id;
* Partially update the comment on the review by id;
* Delete a comment to the review by id.

### Auth
* Getting a JWT token in exchange for email and confirmation_code;
* Sending confirmation_code to the email.

### Users
* Get a list of all users;
* Create an user;
* Get user by username;
* Change user data by username;
* Delete user by username;
* Get personal account details;
* Change the personal account details.

### Categories
* Get a list of all categories;
* Create a category;
* Delete a category.

### Genres
* Get a list of all genres;
* Create a genre;
* Delete a genre.

### Titles
* Get a list of all titles;
* Create an title for reviews;
* Get title information;
* Update title information;
* Delete title.


##Technology
###Dependencies
* django-filter
```
https://django-filter.readthedocs.io/en/stable/
```
* python-dotenv
```
https://pypi.org/project/python-dotenv/
```
* djangorestframework
```
https://www.django-rest-framework.org/
```
* django
```
https://www.djangoproject.com/
```
* djangorestframework-simplejwt
```
https://django-rest-framework-simplejwt.readthedocs.io/en/latest/
```
* gunicorn
```
https://docs.gunicorn.org/en/stable/
```
* psycopg2-binary
```
https://pypi.org/project/psycopg2-binary/
```
* PyJWT
```
https://pyjwt.readthedocs.io/en/stable/
```
* PyTZ
```
https://pypi.org/project/pytz/
```
###Database
* PostgreSQL 

    We used a clear image provided by DockerHub. 
  
 Official Documentation
 ```
https://www.postgresql.org/docs/
 ```

Image Link
```
https://hub.docker.com/_/postgres
```


##Authors

This is a group project of Yandex Praktikum students. 

Mikhail Gaponov
```
https://github.com/Contrigra
```

Dmitry Frolov
```
https://github.com/fd239
```

Aleksey Zverev
```
https://github.com/aleksizverev
```
