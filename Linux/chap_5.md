# Package Management
## Hệ thống quản lý gói (Package Management Systems)
- Các phần cốt lõi của bản phân phối và phần lớn các phần mềm bổ sung được cài đặt thông qua *Package Management System*.  
- Các gói có thể phụ thuộc vào nhau.  

|Công cụ cấp cao|Công cụ cấp thấp|Family|  
|---------------|--------------|------|  
|apt-get|dpkg|Debian|  
|zypper|rpm|SUSE|
|yum|rpm|Red Hat|  
  
  
|Thao tác|RPM|Debian|
|---------|-----------|-----------|
|Cài đặt gói|rpm –i foo.rpm|dpkg --install foo.deb|
|Cài đặt gói với các dependency từ kho lưu trữ|yum install foo|apt-get install foo|
|Xóa gói|rpm –e foo.rpm|dpkg --remove foo.deb|
|Xóa gói và các dependency sử dụng kho lưu trữ|yum remove foo|apt-get remove foo|
|Cập nhật gói|rpm –U foo.rpm|dpkg --install foo.deb|
|Cập nhật gói sử dụng kho lưu trữ và resolving dependencies|yum update foo|apt-get upgrade foo|
|Cập nhật toàn bộ hệ thống|yum update|apt-get dist-upgrade|
|Hiện thị toàn bộ các gói đã cài đặt|yum list installed|dpkg --list|
|Lấy thông tin về gói đã cài đặt gồm các tệp|rpm –qil foo|dpkg --listfiles foo|
|Hiển thị các gói "foo"|yum list foo|apt-cache search foo|
|Hiển thị các gói có sẵn|yum list|apt-cache dumpavail|
|Hiển thị gói của một tệp|rpm –qf file|dpkg --search file|