# 1. SSH là gì?
SSH ( tên tiếng anh là Secure Shell) được hiểu là giao thức kết nối giữa máy khách và máy chủ điều khiển từ xa cho phép người sử dụng chỉnh sửa và kiểm soát server từ xa nhưng vẫn đảm bảo được an toàn. Server sẽ không bao giờ bị đánh cắp thông tin được truyền đi giữa máy chủ và máy tính nếu sử dụng SSH để kết nối vps. Giao thức SSL và SSH đều mã hoá đường truyền dữ liệu. Người dùng có khả năng sử dụng để chuyển tập tin, chạy chương trình, chuyển tiếp khác kết nối TCP / IP bằng đường truyền đã được bảo mật. 
SSH có thể tham chiếu cả tới giao thức mạng mã hóa và tới bộ tiện ích thực hiện giao thức đó. SSH sử dụng mô hình client-server, kết nối một ứng dụng client shell bảo mật, điểm kết thúc mà tại đó phiên được hiển thị, với một máy chủ SSH, điểm kết thúc mà tại đó phiên hoạt động.
Phiên bản SSH đầu tiên xuất hiện vào năm 1995 và được thiết kế bởi Tatu Ylönen, một nhà nghiên cứu tại Đại học Công nghệ Helsinki, người đã thành lập SSH Communications Security. Theo thời gian, các lỗi khác nhau đã xuất hiện trong SSH-1 và nó đã trở nên lỗi thời. Bộ giao thức Secure Shell hiện tại là SSH-2 và được coi là tiêu chuẩn trong năm 2006. Nó không tương thích với SSH-1 và sử dụng Diffie-Hellman key exchange và kiểm tra tính toàn vẹn mạnh hơn (sử dụng mã xác thực qua tin nhắn) để cải thiện bảo mật. Máy khách và máy chủ SSH có thể sử dụng một số phương pháp mã hóa, chủ yếu là AES và Blowfish.

Tuy nhiên, không có lỗ hổng khai thác được tìm thấy trong SSH2, mặc dù theo nguồn thông tin rò rỉ bởi Edward Snowden vào năm 2013, Cơ quan An ninh Quốc gia có thể giải mã một số lưu lượng truy cập SSH.
# Những công dụng tiêu biểu của giao thức SSH
Giao thức được sử dụng trong các mạng công ty để:

Cung cấp quyền truy cập an toàn cho người dùng và quy trình tự động
Chuyển các file tương tác và tự động
Phát lệnh từ xa
Quản lý cơ sở hạ tầng mạng và các thành phần hệ thống giữ nhiệm vụ quan trọng khác.
# Giao thức SSH hoạt động như thế nào?
Giao thức hoạt động trong mô hình client-server, có nghĩa là kết nối được thiết lập bởi máy khách SSH kết nối với máy chủ SSH. Máy khách SSH điều khiển quá trình thiết lập kết nối và sử dụng mã hóa khóa công khai để xác minh danh tính của máy chủ SSH. Sau giai đoạn thiết lập, giao thức SSH sử dụng các thuật toán mã hóa đối xứng mạnh và các thuật toán hash để đảm bảo quyền riêng tư và tính toàn vẹn của dữ liệu được trao đổi giữa máy khách và máy chủ.
Hình bên dưới trình bày một luồng thiết lập đơn giản của kết nối shell an toàn.
![image](https://user-images.githubusercontent.com/101684058/158929006-06d2dc60-87b9-4e55-950a-941c00961f57.png)

# Tính xác thực mạnh mẽ với các khóa SSH
Có một số tùy chọn có thể được sử dụng để xác thực người dùng. Những tùy chọn phổ biến nhất là mật khẩu và xác thực khóa công khai.

Phương thức xác thực khóa công khai được sử dụng chủ yếu cho tự động hóa và đôi khi bởi các quản trị viên hệ thống để đăng nhập một lần. Nó đã được sử dụng rộng rãi hơn nhiều so với những gì công chúng đã từng dự đoán. Ý tưởng là có một cặp khóa mã hóa - khóa công khai và khóa riêng tư - và định cấu hình khóa công khai trên máy chủ để cho phép truy cập và cấp quyền cho bất kỳ ai có bản sao của khóa riêng tư có thể truy cập vào máy chủ. Các khóa được sử dụng để xác thực được gọi là khóa SSH. Xác thực khoá công khai cũng được sử dụng với thẻ thông minh, chẳng hạn như thẻ CAC và PIV được chính phủ Hoa Kỳ sử dụng.
Công dụng chính của khóa xác thực là kích hoạt tự động hóa an toàn. Tự động chuyển file shell an toàn được sử dụng để tích hợp liền mạch các ứng dụng và cũng được dùng cho các hệ thống tự động và quản lý cấu hình.

Như các bạn có thể thấy, các tổ chức lớn có nhiều khóa SSH hơn là họ tưởng tượng và việc quản lý các khóa SSH trở nên rất quan trọng. Khóa SSH cấp quyền truy cập giống như việc cấp quyền truy cập thông qua tên người dùng và mật khẩu. Chúng yêu cầu một quy trình bắt đầu và kết thúc tương tự.

Trong một số trường hợp, chúng ta sẽ tìm thấy vài triệu khóa SSH cho phép truy cập vào các máy chủ sản xuất trong môi trường khách hàng, với 90% các khóa thực sự không được sử dụng và đại diện cho quyền truy cập đã được cấp phép nhưng không bao giờ bị chấm dứt. Đảm bảo các chính sách, quy trình và kiểm toán phù hợp để sử dụng SSH là rất quan trọng đối với việc quản lý danh tính và quyền truy cập phù hợp. Các dự án quản lý danh tính truyền thống đã bỏ qua tới 90% tất cả thông tin đăng nhập, thông qua việc bỏ qua các khóa SSH. Các dịch vụ và công cụ để thực hiện quản lý khóa SSH cũng được cung cấp.

# SH cung cấp tính năng mã hóa và bảo vệ tính toàn vẹn mạnh mẽ
Khi kết nối đã được thiết lập giữa máy khách và máy chủ SSH, dữ liệu được truyền đi sẽ được mã hóa theo các tham số được thương lượng trong quá trình thiết lập. Trong quá trình đàm phán, máy khách và máy chủ đồng ý về thuật toán mã hóa đối xứng được sử dụng và tạo khóa mã hóa sẽ được sử dụng. Lưu lượng giữa các bên giao tiếp được bảo vệ bằng các thuật toán mã hóa mạnh theo tiêu chuẩn của ngành, như AES (Advanced Encryption Standard - Chuẩn mã hóa nâng cao), và giao thức SSH cũng bao gồm cơ chế đảm bảo tính toàn vẹn của dữ liệu được truyền bằng cách sử dụng thuật toán hash tiêu chuẩn, chẳng hạn như SHA -2 (Standard Hashing Algorithm).
