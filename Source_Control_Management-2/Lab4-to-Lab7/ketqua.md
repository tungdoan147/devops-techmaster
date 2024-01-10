# Source Control Management - 2

## Lab4. Làm việc với tag và release trên GitHub

1. Tạo tag

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%201.png)

1. Xóa tag

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%202.png)

Đã xóa các tag v1.1.0 v1.2.0 

## Lab5. Thao tác Merge và Pull Request

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%203.png)

**Merge code**

1. Tạo commit trên nhánh staging

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%204.png)

2 Thực hiện merge code từ nhánh staging sang nhánh production 

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%205.png)

**Pull request**

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%206.png)

1. Tạo commit và push lên nhánh staging

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%207.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%208.png)

1. Tạo PR trên github

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%209.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2010.png)

1. Merge Pull Request 

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2011.png)

## Lab6. Xử lý conflict

  1. Tạo nhánh dev từ nhánh staging

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2012.png)

1. Tạo thay đổi trên nhánh staging

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2013.png)

1. Tạo thay đổi trên nhánh dev

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2014.png)

1. Thực hiện merge code từ staging vào dev

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2015.png)

1. Giải quyết conflict

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2016.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2017.png)

1. Merge code từ dev sang staging

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2018.png)

## Lab7. Khôi phục commit

**Git Reset**

1. Tạo các commit và đưa vào dòng lịch sử của Git

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2019.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2020.png)

1. Thực hiện reset về commit B

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2021.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2022.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2023.png)

1. Push thay đổi lên remote

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2024.png)

**Git Revert**

1. Chuẩn bị commit trong dòng lịch sử git

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2025.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2026.png)

1.  Thực hiện revert

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2027.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2028.png)

Revert ở commit C (revert về commit B) 

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2029.png)

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2030.png)

1. Push thay đổi lên remote

![Untitled](Source%20Control%20Management%20-%202%206efe6c1ea7f14b6f81c9c22814adab8d/Untitled%2031.png)