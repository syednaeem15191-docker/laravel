# mysql

#### `docker login -u ${DOCKER_USERNAME} -p ${DOCKER_PASSWORD}`

##### push laravel 9
* `docker-compose up --build -d laravel9`
* `docker tag mysql_laravel9 syednaeem15191/laravel:9`
* `docker push syednaeem15191/laravel:9`
* `docker tag mysql_mysql8 syednaeem15191/laravel:latest`
* `docker push syednaeem15191/laravel:latest`
* `docker-compose stop`
