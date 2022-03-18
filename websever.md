# Web server là gì?
Web server là máy chủ cài đặt các chương trình phục vụ các ứng dụng web. Webserver có khả năng tiếp nhận request từ các trình duyệt web và gửi phản hồi đến client thông qua giao thức HTTP hoặc các giao thức khác. Có nhiều web server khác nhau như: Apache, Nginx, IIS, … Web server thông dụng nhất hiện nay:
![image](https://user-images.githubusercontent.com/101684058/158930112-6673ea8d-2fb1-4c40-b7b0-5172c56cc23e.png)

# Web server hoạt động như thế nào?

![image](https://user-images.githubusercontent.com/101684058/158930156-88d5991d-3a9b-4336-928d-a3a12432c1c6.png)

1. Trình duyệt phân giải tên miền thành địa chỉ IP
Trình duyệt web của bạn trước tiên cần phải xác định địa chỉ IP nào mà tên miền topdev.vn trỏ về. Trình duyệt sẽ yêu cầu thông tin từ một hoặc nhiều máy chủ DNS (thông qua internet). Máy chủ DNS sẽ cho trình duyệt biết địa chỉ IP nào tên miền sẽ trỏ đến cũng là nơi đặt trang web.

Lúc này trình duyệt web đã biết địa chỉ IP của trang web, nó có thể yêu cầu URL đầy đủ từ webserver.

2. Webserver gửi lại client Trang được yêu cầu
Web server phản hồi bằng cách gửi lại những thông tin client yêu cầu… Nếu trang không tồn tại hoặc có lỗi khác xảy ra, nó sẽ gửi lại thông báo lỗi thích hợp.

3. Trình duyệt hiển thị trang web
Trình duyệt web của bạn nhận lại được các tập tin html css (nhiều file khác)… và render hiển thị trang theo yêu cầu.
# Giới thiệu một số Web Server phổ biến
### Apache HTTP server
Apache là web server được sử dụng rộng rãi nhất thế giới. Apache được phát triển và duy trì bởi một cộng đồng mã nguồn mở dưới sự bảo trợ của Apache Software Foundation. Apache được phát hành với giấy phép Apache License là được sử dụng tự do, miễn phí.

Tính đến tháng 8 năm 2018, apache ước tính phục vụ cho 54.2% các trang web đang hoạt động và 53.3% số máy chủ hàng đầu. Apache chạy trên các hệ điều hành như windows, linux, unix, MacOS ….

### Nginx
Nginx là một web server nhẹ (Đọc thêm Nginx là gì), không chiếm nhiều tài nguyên của hệ thống. Nginx còn là một reserse proxy mã nguồn mở. Nginx khá là ổn định, cấu hình đơn giản và hiệu suất cao.

Nginx được phát triển bởi Igor Sesoev vào năm 2002 chủ yếu là để phục vụ cho website rambler.ru (trang web được truy cập nhiều thứ hai của nước Nga). Theo thống kê của Netcaft, trong một triệu website lớn nhất thế giới có 6.52% sử dụng Nginx.

Nginx là phần mềm mã nguồn mở và miễn phí, được phát hành rộng rãi theo giấy phép BSD. Nginx được phát triển bằng ngôn ngữ  và chạy được trên các hệ điều hành như Linux, FreeBSD, Windows, MacOS…

Nginx có các tính năng như chứng thực người dùng, virtual hosting, hỗ trợ CGI, FCGI, SCGI, WCGI, SSI, ISAPI, HTTPS, Ipv6, …

### Internet Information Services (IIS)
IIS do Microsoft phát triển, sản phẩm này được tích hợp cùng với hệ điều hành Windows Server. Trong IIS bao gồm nhiều dịch vụ như: dịch vụ Web Server, dịch vụ FTP Server. Tính đến thời điểm tháng 5 năm 2015 thì thì số lượng trang Web sử dụng máy chủ IIS gần 248 triệu trang web.

Tất cả các tính năng của web server được quản lí độc lập do đó chúng ta có thể dễ dàng thêm, loại bỏ hoặc thay thế các tính năng của web server.

Nhờ được tích hợp ASP.NET IIS có thể sử dụng toàn bộ sức mạnh của ASP.NET. Module ASP.NET làm cho máy chủ phát triển nhanh chóng nhờ vào giao diện quen thuộc và các dịch vụ ứng dụng của ASP.NET.

### Apache Tomcat
Apache Tomcat là một Java Servlet được phát triển bởi Apache Software Foundation. Tomcat thực thi các ứng dụng Java Servlet và JavaServer Pages (JSP). Tomcat cung cấp một máy chủ HTTP cho ngôn ngữ Java thuần túy.

Apache Tomcat rất ổn định và có tất cả các tính năng của một ứng dụng web thương mại nhưng đi kèm theo giấy phép mã nguồn mở của Apache. Tomcat cũng cung cấp một số chức năng bổ sung như tomcat manager application, speciallized realm imlementation và tomcat valves.

Các phiên bản của apache tomcat trùng với phiên bản và đặc điểm kỹ thuật của servlet java hoặc java servlet API. Tomcat 5.5X hỗ trợ Servlet API 2.3, tomcat 6.0X hỗ trợ servlet API 2.4 và tomcat 7.0 hỗ trợ servlet API 3.0. Ngoài Servlet versions API, phiên bản tomcat hỗ trợ phiên bản JSP API tương ứng.

Apache Tomcat hỗ trợ các hệ điều hành như windows, linux, MacOS, BSD,…

### Lighttpd
Lighttpd là một phần mềm mã nguồn mở, an toàn và linh hoạt, đặc biệt miễn phí và được phân phối theo giấy phép BSD. Lighttpd được viết bởi Jan Kneschke. Lighttpd chiếm ít tài nguyên, memory thấp, CPU nhỏ. Lighttpd được phát triển bằng ngôn ngữ C. chạy trên hệ điều hành Linux, Windows, Mac OS,…
