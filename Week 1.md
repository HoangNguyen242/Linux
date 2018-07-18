# Terminal
## Terminal ảo
- Vì tính đa nhiệm mà Linux cung cấp thêm các terminal ảo, ta có thể ***có nhiều terminal cùng lúc***, mỗi terminal có thể có những tác vụ riêng biệt  
## Smart Terminal
- Các Smart Terminal có thể ***giao tiếp với hệ thống Linux một mức cao hơn***, từ ký tự đơn giản đến biểu tượng, cửa sổ, menu và các biến cố xử lý của thiết bị chuột.

# Shell
> Là chương trình giao diện giữa người dùng và nhân hệ điều hành Linux.
- Mỗi lệnh của người dùng sẽ được *shell* diễn dịch rồi chuyển tới nhân hệ điều hành để thực hiện.  
- Bash là ***shell mặc định của Red Hat Linux***.
# Thi hành lệnh
- Cú pháp lệnh cơ bản trong Linux:  
  > command [options] [arguments]  

*command: Tên của chương trình mà ta muốn thi hành.  
options: Các lựa chọn của lệnh, thường được chỉ ra sau một dấu -.  
arguments: Các đối số của lệnh, thí dụ như tên tập tin, thư mục hay chương trình mà lệnh cần truy nhập tới …*

- Thi hành đồng thời nhiều lệnh  
  Linux cho phép nhập nhiều lệnh tại một thời điểm với cú pháp sau: 
    > command_1 ; command_2 ; command_3  

# Pipeline
- Pipeline là kết nối các tiến trình bằng cách để cho kết quả xuất của một lệnh này là một đối số nhập của một lệnh khác (có nghĩa là lấy đầu ra của lệnh này làm đầu vào của lệnh khác).  
- Cú pháp thi hành Pipeline:  
  > command_1 | command_2 | command_3  

# Tiêu chuẩn nhập, xuất, lỗi
- Mọi chương trình chạy trong shell đều mở ba tập tin (thiết bị): nhập chuẩn (standard input), xuất chuẩn (standard output), và lỗi chuẩn (standard error). 
- Các tập tin này cung cấp ý nghĩa truyền thông giữa các chương trình, và tồn tại trong suốt quá trình tiến trình hoạt động.  
- Thiết bị nhập chuẩn cung cấp một cách thức gửi dữ liệu cho một tiến trình. Mặc định, dữ liệu nhập chuẩn được đọc từ bàn phím.  
- Thiết bị xuất chuẩn cung cấp một cách thức để chương trình gửi dữ liệu ra. Mặc định, thiết bị xuất chuẩn là màn hình.  
- Tập tin lỗi chuẩn là nơi chương trình ghi lại báo cáo về bất kỳ lỗi nào xảy ra trong quá trình thi hành. Mặc định, tập tin này là màn hình.   