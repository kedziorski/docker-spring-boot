# docker-spring-boot
Spring Boot on Docker

This is simple "Hello World" Spring Boot app with Docker support.

## Useful links
- [Docker documentation](https://docs.docker.com/)
- [Dockerfile Maven Plugin (from Spottify)](https://github.com/spotify/dockerfile-maven)

## How to build & run
```
mvn install dockerfile:build
```
Maven will build Spring Boot application and after that will build Docker image (kedziorski/docker-spring-boot) based on Dockerfile.

#### Simple run
```
docker run -p 11000:11000 -t kedziorski/docker-spring-boot
```

#### Run with debug

```
docker run -e "JAVA_OPTS=-agentlib:jdwp=transport=dt_socket,address=5005,server=y,suspend=n" -p 11000:11000 -p 5005:5005 -t kedziorski/docker-spring-boot
```

After run
```
http://localhost:11000/
```
you should see "Hello Docker World" app response.
