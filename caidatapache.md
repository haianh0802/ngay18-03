# Cài đặt Apache trên CentOS 7
Bước 1: Cài đặt Apache
Apache có sẵn trong kho lưu trữ CentOS mặc định nên việc cài đặt khá đơn giản. Để cài đặt Apache hãy chạy lệnh sau:

yum install httpd -y

 Bước 2: Khởi động Apache
 
Khi quá trình cài đặt hoàn tất, hãy bật và khởi động dịch vụ Apache bằng các lệnh sau:

systemctl enable httpd

systemctl start httpd


Để kiểm tra trạng thái của Apache hãy sử dụng lệnh sau:

systemctl status httpd


![image](https://user-images.githubusercontent.com/101684058/158985092-69775dad-249c-43a5-b195-3ac9b302387f.png)

 Bước 3: Cấu hình Firewalld (Nếu có)
Nếu các bạn sử dụng Firewalld để có thể truy cập được website các bạn sẽ cần mở port bằng các lệnh sau đây

![image](https://user-images.githubusercontent.com/101684058/158985405-5703a8c8-94db-43d1-9eef-a024379eeaed.png)

#  Quản lý Apache Service với systemctl
Để dừng Apache, dùng lệnh:

![image](https://user-images.githubusercontent.com/101684058/158985564-20ce0fab-72c9-402b-a8b9-f6eb6659a897.png)

Để khởi động Apache dùng lệnh:

![image](https://user-images.githubusercontent.com/101684058/158985656-b2f70e3a-f5ee-4fc8-8b6c-4899bda97a18.png)

Lệnh khởi động lại Apache

![image](https://user-images.githubusercontent.com/101684058/158985823-b810b6d0-cc1a-4fb3-a190-c56ed4719be6.png)


Tải lại dịch vụ Apache mỗi khi bạn thay đổi cấu hình:

![image](https://user-images.githubusercontent.com/101684058/158985919-95e51787-bb9a-4da5-8c72-0799e72a9f9b.png)

Nếu không muốn Apache tự động chạy mỗi khi khởi động lại VPS sử dụng lệnh sau:

![image](https://user-images.githubusercontent.com/101684058/158986065-217bca91-4e1d-4820-b5f2-c67e1d8fc367.png)

Nếu muốn Apache tự động chạy mỗi khi khởi động lại VPS sử dụng lệnh sau:

![image](https://user-images.githubusercontent.com/101684058/158986175-08dbe84b-62ee-4686-a78a-a3f4fa1371e0.png)


