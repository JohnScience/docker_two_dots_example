# Weird behavior with "../../" in path

I want to have separate directories for the frontend, for the backend, and maybe for the app. Each of them deserves a separate `Dockerfile`. When I tried to follow the recommendation from [Stack Overflow, "Docker: Multiple Dockerfiles in project"](https://stackoverflow.com/questions/27409761/docker-multiple-dockerfiles-in-project), I got the following error:

```text
C:\Users\USER\Documents\github\docker_two_dots_example\docker\front>docker build -t front .
[+] Building 0.8s (6/6) FINISHED                                                                                                 docker:default
 => [internal] load build definition from Dockerfile                                                                                       0.0s
 => => transferring dockerfile: 130B                                                                                                       0.0s
 => [internal] load .dockerignore                                                                                                          0.0s
 => => transferring context: 2B                                                                                                            0.0s
 => CANCELED [1/3] RUN mkdir /app                                                                                                          0.7s
 => [internal] load build context                                                                                                          0.0s
 => => transferring context: 2B                                                                                                            0.0s
 => CACHED [2/3] WORKDIR /app                                                                                                              0.0s
 => ERROR [3/3] COPY ../../front/package.json ./                                                                                           0.0s
------
 > [3/3] COPY ../../front/package.json ./:
------
Dockerfile:7
--------------------
   5 |     WORKDIR /app
   6 |
   7 | >>> COPY ../../front/package.json ./
   8 |
--------------------
ERROR: failed to solve: failed to compute cache key: failed to calculate checksum of ref 2b316384-fb2f-4c68-a84d-2372c5e110e6::36lybkymhzvjn2qstmm47fcte: "/front/package.json": not found

C:\Users\USER\Documents\github\docker_two_dots_example\docker\front>
```
