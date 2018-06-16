# Hệ thống file
## Cấu trúc hệ thống file
- Trong nhiều hệ điều hành, bao gồm cả linux hệ thống file có cấu trúc dạng cây.  
- Lệnh `mount` được sử dụng để gắn một hệ thống file vào một điểm gắn kết.
`$ mount /dev/sda5 /mnt`  
- Nó sẽ đính kèm hệ thống tập tin chứa trong phân vùng đĩa được kết hợp bởi nút thiết bị /dev/sda5, vào cây hệ thống tập tin tại điểm gắn kết /mnt.
- Lệnh `unmount` được sử dụng để tách hệ thống file khỏi điểm gắn kết.  
`$ umount /mnt`  
- Lệnh `df -Th` hiển thị thông tin về các hệ thống tập tin được gắn kết bao gồm các thống kê kiểu và cách sử dụng về không gian hiện đang sử dụng và trống.

## Thư mục home
- Trong UNIX, mỗi người dùng đều có thư mục home của riêng mình, thường được đặt trong /home.  
- Thư mục /home thường được gắn kết như là một hệ thống tập tin riêng biệt trên phân vùng riêng của nó, hoặc thậm chí được chuyển đi từ xa trên một mạng thông qua NFS.

## Thư mục nhị phân
- Thư mục /bin chưa các tệp nhị phân thực thi.  
- Tất cả các thư mục nhị phân nằm trong phân vùng gốc.

## Thư mục thiết bị
- Chứa các tập tin để nhận biết cho các thiết bị của hệ thống, phần cứng, phần mềm ngoại trừ các thiết bị mạng.

## Thư mục biến
- Chứa những tập tin có thể thay đổ kích thước và nội dung khi hệ thống đang chạy.  
- Chẳng hạn như các mục được nhập vào trong các thư mục sau:  
  - Hệ thống tập tin log: /var/log  
  - Các gói và các file dữ liệu /var/lib  
  - Print queues: /var/spool  
  - Các file tạm thời cần khi reboot : /var/tmp  
  - Thư mục chính FTP: /var/ftp  
  - Thư mục máy chủ web: /var/www  

## Thư mục cấu hình hệ thống
- Thư mục /etc là trang chủ cho các tệp cấu hình hệ thống. Nó không chứa các chương trình nhị phân, mặc dù có một số tập lệnh thực thi.

## The boot directory
- Thư mục / boot chứa một số tệp cần thiết cần thiết để khởi động hệ thống.

## Thư mục thư viện
- Thư mục / lib chứa các thư viện cho các chương trình cần thiết trong thư mục / bin và / sbin.

## Thư mục bổ sung
- |Thư mục|Chức năng|
|---------|-----|
| /opt | Các gói phần mềm ứng dụng tùy chọn |
| /sys | Hệ thống tệp ảo giả cung cấp thông tin về hệ thống và phần cứng. Có thể được sử dụng để thay đổi thông số hệ thống và gỡ lỗi. |
| /srv | Dữ liệu trang web cụ thể được hệ thống phân phối. |
| /tmp | Hồ sơ tạm thời. Trên một số bản phân phối các tệp này bị xóa trên một lần khởi động lại |
| /media | Nó thường được đặt ở nơi các thiết bị di động, chẳng hạn như đĩa CD, DVD và ổ USB được lắp. |
| /usr | Ứng dụng, tiện ích và dữ liệu đa người dùng |
| /usr/include | Các tệp tiêu đề được sử dụng để biên dịch ứng dụng |
| /usr/lib | Thư viện cho các chương trình nhị phân |
| /usr/lib64 | Thư viện 64 bit cho các chương trình nhị phân |
| /usr/share | Dữ liệu chia sẻ được các ứng dụng sử dụng, thường độc lập về cấu trúc |
| /usr/src | Mã nguồn, thường cho nhân Linux |
| /usr/local | Dữ liệu và chương trình cụ thể cho máy cục bộ. |

## Bảng hệ thống file
- /etc/fstab.

