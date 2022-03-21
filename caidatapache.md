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

# Tạo folder virtual server
Tạo folder html cho haianh.com như sau, sử dụng flag -p để tạo folder cần thiết:

sudo mkdir -p /var/www/haianh.com/html

Lập một folder bổ sung để lưu trữ file log cho trang web:

sudo mkdir -p /var/www/haianh.com/log

Tiếp theo, chỉ định quyền sở hữu folder html với biến $USER:

sudo chown -R $USER:$USER /var/www/haianh.com/html

Đảm bảo rằng web của bạn có quyền mặc định.

sudo chmod -R 755 /var/www

Tiếp theo, tạo một trang index.html mẫu bằng vi hoặc trình soạn thảo:

sudo vi /var/www/haianh.com/html/index.html

Nhấn i để chuyển sang chế độ INSERT và thêm HTML mẫu vào file:

/var/www/haianh.com/html/index.html

<html>
  <head>
    <title>Welcome to haianh.com!</title>
  </head>
  <body>
    <h1>   PHAM HAI ANH  </h1>
  </body>
</html>

lưu và đóng file bằng cách nhấn ESC, nhập :wq và nhấn ENTER.

Trước khi tạo virtual server, cần tạo một directiry sites-available để lưu trữ chúng. Ngoài ra, bạn cũng cần tạo một directory sites-enabled. Directoiry này sẽ chứa các symbolic link cho các virual host mà ta muốn publish. Tạo cả hai directiry này bằng lệnh sau:

sudo mkdir /etc/httpd/sites-available /etc/httpd/sites-enable


Tiếp theo, yêu cầu Apache tìm kiếm các virtual server trong directory sites-enabled. Để thực hiện điều này, hãy chỉnh sửa file cấu hình chính của Apache. Sau đó thêm một dòng khai báo directory cho các file cấu hình bổ sung:

sudo vi /etc/httpd/conf/httpd.conf

Thêm dòng này vào cuối file:

