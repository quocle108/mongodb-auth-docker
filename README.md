# docker-mongo-auth
A Docker Image for MongoDB which makes it easy to create an Admin, a Database and a Database User when the container is first launched.
# Build Image
  ```
  docker image build -t mongo-auth:1.0 .

  ```

# Run
  
- With docker-compose.yml
  ```
  services:
    db:
      image: mongo-auth:1.0
      environment:
        - AUTH=yes
        - MONGODB_ADMIN_USER=admin
        - MONGODB_ADMIN_PASS=admin123
        - MONGODB_APPLICATION_DATABASE=sample
        - MONGODB_APPLICATION_USER=testuser
        - MONGODB_APPLICATION_PASS=testpass
      ports:
        - "27017:27017"
  // run command
  ```

- With command line
  ```
  docker run -it \
    -e AUTH=yes \
    -e MONGODB_ADMIN_USER=admin \
    -e MONGODB_ADMIN_PASS=adminpass \
    -e MONGODB_APPLICATION_DATABASE=mytestdatabase \
    -e MONGODB_APPLICATION_USER=testuser \
    -e MONGODB_APPLICATION_PASS=testpass \
    -p 27017:27017 songmai108/mongo-auth
  ```

Find the image on Docker Cloud @ https://hub.docker.com/repository/docker/songmai108/mongo-auth
