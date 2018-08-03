# Người dùng và nhóm người dùng
- Linux là một **hệ điều hành đa người dùng**, nhiều người dùng có thể đăng nhập cùng một lúc.  
- Lệnh `who` liệt kê những người dùng hiện đang đăng nhập. Để xác định người dùng hiện tại, hãy sử dụng lệnh `whoami`.  
- Linux sử dụng các nhóm để quản lý người dùng. Nhóm là tập hợp các tài khoản có quyền được được quyền chia sẻ.  
- Kiểm soát nhóm thông qua tệp `/etc/group` (hiển thị danh sách nhóm và thành viên).  
- Mỗi người dùng Linux được chỉ định một ID duy nhất(**UID**), cũng như một hoặc nhiều ID nhóm(**GID**), bao gồm một ID mặc định giống với ID người dùng. Chúng được kết hợp với tên thông qua các tập tin `/etc/passwd` và `/etc/group`.  
- Chỉ người dùng gốc(root user) mới có thể thêm và xóa người dùng và nhóm.  
- Việc thêm một người dùng mới được thực hiện bằng lệnh `useradd` và loại bỏ một người dùng hiện có được thực hiện bằng lệnh `userdel`.
- Lệnh `id` không cung cấp thông tin về người dùng hiện tại. Nếu được đặt tên của một người dùng khác làm đối số, `id` sẽ báo cáo thông tin về người dùng đó.  
- Sử dụng lệnh `passwd` để thay đổi mật khẩu cho người dùng.  
- Thêm một nhóm mới được thực hiện với lệnh `groupadd` và được gỡ bỏ bằng lệnh `groupdel`.  
- Thêm một người dùng vào một nhóm đã tồn tại được thực hiện với lệnh `usermod`.   
- Tất cả các lệnh này cập nhật file `/etc/group` nếu cần. Lệnh `groupmod` có thể được sử dụng để thay đổi các thuộc tính nhóm.

# Người dùng gốc (The root user)
- Tài khoản gốc có quyền lực và có toàn quyền truy cập vào hệ thống.  
- Phải cực kỳ thận trọng trước khi cấp quyền truy cập root đầy đủ cho người dùng.  
- Có thể sử dụng tính năng `sudo` để gán nhiều đặc quyền giới hạn cho người dùng tiêu chuẩn (standard user ):  
  1. Chỉ trên cơ sở tạm thời.  
  2. Chỉ cho phép truy cập một tập hợp lệnh cụ thể.  
- Khi gán đặc quyền nâng cao, bạn có thể sử dụng lệnh su (switch user) để khởi động một shell mới đang chạy như một người dùng khác (bạn phải nhập mật khẩu của người dùng mà bạn đang trở thành).  
# Startup Files
- Trong Linux, chương trình lệnh shell, bash sử dụng một hoặc nhiều tệp khởi động để định hình môi trường.  
- Các tệp trong thư mục `/etc` xác định thiết lập chung cho tất cả người dùng trong khi tệp khởi tạo trong thư mục chính của người dùng có thể chứa và ghi đè cài đặt chung.
- Các startup file có thể làm bất cứ điều gì người dùng muốn trong mọi lệnh shell, ví dụ:  
  - Tùy chỉnh với ý muốn của người dùng.
  - Xác định các dòng lệnh tắt và dòng lệnh ẩn.
  - Thiết lập trình soạn thảo văn bản mặc định.
  - Thiết lập được dẫn để tìm chương trình thực thi.  

# Biến môi trường (Environment variables)
- Các biến môi trường được đặt tên đơn giản với số lượng có giá trị cụ thể và được hiểu bởi lệnh shell, chẳng hạn như bash.  
- Một số được thiết lập trước bởi hệ thống, và một số khác được thiết lập bởi người dùng hoặc ở dòng lệnh hoặc trong khi khởi động và các tập lệnh khác.  
- Tất cả các lệnh `set`, `env`, hoặc `export` hiển thị các biến môi trường.  
- Theo mặc định, các biến được tạo trong một tập lệnh chỉ tồn tại cho shell hiện tại. Tất cả các tiến trình con (sub-shell) sẽ không có quyền truy cập vào các giá trị đã được thiết lập hoặc sửa đổi.  
- Cho phép các tiến trình con xem các giá trị, yêu cầu sử dụng lệnh xuất.  

Task|Command 
---|---
Hiển thị giá trị của một biến cụ thể |	echo $SHELL 
Xuất một giá trị biến mới |	export VAR=value
Thêm biến vĩnh viễn |	Add the line export VAR=value to ~/.bashrc

>HOME là một biến môi trường đại diện cho thư mục nhà hoặc đăng nhập của người dùng.   
>Biến môi trường PATH là một danh sách có thứ tự các thư mục được quét khi một lệnh được đưa ra để tìm chương trình hoặc tập lệnh thích hợp để chạy.  
>Biến môi trường SHELL trỏ tới lệnh shell mặc định của người dùng (chương trình đang xử lý bất cứ điều gì bạn gõ vào một cửa sổ lệnh, thường là bash) và chứa tên đường dẫn đầy đủ đến shell.  
>Biến môi trường PS (Prompt Statement- Cậu lệnh Prompt) được sử dụng để tùy chỉnh chuỗi yêu cầu của bạn trong các cửa sổ terminal để hiển thị thông tin bạn muốn.


|Character|Usage|
|---------|-----|
|\u|Tên người dùng|
|\h|Tên máy chủ|
|\w|Thư mục làm việc hiện tại| 
|\!|Số lịch sử của lệnh này|
|\d|Ngày|
> Chúng phải ở trong dấu ' ' khi được sử dụng.  

# Lệnh lịch sử (Command history)  
- Các bash theo dõi các lệnh và câu lệnh đã nhập trước đó trong bộ đệm lịch sử. Bạn có thể gọi lại các lệnh đã sử dụng trước đó chỉ bằng cách sử dụng các phím con trỏ Lên và Xuống.
- Để xem danh sách các lệnh đã thực hiện trước đó, bạn có thể sử dụng `history` tại dòng lệnh.

|Biến|Công dụng|
|--------|-----|
|HISTFILE|Chứa vị trí tệp lịch sử|
|HISTFILESIZE|Lưu trữ số lượng tối đa của dòng trong tệp lịch sử|
|HISTSIZE|Lưu trữ số lượng tối đa của dòng trong tệp lịch sử cho phiên hiện tại|

- Cú pháp để thực hiện các lệnh trước đó

|Cú pháp|Chức năng|
|------|-----|
|!!|Thực thi lệnh gần nhất|
|!|Thay thế lịch sử|
|!$|Xem xét đối số cuối cùng trong một dòng|
|!n|Tham khảo dòng lệnh thứ n|
|!string|Tham khảo lệnh gần đây nhất bắt đầu bằng chuỗi|  

# Tạo bí danh  
- Các lệnh tùy chỉnh có thể được tạo ra để thay đổi chức năng của những cái đã tồn tại bằng cách tạo bí danh.
- Lệnh `alias` không có đối số sẽ liệt kê các bí danh hiện đang được xác định.

