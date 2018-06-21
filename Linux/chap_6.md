# Sao lưu dữ liệu
- Lệnh `rsync` được dùng để đồng bộ hóa toàn bộ cây thư mục.  
>Về cơ bản, nó sao chép tập tin như lệnh `cp`.  
- `rsync` sao chép đệ quy một cây thư mục thông qua mạng, chỉ có ***sự khác biệt*** mới được truyền tải.  
- Sử dụng `rsync -r` để đệ quy đi từ trên xuống cây thư mục sao chép tất cả các file và các thư mục dưới thư mục nguồn.  
# Nén dữ liệu
  
|Lệnh|Chức năng|
|-------|-----------|
|gzip 	|Tiện ích nén được Linux sử dụng thường xuyên nhất|
|bzip2  |Tạo file nhỏ hơn so với các tệp được gzip tạo ra|
|xz     |Tiện ích nén hiệu quả nhất về không gian được sử dụng trong Linux.|
|zip    |Thường xuyên yêu cầu xem xét và nén các file ở các hệ điều hành khác|

# Lưu trữ dữ liệu

|Lệnh|Chức năng|
|-------|-----------|
|tar xvf mydir.tar|Giải nén các file mydir.tar vào thư mục mydir|
|tar zcvf mydir.tar.gz mydir|Tạo file nén và nén bằng gzip|
|tar jcvf mydir.tar.bz2 mydir|Tạo file nén và nén bằng bz2|
|tar xvf mydir.tar.gz|Giải nén các file mydir.tar.gz vào thư mục mydir|
|tar cvf  mydir.tar|Hiển thị nội dung trong thư mục mydir|

# Sao chép đĩa
- Lệnh `dd` sử dụng để tạo bản sao cho không gian của đĩa thô (raw disk)  
- Lệnh `dd` có thể sao chép đĩa khởi động dưới dạng thẻ Compact Flash, Micro SD hay USB. Chèn thẻ CF được sao chép vào hệ thống và tạo ra một bản sao.  