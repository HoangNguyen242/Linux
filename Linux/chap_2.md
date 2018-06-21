# Làm Việc Với Các Tệp  

## I.Luồng file (The file streams)  
- Có ba luồng file hay bộ mô tả tiêu chuẩn luôn mở khi lệnh được thực hiện:  
  - Đầu vào tiêu chuẩn (stdin).   
  - Đầu ra tiêu chuẩn (stdout).  
  - Lỗi tiêu chuẩn (stderr).  

## II.Tìm kiếm file
- Tiện ích `locate` thực hiện tìm kiếm thông qua cơ sở dữ liệu và thư mục được xây dựng trước đó trên hệ thống, kết nối tất cả các mục có chuỗi ký tự được chỉ định.  
- Hầu hết hệ thống trên Linux chạy mỗi ngày nhưng có thể cập nhật bất cứ lúc nào bằng lệnh updatedb với tư cách root user.  
- Kết quả thu được từ `locate` đôi khi rất dài, có thể sử dụng `grep` làm bộ lọc rút gọn danh sách có liên quan 
- Có thể sử dụng các ký tự đại diện để tìm kiếm tên tệp có chứa các ký tự cụ thể.  

|Wildcards|Result|  
|---------|-----------|  
|?     |Đưa ra kết quả phù hợp với từng ký tự riêng biệt|  
|*     |Đưa ra kết quả phù hợp với từng chuỗi ký tự|  
|[set] |Đưa ra kết quả phù hợp với từng ký tự không nằm trong tập ký tự|  
|[!set]|Đưa ra kết quả phù hợp với từng ký tự không nằm trong tập ký tự|  

## III.Quản lý file

|Lệnh|Công dụng|  
|-------|-----------|  
|cat  |Xem các file mới|  
|tac  |Xem file ngược, bắt đầu từ dòng cuối|  
|less |Xem những file lớn|  
|tail |Được sử dụng để in những dòng cuối cùng của một tệp. Thay đổi số dòng bằng cách thực hiện -n i hoặc chỉ -i nếu bạn muốn xem i dòng cuối thay vì mặc định|  
|head |Ngược lại với tail|  

## IV. So sánh tệp
- Lệnh `diff` dùng để so sánh các file và thư mục.

## V. File tiện ích
- Tính chất thật của file được xác định bởi tiện ích `file`. 
>Nó kiểm tra nội dung và các đặc điểm nhất định để xác định xem các tệp là văn bản thuần túy, thư viện được chia sẻ, chương trình thực thi, tập lệnh hay thứ gì khác.
