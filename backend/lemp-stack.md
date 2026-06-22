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

## 3. Nginx khác gì Apache?

| Tiêu chí                         | Nginx             | Apache                                  |
| -------------------------------- | ----------------- | --------------------------------------- |
| Kiến trúc xử lý                  | Event-driven      | Process/Thread-based                    |
| Khả năng xử lý kết nối đồng thời | Rất cao           | Tốt nhưng tiêu tốn nhiều tài nguyên hơn |
| Hiệu suất với nội dung tĩnh      | Rất tốt           | Tốt                                     |
| Hiệu suất với nội dung động      | Thông qua PHP-FPM | Hỗ trợ trực tiếp qua module             |
| Mức sử dụng bộ nhớ               | Thấp              | Cao hơn                                 |
| Tệp cấu hình                     | `nginx.conf`      | `.htaccess`, `httpd.conf`               |
| Hỗ trợ `.htaccess`               | Không             | Có                                      |
| Khả năng tùy biến                | Tốt               | Rất linh hoạt                           |

## HTTP/1.1 khác gì HTTP/2?
HTTP/2 được phát triển nhằm khắc phục các hạn chế về hiệu năng của HTTP/1.1

| Tiêu chí                          | HTTP/1.1          | HTTP/2    |
| --------------------------------- | ----------------- | --------- |
| Định dạng dữ liệu                 | Văn bản thuần túy | Nhị phân  |
| Số lượng yêu cầu trên một kết nối | Tuần tự           | Đồng thời |
| Multiplexing                      | Không hỗ trợ      | Có        |
| Header Compression                | Không             | Có        |
| Server Push                       | Không             | Có        |
| Hiệu suất tải trang               | Thấp hơn          | Cao hơn   |

### Hạn chế của HTTP/1.1

* Chỉ xử lý tuần tự trên một kết nối.
* Phát sinh nhiều kết nối TCP.
* Tăng độ trễ khi tải nhiều tài nguyên.

### Ưu điểm của HTTP/2

* Giảm thời gian tải trang.
* Tối ưu băng thông.
* Cải thiện trải nghiệm người dùng.
## 5. VPS là gì?
VPS (Virtual Private Server) là máy chủ ảo được tạo ra bằng công nghệ ảo hóa trên một máy chủ vật lý
Mỗi VPS có:
- Hệ điều hành riêng
- CPU, RAM và dung lượng lưu trữ riêng
- Quyền quản trị độc lập

## 6. VPS khác gì máy chủ vật lý?

| Tiêu chí             | VPS                       | Máy chủ vật lý             |
| -------------------- | ------------------------- | -------------------------- |
| Tài nguyên           | Chia sẻ từ máy chủ vật lý | Sử dụng toàn bộ tài nguyên |
| Chi phí              | Thấp                      | Cao                        |
| Khả năng mở rộng     | Linh hoạt                 | Hạn chế hơn                |
| Hiệu năng            | Tốt                       | Cao nhất                   |
| Thời gian triển khai | Nhanh                     | Lâu hơn                    |
| Quản trị             | Đơn giản                  | Phức tạp hơn               |
| Mức độ cô lập        | Cao                       | Hoàn toàn độc lập          |

### Khi nào nên sử dụng VPS?

* Website cá nhân.
* Blog và trang tin tức.
* Hệ thống thử nghiệm.
* Ứng dụng có lượng truy cập vừa và nhỏ.

### Khi nào nên sử dụng máy chủ vật lý?

* Hệ thống có lượng truy cập lớn.
* Ứng dụng yêu cầu hiệu năng cao.
* Dữ liệu nhạy cảm cần mức độ kiểm soát tối đa.


VPS là giải pháp cân bằng giữa chi phí và hiệu năng, phù hợp với nhiều loại ứng dụng web hiện nay, trong khi máy chủ vật lý đáp ứng tốt các hệ thống yêu cầu tài nguyên và khả năng kiểm soát cao.