IncludeOptional sites-enabled/*.conf

Lưu và đóng file khi đã hoàn tất việc thêm dòng đó vào. Bây giờ các directory virtual server đã được tạo. Tiếp theo là tạo file virtual host.

# Tạo file virtual host
Đầu tiên tạo một file mới trong directory sites-available:

sudo vi /etc/httpd/sites-available/haianh.com.conf

Thay đổi miền haianh.com thành tên miền của bạn:

/etc/httpd/sites-available/example.com.conf


<VirtualHost *:80>
    ServerName www.haianh.com
    ServerAlias haianh.com
    DocumentRoot /var/www/haianh.com/html
    ErrorLog /var/www/haianh.com/log/error.log
    CustomLog /var/www/haianh.com/log/requests.log combined
</VirtualHost>

Thao tác này sẽ cho Apache biết nơi tìm root – lưu giữ các tài liệu web mà có thể được truy cập công khai. Ngoài ra, nói cũng cho biết nơi lưu trữ lỗi và request log cho trang web.

Lưu và đóng file khi hoàn tất.

Bây giờ đã tạo các file virtual host. Hãy kích hoạt chúng để Apache biết để phục vụ cho khách truy cập. Để làm việc này, hãy tạo một liên kết cho virtual host trong directory site-enabled:

sudo ln -s /etc/httpd/sites-available/haianh.com.conf 
/etc/httpd/sites-enabled/haianh.com.conf

Bây giờ, virtual host đã được cấu hình và sẵn sàng cung cấp nội dung. Trước khi khởi động lại Apache, hãy đảm bảo rằng SELinux có các chính sách phù hợp cho virtual host của bạn. Tiếp theo, hãy điều chỉnh quyền của SELinux để tiếp tục việc cài đặt web server trên CentOS 7.

# Điều chỉnh các chính sách Apache
Việc đặt chính sách Apache trên phạm vi rộng sẽ yêu cầu SELinux xử lý các quy trình bằng cách sử dụng boolean httpd_unified. Mặc dù cách tiếp cận này thuận tiện, nhưng nó không cung cấp cho bạn mức độ kiểm soát giống như tiếp cận vào file hay directory.

Chạy lệnh sau để đặt một chính sách Apache chung:

sudo setsebool -P httpd_unified 1
Bash
Lệnh setsebool thay đổi giá trị boolean của SELinux. Flag -P sẽ cập nhật giá trị boot-time. Điều này làm các thay đổi vẫn giữ nguyên sau các lần khởi động lại. httpd_unified là boolean yêu cầu SELinux xử lý tất cả các quy trình thuộc cùng một loại. Vì vậy hãy bật nó với giá trị là 1.

# Điều chỉnh chính sách Apache trên directory
Việc đặt riêng các quyền SELinux cho directory /var/www/haianh.com/log sẽ cung cấp nhiều quyền kiểm soát hơn, nhưng cũng yêu cầu bảo trì nhiều hơn. Vì việc này khác với việc đặt chính sách chung, nên ta cần set các loại context một cách thủ công, cho từng log directory mới trong cấu hình của virtual host.

Đầu tiền kiểm tra context type mà SELinux đã cung cấp cho directory /var/www/haianh.com/log:

sudo ls -dZ /var/www/haianh.com/log/

Lệnh này liệt kê và in cotext SELinux của directory. Bạn sẽ thấy output như sau:

Output
drwxr-xr-x. root root unconfined_u:object_r:httpd_sys_content_t:s0 /var/www/haianh.com/log/

Context hiện tại là httpd_sys_content_t. Điều này cho SELinux biết Apache chỉ có thể đọc các file được tạo trong directory này. Trong hướng dẫn này, bạn sẽ thay đổi context type của directory /var/www/haianh.com/log thành httpd_log_t. Nó cho phép Apache tạo và nối các file log ứng dụng web lại với nhau:

sudo semanage fcontext -a -t httpd_log_t "/var/www/haianh.com/log(/.*)?"

Tiếp theo, sử dụng lệnh restorecon để áp dụng các thay đổi này và để chúng tồn tại qua các lần khởi động lại:

sudo restorecon -R -v /var/www/haianh.com/log

Flag -R chạy lệnh theo quy tắc đệ quy. Nghĩa là nó sẽ cập nhật mọi file hiện có thể sử dụng context mới. Flag -v sẽ in ra các thay đổi về context mà lệnh thực hiện. Kết quả:

Output

restorecon reset /var/www/haianh.com/log context unconfined_u:object_r:httpd_sys_content_t:s0->unconfined_u:object_r:httpd_log_t:s0

Hãy liệt kê các ngữ cách một lần nữa để xem các thay đổi:

sudo ls -dZ /var/www/haianh.com/log/

Output sẽ phản ánh các loại context được cập nhật:

Output
drwxr-xr-x. root root unconfined_u:object_r:httpd_log_t:s0 /var/www/haianh.com/log

Bây giờ directory /var/www/haianh.com/log đang sử dụng loại httpd_log_t. Hãy kiểm tra lại cấu hình virtual server của mình. Bước cuối cùng trong việc cài đặt web server trên CentOS 7 là kiểm tra lại virtual host.


# Kiểm tra Virtual Host
Khi SELinux context đã được cập nhật, Apache sẽ có thể ghi vào directory /var/www/haianh.com/log. Bây giờ bạn có thể khởi động lại Apache:

sudo systemctl restart httpd

Liệt kê content của directory /var/www/haianh.com/log để xem Apache có tạo các file hay không:

ls -lZ /var/www/haianh.com/log

Bạn sẽ thấy Apache có thể tạo file error.log và request.log, các file này đã được chỉ định trong cấu hình virtual host:

Output
-rw-r--r--. 1 root root 0 Feb 26 22:54 error.log
-rw-r--r--. 1 root root 0 Feb 26 22:54 requests.log

Bây giờ virtual host và các quyền SELinux đã được cập nhật. Apache sẽ phục vụ tên miền của bạn. Kiểm tra điều này bằng cách truy cập http://example.com, bạn sẽ thấy một thứ như sau:

PHAM HAI ANH

Điều này xác nhận virtual server đã được cấu hình thành công. Lặp lại bước 4 và 5 để tạo virtual host mới với quyền SELinux cho miền bổ sung. Sau đó kết thúc việc cài đặt web server trên CentOS 7.
