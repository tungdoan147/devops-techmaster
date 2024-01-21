# Containerization-1

### **Lab 5. Thao tác với Storage**

**Bind mount** 

```bash
docker run --name bind-centos -itd -v /opt/docker_host_folder:/opt/mount_point centos
Unable to find image 'centos:latest' locally
latest: Pulling from library/centos
a1d0c7532777: Pull complete 
Digest: sha256:a27fd8080b517143cbbbab9dfb7c8571c40d67d534bbdee55bd6c473f432b177
Status: Downloaded newer image for centos:latest
4f3b507302dab74bb9988581df03c72dd0598a12add25126c8d87eaaf1495125
root@ubuntu:/home/tungnd# docker ps 
CONTAINER ID   IMAGE     COMMAND       CREATED          STATUS         PORTS     NAMES
4f3b507302da   centos    "/bin/bash"   11 seconds ago   Up 9 seconds             bind-centos
```

Ghi nội dung vào thư mục /opt/mount_point của container:

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled.png)

Kiểm tra file được mount ra ngoài

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%201.png)

Ngược lại thêm mới nội dung trên file ở thư mục đã mount ra từ container /opt/docker_host_folder

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%202.png)

Kiểm tra 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%203.png)

**Volume mount** 

Run container

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%204.png)

Ghi file vào container 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%205.png)

Kiểm tra tập tin trong centos_volume

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%206.png)

**Quản trị Volume**

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%207.png)

**Luyện tập** 

1. Khởi chạy ứng dụng CSDL mongo 

```bash
docker run -itd --name mongo -e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=VRuAd2Nvmp4ELHh5 \
-e MONGO_INITDB_DATABASE=test \
-v /home/tungnd/test1:/data/db mongo:6-jammy
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%208.png)

1. Sử dụng Docker Volume

```bash
docker run -itd --name mongo -e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=VRuAd2Nvmp4ELHh5 \
-e MONGO_INITDB_DATABASE=test \
-v tungnd-test:/data/db mongo:6-jammy
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%209.png)

1. Mysql với  init schema

Chạy lệnh sau khi cop nội dung file init.sql 

```bash
docker run -itd --name mysql-exist -e MYSQL_ROOT_PASSWORD=admin123 \
-e MYSQL_DATABASE=bigstore \
-v /home/tungnd/test1/init.sql/docker-entrypoint-initdb.d/init.sql \
-v bigstore_db:/var/lib/mysql mysql:5.6
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2010.png)

Kiểm tra trong container  (Đã có tables bigstore)

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2011.png)

Liệt kê volume (đã có volume bigstore_db)

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2012.png)

### **Lab 6. Thao tác với Network**

**Bridge Network**

1. Xem danh sách network 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2013.png)

1. Tạo mới nw mới sử dụng driver bridge

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2014.png)

1. Kiểm tra thông tin chi tiết nw

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2015.png)

1. Thêm container vào nw

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2016.png)

1. Gỡ container ra khỏi nw

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2017.png)

1. Chỉ định nw khi tạo container 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2018.png)

1. Mapping port 

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2019.png)

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2020.png)

**Host Network**

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2021.png)

**Luyện tập** 

Sau khi tạo file tạo network dashy-net

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2022.png)

Chạy lệnh 

```bash
docker run -itd --name my-dashboard \
--network dashy-net \
-p 4000:80 \
-v bigstore_db:/var/lib/mysql --restart always lissy93/dashy:latest 
```

![Untitled](Containerization-1%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2023.png)

Ở đây mình dùng --restart=always không được mà phải dùng --restart always