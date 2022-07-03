# Build and host React APP in docker container

***STEPS***

- Build an image with custon name
    ```dockerfile
          docker image build -t myreact:latest .
    ```
- Run Container based on created image
    ```dockerfile
        docker container run -d -p 8082:80 --name react-prod  myreact:latest
    ```
