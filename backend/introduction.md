## Internet
- Internet là hệ thống mạng kết nối các thiết bị điện tử và mạng máy tính trên toàn thế giới, cho phép chúng ta có thể truyền tải và chia sẻ thông tin một cách nhanh chóng, hiệu quả.
- Internet truyền thông tin theo kiểu nối chuyển gói dữ liệu (packet switching) dựa trên một giao thức liên mạng đã được chuẩn hóa (giao thức IP).

## HTTP
- HTTP (Hypertext Transfer Protocol) là giao thức nền tảng giúp trình duyệt và máy chủ giao tiếp với nhau trên Internet.
- HTTP hoạt động theo mô hình yêu cầu – phản hồi (Request – Response). Trình duyệt gửi yêu cầu đến máy chủ, sau đó máy chủ xử lý và trả về kết quả cho người dùng.
- HTTP có thể truyền tải nhiều loại dữ liệu khác nhau như văn bản HTML, hình ảnh, video, tệp tin và dữ liệu API ở định dạng JSON
- HTTPS (Hypertext Transfer Protocol Secure) là phiên bản bảo mật của giao thức HTTP, được sử dụng để truyền tải dữ liệu an toàn trên Internet. Giao thức này hoạt động dựa trên chứng chỉ SSL/TLS, giúp mã hóa toàn bộ thông tin trao đổi giữa trình duyệt và máy chủ.
- Quy trình hoạt động của HTTPS :
  - Người dùng truy cập website bằng địa chỉ bắt đầu với HTTPS
  - Trình duyệt gửi yêu cầu xác minh và nhận chứng chỉ SSL/TLS từ máy chủ
  - Máy chủ phản hồi bằng chứng chỉ SSL kèm theo khóa công khai
  - Trình duyệt sử dụng khóa công khai để mã hóa khóa phiên và gửi lại cho máy chủ
  - Máy chủ giải mã, xác nhận khóa phiên và phản hồi lại cho trình duyệt
  - Sau khi xác thực thành công, hai bên sử dụng khóa phiên để trao đổi dữ liệu an toàn
