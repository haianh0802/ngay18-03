# Các bước cài đặt IIS
1. Chạy Server Manager và nhấp vào Add roles and features .

 ![image](https://user-images.githubusercontent.com/101684058/158955776-dc096c31-7a90-4e3f-a07f-9a81249b4798.png)
 
 2. Nhấp vào nút Next .
 
 ![image](https://user-images.githubusercontent.com/101684058/158956038-fd40668f-0bd0-48da-aee1-00218f325b11.png)

3. Chọn Role-based or feature-based installation .

![image](https://user-images.githubusercontent.com/101684058/158957647-06b79428-a2e1-4542-849b-ed44d3552c30.png)

4.Chọn host bạn muốn thêm các service.\

![image](https://user-images.githubusercontent.com/101684058/158957896-199d9fb6-f88f-4914-be6f-849a3ffa69bf.png)

5.Tích vào hộp Web Server (IIS) 

![image](https://user-images.githubusercontent.com/101684058/158958107-3808fa59-b119-4edd-bcfa-2a09ca57691a.png)

6. Các tính năng bổ sung được yêu cầu để thêm IIS Server. Nhấp vào nút Add Features > Next 

![image](https://user-images.githubusercontent.com/101684058/158958323-70e3581f-1ed4-4125-9b59-98f8c97b7361.png)

7. Nhấp vào nút Next.

![image](https://user-images.githubusercontent.com/101684058/158958937-1fe69bca-9b80-4363-bbfb-0ca19a5dabf4.png)

8. Nhấp vào nút Next.

![image](https://user-images.githubusercontent.com/101684058/158959072-8948b602-4697-4e1c-9f11-28516bb5a19d.png)

9. Đây là phần chọn các tính năng của Web Server. Hãy chọn những tính năng mà bạn mong muốn thêm. Trong ví dụ này, các tùy chọn mặc định được giữ nguyên. Tất nhiên, bạn có thể thêm các tính năng này sau khi cài đặt IIS.

![image](https://user-images.githubusercontent.com/101684058/158959509-edd108f9-5ea4-4336-8107-1996fa9db62c.png)

10. Nhấp vào nút Install.

![image](https://user-images.githubusercontent.com/101684058/158959645-83bb101d-c2b7-4a78-818f-fb1fa90ee9e8.png)

11. Sau khi hoàn thành cài đặt, nhấp vào nút Close.

![image](https://user-images.githubusercontent.com/101684058/158959783-c5f5cd2a-36e3-4751-95a9-ce15a40d783a.png)

12. Chạy trình duyệt web và truy cập vào localhost , sau đó bạn cũng có thể xác minh IIS có đang chạy bình thường không.

![image](https://user-images.githubusercontent.com/101684058/158960122-4f72eeb4-6e1c-42c1-9185-78e766ef2abd.png)

# Sử dụng IIS trên Windows Server 2019
1. Chạy Powershell với quyền admin và cấu hình
2. Chạy Start > Server Manager và nhấp vào Tools > Internet Information Services (IIS) Manager

![image](https://user-images.githubusercontent.com/101684058/158963632-53864bb6-0294-44cd-98ec-917880463d38.png)

3. Mở các mục ở bảng điều khiển bên trái, Default Web Site được cấu hình.

![image](https://user-images.githubusercontent.com/101684058/158963939-38402c06-a4e6-4d15-a2c0-e242bb388118.png)

4. Chọn Default Web Site và nhấp vào Advanced Settings..., sau đó có thể xác nhận các cài đặt như Physical Path (Document Root), v.v...

![image](https://user-images.githubusercontent.com/101684058/158964264-f832db80-d398-4ac9-8093-045155a8b30b.png)

5. Mở Default Document, sau đó có thể xác nhận các tài liệu mặc định.

![image](https://user-images.githubusercontent.com/101684058/158965228-00a4d2ad-6e1e-46ef-a204-58e7eeec6cab.png)

6. Bạn có thể xem các tài liệu mặc định

![image](https://user-images.githubusercontent.com/101684058/158965321-16b4fd92-6a78-4e3d-a1b0-65a46572eb8e.png)

7. Tạo trang test trong Physical Path (Document Root) và xác minh quyền truy cập bằng trình duyệt web.

![image](https://user-images.githubusercontent.com/101684058/158965594-ab1f213b-4ac4-4215-98c2-f0aa92c26d2b.png)


![image](https://user-images.githubusercontent.com/101684058/158965849-ecc348ae-d256-409c-aedc-2e7f32b5e020.png)


