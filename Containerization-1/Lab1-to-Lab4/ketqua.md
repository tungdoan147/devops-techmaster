# Containerization-1

### Lab1. Cài đặt Docker trên Ubuntu

Đã cài đặt Docker

docker infor

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled.png)

Thiết lập ra container 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%201.png)

Thêm được user các nhân vào group Docker 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%202.png)

### Lab2. Tạo tài khoản và khám phá Docker Hub

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%203.png)

### Lab3. Thao tác với images

```bash
docker image --help

Usage:  docker image COMMAND

Manage images

Commands:
  build       Build an image from a Dockerfile
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Display detailed information on one or more images
  load        Load an image from a tar archive or STDIN
  ls          List images
  prune       Remove unused images
  pull        Download an image from a registry
  push        Upload an image to a registry
  rm          Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

Run 'docker image COMMAND --help' for more information on a command.
```

1.  Liệt kê các danh sách Image

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%204.png)

1.  Pull Image

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%205.png)

```bash
docker pull openjdk
docker pull openjdk:23-ea-5-jdk-bookworm
docker pull node:latest
docker pull python:3.6 
docker pull python:3.9
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%206.png)

1. Tag images 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%207.png)

1. Push Images

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%208.png)

1. Save images

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%209.png)

1. Load images

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2010.png)

1. Delete images

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2011.png)

### Lab4. Thao tác với container

1. Tạo container từ image 

```bash
docker run nginx
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2012.png)

```bash
docker run -d -p 80:80 docker/getting-started
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2013.png)

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2014.png)

```bash
docker run -itd -e MYSQL_ROOT_PASSWORD=tungnd -v mysql_data:/var/lib/mysql --name mysql-4 -p 13307:3306 mysql:5.7
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2015.png)

1. Liệt kê các container

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2016.png)

1. Kiểm tra thông tin của container

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2017.png)

1. Kiểm tra log ứng dụng 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2018.png)

1. Truy cập vào trong container 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2019.png)

1. Trạng thái của container

Luyện tập 

Luyện tập 0:

```bash
docker run -d --name my-calculator -p 3000:3000 orezfu/calculator:v1
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2020.png)

```bash
docker ps 
CONTAINER ID   IMAGE                  COMMAND                  CREATED          STATUS          PORTS                                                    NAMES
901c10873a45   orezfu/calculator:v1   "docker-entrypoint.s…"   3 minutes ago    Up 3 minutes    0.0.0.0:3000->3000/tcp, :::3000->3000/tcp                my-calculator
cebbaca2fd0b   mysql:5.7              "docker-entrypoint.s…"   19 minutes ago   Up 19 minutes   33060/tcp, 0.0.0.0:13307->3306/tcp, :::13307->3306/tcp   mysql-4
```

Luyện tập 1: Chạy ứng dụng Java

```bash
docker run -d --name my-java-app -p 8000:8080 orezfu/java-app:v1
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2021.png)

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2022.png)

Luyện tập 2: Chạy ứng dụng mysql 

```bash
docker run -d --name mysql-tech -p 13336:3306 -v data_mysql_tech:/var/lib/mysql -e MYSQL_DATABASE=tungnd \
-e MYSQL_USER=tungnd \
-e MYSQL_PASSWORD=tungnd \
-e MYSQL_ROOT_PASSWORD=tungnd mysql:5.7
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2023.png)

```bash
docker ps
CONTAINER ID   IMAGE                  COMMAND                  CREATED          STATUS          PORTS                                                    NAMES
1ec57e5d6f07   mysql:5.7              "docker-entrypoint.s…"   23 seconds ago   Up 22 seconds   33060/tcp, 0.0.0.0:13336->3306/tcp, :::13336->3306/tcp   mysql-tech
15086bb7c375   orezfu/java-app:v1     "java -jar /app/app.…"   9 minutes ago    Up 9 minutes    0.0.0.0:8000->8080/tcp, :::8000->8080/tcp                my-java-app
901c10873a45   orezfu/calculator:v1   "docker-entrypoint.s…"   16 minutes ago   Up 16 minutes   0.0.0.0:3000->3000/tcp, :::3000->3000/tcp                my-calculator
cebbaca2fd0b   mysql:5.7              "docker-entrypoint.s…"   31 minutes ago   Up 31 minutes   33060/tcp, 0.0.0.0:13307->3306/tcp, :::13307->3306/tcp   mysql-4
```

Luyện tập 3: Xóa các container trong luyện tập 0,1,2

```bash
docker rm $(docker ps -a -q) -f 
1ec57e5d6f07
15086bb7c375
901c10873a45
cebbaca2fd0b
root@tungnd-MS-7B19:/home/tungnd#  docker ps 
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```