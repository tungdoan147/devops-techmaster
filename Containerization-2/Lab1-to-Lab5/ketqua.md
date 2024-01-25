# Containerization-2

## Lab 1: Build docker image cho Web tĩnh

### **Chuẩn bị**

- Clone source code về máy

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled.png)

- Test source code trên trình duyệt

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%201.png)

### **Xây dựng Image**

**Bước 1. Viết Dockerfile**

 

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%202.png)

**Bước 2. Build image từ Dockerfile**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%203.png)

**Bước 3. Kiểm tra image**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%204.png)

Đã có images slick

**Bước 4. Push image lên Docker Hub**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%205.png)

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%206.png)

### Thực thi tạo container từ image

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%207.png)

### Kết quả

1 Docker Image của Web Slick trên Docker Hub

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%208.png)

2 Kết quả chạy Web Slick trên Docker

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%209.png)

## **Lab 2 - Build Docker Image cho ứng dụng ReacJS**

### **Chuẩn bị**

- Clone source code về máy

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2010.png)

- Test source code, theo các bước mô tả trong [README.md](http://README.md)

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2011.png)

### Xây dựng Image

**Cách 1 - Dev Mode**

**Bước 1. Viết Dockerfile** 

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2012.png)

**Bước 2. Build Image từ dockerfile** 

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2013.png)

**Bước 3. Kiểm tra image**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2014.png)

Đã có images calculator

**Bước 4. Tạo container từ image**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2015.png)

Check trên trình duyệt 

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2016.png)

## Lab 3: Build docker image cho ứng dụng Java Springboot - 1 - Hello World

### Chuẩn bị

- Cài đặt môi trường Java trên Ubuntu

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2017.png)

- Clone source

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2018.png)

- Chạy lệnh

 

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2019.png)

- Kiểm tra

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2020.png)

- Đóng gói ứng dụng

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2021.png)

### Xây dựng Image

**Bước 1: Viết Dockerfile**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2022.png)

**Bước 2: Build Dockerfile tạo Image**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2023.png)

**Bước 3: Chạy container được sinh ra bởi Image**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2024.png)

Kiểm tra:

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2025.png)

**Bước 4: Push image lên Docker Hub**

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2026.png)

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2027.png)

Kiểm tra image trên Docker Hub

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2028.png)

## Lab 4: Build image cho ứng dụng Angular

  1. Clone source code về máy

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2029.png)

1. Thiết lập Dockerfile

```bash
FROM node:13-alpine AS builder
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx:1.17-alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
Chạy docker build image
```

1. Từ dockerfile build thành docker image có tên là angular-app

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2030.png)

1. Khởi động container 

```bash
docker run -itd -p 8081:80 --name tungnd angular-app
```

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2031.png)

1. Kiểm tra 

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2032.png)

## Lab 5: Build image cho ứng dụng Python

### Yêu cầu 1:

- Clone source code

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2033.png)

 

- Viết Dockerfile

```bash
FROM python:3.9-slim-buster
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . . 
EXPOSE 5000
ENV FLASK_APP="hello_flask.py"
ENTRYPOINT ["flask", "run", "--host", "0.0.0.0"]
```

- Build Image

```bash
docker build -t tungnd/flask:01 -f Dockerfile .
```

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2034.png)

- Khởi chạy

```bash
docker run -itd -p 5000:5000 tungnd/flask:01
```

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2035.png)

- Kiểm tra

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2036.png)

### Yêu cầu 2:

- Push image

```bash
docker tag tungnd/flask:01 312199/tungnd-flask01
docker push 312199/tungnd-flask01
```

[https://hub.docker.com/repository/docker/312199/tungnd-flask01/general](https://hub.docker.com/repository/docker/312199/tungnd-flask01/general)

![Untitled](Containerization-2%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2037.png)