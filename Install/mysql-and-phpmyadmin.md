# Hướng dẫn cài đặt MySQL và phpMyAdmin trên Docker
```
MySQL Community Edition là phiên bản có thể tải xuống miễn phí của cơ sở dữ liệu nguồn mở phổ biến nhất thế giới. Dựa theo giấy phép GPL và được hỗ trợ bởi một cộng đồng các nhà phát triển mã nguồn mở.
PhpMyAdmin là một công cụ phần mềm miễn phí viết bằng ngôn ngữ PHP nhằm cung cấp một giao diện để quản lý cơ sở dữ liệu MySQL hoặc MariaDB.
Docker là một nền tảng phần mềm được thiết kế để giúp tạo, triển khai và chạy các ứng dụng dễ dàng hơn.
```
Đầu tiên cúng ta sẽ tạo một Docker Network với tên sql nhằm mục đích khởi chạy Docker Container MySQL và phpMyAdmin trong network:
```
docker network create sql
```
# Thực hiện lần lượt các lệnh sau đây sẽ khởi tạo MySQL Container trên Docker. Trước tiên, hãy tạo một thư mục dùng để lưu dữ liệu rồi sau đó chạy lệnh khởi tạo MySQL Container:
Khởi tạo thư mục chứa dữ liệu
```
mkdir -p /opt/docker/mysql
```
Khởi tạo thư mục chứa file config
```
mkdir -p /opt/docker/mysql/conf.d/
```
Khởi tạo file
```
my-custom.cnf
[mysqld] max_connections=250
```