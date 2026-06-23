## LEMP Stack là gì?
- LEMP là tập hợp các công nghệ thường được sử dụng để xây dựng và triển khai ứng dụng web
- LEMP là viết tắt của Linux, Nginx, Mysql, PHP
- Quy trình xử lý:
     1. Người dùng gửi yêu cầu từ trình duyệt
     2. Nginx tiếp nhận yêu cầu
     3. Nếu là tệp tĩnh (CSS, JavaScript, hình ảnh), Nginx trả về trực tiếp
     4. Nếu là mã PHP, Nginx chuyển yêu cầu đến PHP-FPM
     5. PHP xử lý nghiệp vụ và truy vấn cơ sở dữ liệu
     6. Kết quả được trả về cho người dùng

- Ưu điểm của LEMP Stack
    * Hiệu năng cao
    * Tiết kiệm tài nguyên
    * Dễ mở rộng
    * Phù hợp với các ứng dụng có lượng truy cập lớn
## Tại sao cần Nginx?
Nginx là phần mềm máy chủ web và reverse proxy được thiết kế để xử lý đồng thời số lượng lớn kết nối với hiệu năng cao
Mọi yêu cầu từ người dùng đều đi qua Nginx trước khi được chuyển đến ứng dụng
- Vai trò của Nginx
   - Phục vụ nội dung tĩnh như HTML, CSS, JavaScript và hình ảnh
   - Chuyển tiếp yêu cầu đến ứng dụng thông qua cơ chế reverse proxy
   - Cân bằng tải giữa nhiều máy chủ
   - Xử lý chứng chỉ SSL/TLS và HTTPS
   - Thực hiện cache để tăng tốc độ phản hồi
   - Giới hạn truy cập và tăng cường bảo mật
- Lợi ích của Nginx
   - Giảm tải cho ứng dụng
   - Tăng tốc độ phản hồi
   - Hỗ trợ mở rộng hệ thống
   - Tối ưu tài nguyên

## Nginx khác gì Apache?
Apache có hệ sinh thái lâu đời, cấu hình linh hoạt và tương thích với nhiều ứng dụng cũ
Nginx mới hơn, được thiết kế để giải quyết bài toán hiệu năng và xử lý lượng truy cập lớn

Apache tạo một tiến trình hoặc luồng riêng cho mỗi kết nối => tốn RAM khi có nhiều ng truy cập cùng lúc
Nginx đc thiết kế để xử lý nhiều kết nối đồng thời => Nginx thường nhanh hơn và tiết kiệm tài nguyên hơn

Apache có thể khai báo các biến môi trường riêng thông qua cấu hình máy chủ. Trong một số trường hợp, các biến này được ưu tiên hơn giá trị trong file .env, khiến ứng dụng sử dụng cấu hình khác với mong đợi. Điều này không làm thay đổi nội dung file .env nhưng có thể gây nhầm lẫn khi triển khai và bảo trì hệ thống.

Apache không hỗ trợ http2 hiệu quả bằng nginx do http2 tận dụng tối đa cơ chế xử lý bất đồng bộ, trong khi đây lại là điểm mạnh của Nginx
Tóm lại, các hệ thống cũ thường sử dụng apache, đối với các hệ thống hiện đại, nginx được sử dụng nhiều hơn

## HTTP1 khác gì HTTP2?
http2 được phát triển nhằm khắc phục các hạn chế về hiệu năng của http1
http1 truyền dữ liệu dưới dạng văn bản và thường phải mở nhiều kết nối để tải toàn bộ nội dung của một trang web
http2 sử dụng định dạng nhị phân, cho phép gửi nhiều yêu cầu cùng lúc trên một kết nối duy nhất, đồng thời hỗ trợ nén header và Server Push.
Nhờ đó, http2 giúp giảm độ trễ, tăng tốc độ tải trang và tối ưu băng thông tốt hơn so với http1

##  VPS là gì?
VPS (Virtual Private Server) là máy chủ ảo được tạo ra bằng công nghệ ảo hóa trên một máy chủ vật lý
Mỗi VPS có:
- Hệ điều hành riêng
- CPU, RAM và dung lượng lưu trữ riêng
- Quyền quản trị độc lập

VPS khác gì máy chủ vật lý?

|            | VPS                       | Máy chủ vật lý             |
| -------------------- | ------------------------- | -------------------------- |
| Tài nguyên           | Chia sẻ từ máy chủ vật lý | Sử dụng toàn bộ tài nguyên |
| Chi phí              | Thấp                      | Cao                        |
| Khả năng mở rộng     | Linh hoạt                 | Hạn chế hơn                |
| Hiệu năng            | Tốt                       | Cao nhất                   |
| Thời gian triển khai | Nhanh                     | Lâu hơn                    |
| Quản trị             | Đơn giản                  | Phức tạp hơn               |
| Mức độ cô lập        | Cao                       | Hoàn toàn độc lập          |
