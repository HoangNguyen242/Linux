# Hệ thống file
## Cấu trúc hệ thống file
- Trong nhiều hệ điều hành, bao gồm cả linux hệ thống file có cấu trúc dạng cây.  
- Lệnh `mount` được sử dụng để gắn một hệ thống file vào một điểm gắn kết.
`$ mount /dev/sda5 /mnt`  
- Nó sẽ đính kèm hệ thống tập tin chứa trong phân vùng đĩa được kết hợp bởi nút thiết bị /dev/sda5, vào cây hệ thống tập tin tại điểm gắn kết /mnt.
- Lệnh `unmount` được sử dụng để tách hệ thống file khỏi điểm gắn kết.  
`$ umount /mnt`  
- Lệnh `df -Th` hiển thị thông tin về các hệ thống tập tin được gắn kết bao gồm các thống kê kiểu và cách sử dụng về không gian hiện đang sử dụng và trống.

## Các thư mục home
- Trong UNIX, mỗi người dùng đều có thư mục home của riêng mình, thường được đặt trong /home.  
- Thư mục /home thường được gắn kết như là một hệ thống tập tin riêng biệt trên phân vùng riêng của nó, hoặc thậm chí được chuyển đi từ xa trên một mạng thông qua NFS.

## Các thư mục nhị phân
- Thư mục /bin chưa các tệp nhị phân thực thi.  
- Các lệnh cần thiết chẳng hạn như: `ps`,`ls`,`cp`.

