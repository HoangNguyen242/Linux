# File etc
- Lưu nhiều file cấu hình hệ thống
# Quản trị tài khoản
## Tài Khoản
- Để truy nhập vào hệ thống, người dùng phải có một tài khoản người dùng. Mỗi tài khoản người dùng sẽ có một mã số nhận diện người dùng (User ID).  
- Người dùng lập thành các nhóm, cung cấp cho họ các quyền để đọc, ghi hay thi hành tập tin nào đó. Mỗi một tài khoản nhóm có một tên riêng và có một mã số nhận diện nhóm (Group ID).  

## Thư mục chủ
- Khi tạo một tài khoản người dùng, mặc định Linux tạo một thư mục có tên trùng với tên tài khoản người dùng đó và đặt trong thư mục /home/. Thư mục được tạo này được gọi là thư mục chủ của người dùng.  

## Thông tin môi trường làm việc người dùng - /etc/skel/ 
- Thư mục `/etc/skel/` có chứa các tập tin và thư mục cấu hình màn hình của người dùng, đồng thời có chứa có chứa các tập tin khởi nạp khung là `.bash_profile`, `.bash_logout` và `.bashrc`.  

# Danh sách lệnh và tập tin liên quan
## Các lệnh quản trị người dùng và nhóm
|Lệnh|Chức năng|  
|:---:|---|  
|useradd|Tạo tài khoản người dùng|  
|passwd|Thay đổi mật khẩu đăng nhập|  
|userdel|Xóa tài khoản người dùng|  
|usermod|Thay đổi thông tin tài khoản|  
|groupadd|Thêm tài khoản nhóm người dùng|  
|groupdel|Xóa tài khoản nhóm người dùng|  
|groupmod|Thay đổi thông tin tài khoản nhóm|  
|id|Cho biết thông tin về người dùng|  
|su|Truy nhập với quyền người dùng khác|

## Các tập tin liên quan 
|Tên tập tin|Chức năng|
|:---:|---|
|/etc/passwd| 	Lưu thông tin tài khoản người dùng|  
|/etc/shadow| 	Chứa mật mã đăng nhập và các thông tin về tài khoản người dùng|  
|/etc/group| 	Lưu thông tin tài khoản nhóm người dùng|  
|/etc/gshadow| 	Lưu mật mã đăng nhập của nhóm|  
|/etc/login.defs| 	Chứa các thông tin được gán tự động cho tài khoản khi được tạo|  
 