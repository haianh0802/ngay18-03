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
