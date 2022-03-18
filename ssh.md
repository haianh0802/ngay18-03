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
