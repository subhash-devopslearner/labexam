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