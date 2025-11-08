# How to run LabExam Django project

## Using Docker commands

1. `git clone https://github.com/subhash-devopslearner/labexam.git`  
2. `cd labexam`  
3. `docker build -t labexam:v1 .`  
4. `docker run -d -p 8000:8000 labexam:v1`  
5. `Open http://localhost:8000` 
6. `docker stop contaner-name`          - (optional)  
7. `docker rm container-name`           - (optional)  
8. `docker image rm docker-image-name`  - (optional)    


## Using Docker Compose commands

1. `git clone https://github.com/subhash-devopslearner/labexam.git`  
2. `cd labexam`  
3. `docker compose up --build`  
4. `Open http://localhost:8000`  
5. `docker compose down`  

## Using Docker Compose with Django and Postgres DB

***Check for DB part in docker-compose.yml file***  
***Added package for postgres db, check requirements.txt***  

1. `git clone https://github.com/subhash-devopslearner/labexam.git`  
2. `cd labexam`  
3. `docker compose build`  
4. `docker compose up` 
5. `Open http://localhost:8000`   
6. `docker compose exec web python manage.py migrate`  
7. `docker compose exec web python manage.py createsupersuper`  
8. `Open http://localhost:8000/admin`  
9. `docker compose down`  
10. `docker compose down -v` - (optional, to delete docker mounted volume)    

## Using Docker Compose with Django and Postgres DB with .env

***Check for environment part in docker-compose.yml file***  
***In DB part, DB variables are read from .env and set using environment keyword as bash variables***
***Check for settings.py in labexam for django settings reading using .env***  
***Must add .env to .gitignore and .dockerignore files***

1. `git clone https://github.com/subhash-devopslearner/labexam.git`  
2. `cd labexam`  
3. `docker compose build`  
4. `docker compose up` 
5. `Open http://localhost:8000`   
6. `docker compose exec web python manage.py shell`    
7. `import os`  
8. `print(os.environ.get('DB_HOST'))`    
9. `docker compose down`  

```
python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"

Get secret key for Django using above command and save in .env file

Always put secret key inside '' (single quotes)
```

