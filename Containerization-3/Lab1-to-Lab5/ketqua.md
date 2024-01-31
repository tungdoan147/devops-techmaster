# Containerization-3

## Lab 1. Cài đặt docker-compose

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled.png)

 

## Lab 2. Simple App with Docker Compose

### Bước 1: Tạo compose file

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%201.png)

### **Bước 2: Triển khai các dịch vụ trong compose file**

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%202.png)

### **Bước 3: Kiểm tra các container được tạo ra từ compose**

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%203.png)

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%204.png)

### **Bước 4: Xóa compose**

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%205.png)

## Lab 3. Viết compose file và triển khai ứng dụng Jav Spring Boot

### Chuẩn bị

Clone project

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%206.png)

Check out sang nhánh compose

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%207.png)

### **Cách 1. Triển khai compose với image tạo trước**

1. **Viết Docker Compose file**

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%208.png)

1. **Triển khai compose** 

Build

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%209.png)

Docker compose up

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2010.png)

1. **Kiểm tra kết quả**

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2011.png)

1. **Stop triển khai compose**

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2012.png)

### **Cách 2. Triển khai compose với option build image**

1. **Tạo compose file** 

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2013.png)

1. **Thực hiện triển khai compose**

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2014.png)

1. **Kiểm tra kết quả** 

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2015.png)

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2016.png)

## Lab 4. Triển khai ứng dụng Obo

**Triển khai ứng dụng** 

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2017.png)

**Liệt kê các service trong docker-compose file** 

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2018.png)

**Lệnh gỡ bỏ các service trong docker-compose file** 

![Untitled](Containerization-3%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2019.png)