# 1. Cách Sử Dụng Vi
- Trình soạn thảo chuẩn của Linux là *vim*.  
- Cú pháp khởi động: `vi [file]`  
- *vim* có hai chế độ làm việc chính: chế độ lệnh và chế độ soạn thảo.  
  - Trong chế độ lệnh, mọi thứ ta nhập vào đều được chương trình xử lý như là lệnh.
  - Trong chế độ soạn thảo, mọi thứ ta nhập vào đều được coi là nội dung và được đưa vào văn bản.  

- Để chuyển từ chế độ soạn thảo sang chế độ lệnh, nhấn phím `Esc`; ngược lại, để chuyển từ chế độ lệnh sang chế độ soạn thảo, nhấn `Ins` hay phím chữ cái bất kỳ.  
- Các định nghĩa về từ, câu và đoạn trong vim: 
  1. Một từ là bất kỳ chuỗi ký tự nào được phân ranh giới bởi các khoảng trắng hay dấu chấm câu, mặc dù bản thân mỗi ký tự dấu chấm câu cũng là một từ.  
  2. Một câu là một chuỗi ký tự kết thúc bằng một dấu chấm và sau đó là hai khoảng trắng.  
  3. Một đoạn là chuỗi ký tự kết thúc bằng hai ký tự xuống hàng (các đoạn được phân cách nhau bằng một dòng trắng).  

## Các Lệnh Cơ Bản
|Lệnh|Chức năng|
|:---:|---|
|:help|Mở hướng dẫn sử dụng vim|  
|:w [file]|Ghi lại nội dung tập tin. Nếu tập tin đang soạn thảo chưa có tên, ta phải chỉ ra tên tập tin file.| 
|:q| Thoát khỏi vim| 
|:q!| Thoát khỏi vim mà không ghi lại tập tin|  
|:qa!| Thoát khỏi vim mà không ghi lại tất cả các tập tin đang mở|  
|:wq| Thực hiện ghi lại tập tin trước khi thoát.|  
|:next| Chuyển tới bộ đệm (tập tin) kế tiếp (trong trường hợp vim mở đồng thời nhiều tập tin)|  
|:prev| Chuyển tới bộ đệm (tập tin) kế trước (trong trường hợp vim mở đồng thời nhiều tập tin)|  
|:e file| Đóng tập tin hiện hành và mở tập tin file.|  
|:sh| Chuyển tạm sang shell để thi hành các lệnh của shell. Để từ shell quay trở lại vim, nhập exit tại lời nhắc lệnh shell.|  

## Di Chuyển Trong Văn Bản
|Lệnh|Chức Năng|  
|:---:|---|  
|[[| Chuyển lên đầu văn bản|  
|]]| Chuyển xuống cuối văn bản|  
|[Ctrl-F]| Chuyển lên màn hình trước|  
|[Ctrl-B]| Chuyển xuống màn hình sau|  
|[Enter]| Chuyển xuống đầu dòng kế tiếp|  
|nG| Chuyển đến dòng thứ n. Nếu không có n, lệnh G chuyển xuống dòng cuối cùng của văn bản. Số dòng hiện hành có thể được hiển thị bằng cách nhấn [Ctrl-G]|  
|	w| Chuyển lên trước một từ. Nếu sử dụng W thì không coi dấu chấm là một từ|  
|	b| Chuyển về sau một từ. Nếu sử dụng B thì không coi dấu chấm là một từ|  
|	(| Chuyển lên câu trước|  
|	)| Chuyển xuống câu sau|  
|	{| Chuyển tới cuối đoạn trước|  
|	}| Chuyển tới cuối đoạn hiện hành (đầu đoạn kế tiếp)| 

> Ngoài các lệnh di chuyển con trỏ trên, ta cũng có thể sử dụng các phím mũi tên, phím [Home], [End], [Ins]… để di chuyển trong văn bản.  

## Các Lệnh Xóa, Sửa
|Lệnh|Chức Năng|  
|:---:|---|  
|u| Huỷ bỏ lệnh vừa thực hiện|  
|.| Lập lại thay đổi được thực hiện sau cùng|  
|x| Xoá một ký tự tại vị trí con trỏ|  
|dw| Xoá một từ tại vị trí con trỏ|  
|dd| Xoá dòng hiện hành| 
|D| Xoá phần cuối dòng tính từ vị trí con trỏ|  
|d0| Xoá phần đầu dòng tính từ vị trí con trỏ|   
|r| Thay thế một ký tự tại vị trí con trỏ|  
|cw| Xoá từ tại vị trí con trỏ và chuyển về chế độ soạn thảo|  
|o| Chèn một dòng trắng phía dưới dòng hiện hành, và chuyển về chế độ soạn thảo|  
|O| Chèn một dòng trắng phía trên dòng hiện hành, và chuyển về chế độ soạn thảo| 
|a| Chuyển về chế độ soạn thảo, và cho phép nhập nội dung vào sau vị trí con trỏ|  
|A| Chuyển về chế độ soạn thảo và di chuyển con trỏ tới cuối dòng|  
|i| Chuyển về chế độ soạn thảo và cho phép nhập nội dung vào trước vị trí con trỏ|  
|I| Chuyển về chế độ soạn thảo và di chuyển con trỏ tới đầu dòng|  
|R| Chuyển sang chế độ ghi đè (trong chế độ soạn thảo)|  

## Cách Lệnh Tìm Kiếm, Thay Thế
|Lệnh|Chức Năng|  
|---|---|  
|/string| Thực hiện tìm chuỗi string trong văn bản từ trên xuống. Để thực hiện tìm ngược từ dưới lên trên, sử dụng ? thay thế cho /.|  
|n| Thực hiện tìm kiếm tiếp tục|  
|N| Thực hiện tìm kiếm tiếp tục theo chiều ngược lại|  
|:n1,n2 s/pattern/| Thực hiện tìm kiếm chuỗi pattern và thay thế bằng chuỗi replace|  
|replace/| từ dòng thứ n1 đến dòng n2|  
|:1,$ s/pattern/| Thực hiện tìm kiếm chuỗi pattern và thay thế bằng chuỗi replace|  
|replace/g| trong toàn bộ văn bản. Ta cũng có thể dùng cú pháp sau: `:g/pattern/s//replace/`|   

## Sao Chép Và Di Chuyển Nội Dung
- Để thực hiện sao chép hay di chuyển nội dung, ta cần thực hiện các bước sau: 
  1. Đưa các dòng muốn sao chép/di chuyển vào bộ đệm.  
  2. Di chuyển con trỏ tới điểm mà ta muốn đưa nội dung vào.  
  3. Lấy nội dung từ trong bộ đệm ra.  

|Lệnh|Chức năng|  
|:---:|---|  
|:r file|Chèn tập tin file vào vị trí hiện hành con trỏ|  
|:co num|Sao chép nội dung từ vị trí con trỏ đến dòng thứ num trong văn bản|  
|:m num|Di chuyển nội dung từ vị trí con trỏ đến dòng thứ num trong văn bản|  
|nyy|Đưa dòng n đến cuối văn bản vào bộ đệm|  
|y)|Chép phần nội dung từ con trỏ đến cuối câu vào bộ đệm|  
|y}|Chép phần nội dung từ con trỏ đến cuối đoạn vào bộ đệm|  
|p|Lấy nội dung của bộ đệm đưa vào sau vị trí hiện hành của con trỏ|  
|P|Lấy nội dung của bộ đệm đưa vào trước vị trí hiện hành của con trỏ|  
|ma|Đánh dấu dòng hiện hành với tên a|  
|"buff-name|Xác định tên bộ đệm|
# File etc
- Lưu nhiều file cấu hình hệ thống
# 2. Quản trị tài khoản
## Tài Khoản
- Để truy nhập vào hệ thống, người dùng phải có một tài khoản người dùng. Mỗi tài khoản người dùng sẽ có một mã số nhận diện người dùng (User ID).  
- Người dùng lập thành các nhóm, cung cấp cho họ các quyền để đọc, ghi hay thi hành tập tin nào đó. Mỗi một tài khoản nhóm có một tên riêng và có một mã số nhận diện nhóm (Group ID).  

## Thư mục chủ
- Khi tạo một tài khoản người dùng, mặc định Linux tạo một thư mục có tên trùng với tên tài khoản người dùng đó và đặt trong thư mục /home/. Thư mục được tạo này được gọi là thư mục chủ của người dùng.  

## Thông tin môi trường làm việc người dùng - /etc/skel/ 
- Thư mục `/etc/skel/` có chứa các tập tin và thư mục cấu hình màn hình của người dùng, đồng thời có chứa có chứa các tập tin khởi nạp khung là `.bash_profile`, `.bash_logout` và `.bashrc`.  

## Danh sách lệnh và tập tin liên quan
### Các lệnh quản trị người dùng và nhóm
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

### Các tập tin liên quan 
|Tên tập tin|Chức năng|
|:---:|---|
|/etc/passwd| 	Lưu thông tin tài khoản người dùng|  
|/etc/shadow| 	Chứa mật mã đăng nhập và các thông tin về tài khoản người dùng|  
|/etc/group| 	Lưu thông tin tài khoản nhóm người dùng|  
|/etc/gshadow| 	Lưu mật mã đăng nhập của nhóm|  
|/etc/login.defs| 	Chứa các thông tin được gán tự động cho tài khoản khi được tạo|  
 
# 3. Quản trị hệ thống
## Khởi nạp hệ thống - Tiến trình, deamon
### Quá trình khởi động (boot)
- Quá trình khởi động hệ điều hành Linux thực hiện qua các bước cơ bản như sau:  
  1.	BIOS thực hiện kiểm tra tính toàn vẹn trên bộ nhớ và tìm kiếm các chỉ dẫn trên **Master Boot Record (MBR)** trên đĩa mềm hay trên ổ cứng  
  2.	MBR gọi bộ nạp khởi động của Linux – *LILO* hay *GRUB*  
  3. LILO/GRUB sau đó sẽ nhận diện nhân hệ điều hành để thi hành và sau đó sẽ nạp nhân hệ điều hành Linux từ phần chia `/boot/` 
  4.	Nhân hệ điều hành chuyển điều khiển cho chương trình `/sbin/init`.  
  5.	Dựa trên mức thi hành tương ứng, `/sbin/init` thực hiện nạp các dịch vụ và gắn (mount) tất cả các phần chia hệ thống (được khai báo trong `/etc/fstab`).  

### Tiến trình
- Một tiến trình là một “yêu cầu” hay “hoạt động” của một chương trình. Một chương trình là một danh sách các chỉ dẫn cho máy tính thực hiện.  
- Để chạy chương trình, nó cần được sao chép (hoặc nạp) vào bộ nhớ chính máy tính và đơn vị xử lý trung tâm để cho biết bắt đầu đọc (và thực hiện) các chỉ dẫn lấy từ bộ nhớ. 
> Việc thi hành các chỉ dẫn của chương trình sẽ tạo ra các tiến trình.  

Mỗi tiến trình đều có những thuộc tính như sau: 
-	PID – mã số nhận diện tiến trình. Đây là một con số mà nhân hệ điều hành sử dụng để nhận diện tiến trình. 
-	PPID – mã số nhận diện tiến trình cha, là tiến trình phát sinh ra tiến trình hiện hành 
-	UID và GID – mã nhận diện tài khoản người dùng và nhóm đã tạo ra tiến trình 
- Độ ưu tiên tiến trình. Độ ưu tiên của tiến trình có giá trị từ -20 (độ ưu tiên cao nhất) đến +19 (độ ưu tiên thấp nhất).  

`Fork` tạo một bản sao của tiến trình gốc, gọi là tiến trình con. Tiến trình con giống với tiến trình cha ở tất cả các thuộc tính ngoại trừ các thuộc tính sau:  
- Tiến trình mới có PID phân biệt  
- PPID của tiến trình con trỏ tới tiến trình cha  
- Tiến trình con không được cấp phép sử dụng tài nguyên riêng  
- Tiến trình con có bản sao của bộ mô tả tập tin của tiến trình cha  

### Deamon
- Daemon là bất kỳ chương trình (tiến trình) nào được 'chạy' liên tục trong chế độ ngầm, luôn thực hiện kiểm tra các yêu cầu và đáp ứng lại các yêu cầu đó.  

### Tiến trình Init  
- Là một trong những chương trình thiết yếu đối với hoạt động của một hệ thống Linux  
- Có nhiều nhiệm vụ quan trọng, như là khởi nạp các thể hiện của getty (để người dùng có thể đăng nhập), thực thi các mức thi hành chương trình và quản lý những tiến trình vô chủ (mất tiến trình cha).  

## Quản lý tiến trình
|Lệnh|Chức Năng|  
|:---:|---|  
|ps|Hiển thị thông tin tiến trình|  
|top|Hiển thị thông tin sử dụng tài nguyên|  
|kill|Kết thúc một tiến trình|  

## Thi hành lệnh ở chế độ ngầm (background) 
- Để thi hành một lệnh ở chế độ ngầm, ta đặt một ký tự '&' tại cuối dòng lệnh. 

## Lập lịch thi hành - cron và crontab
- Những tác vụ hệ thống lặp đi lặp lại theo những khoảng thời gian định kỳ có thể được lập lịch để thi hành tự động. Lịch này có thể được thực hiện bằng lệnh cron. 
- Thông tin lịch được đặt trong tập tin crontab. 
> Một mục từ trong tập tin crontab có sáu trường theo định dạng sau: `minute hour day month week command`

# 4. Quản lý đĩa và hệ thống tập tin
## Tự động gắn kết hệ thống tập tin - tập tin /etc/fstab 
- Ta có thể thực hiện gắn kết một hệ thống tập tin một cách tự động mỗi khi khởi động hệ thống bằng cách khai báo các thông tin gắn kết vào trong một tập tin cấu hình `/etc/fstab`.  

## Tạo phần chia và định dạng hệ thống tập tin - lệnh fdisk, mkfs 
- Để thay đổi các phần chia trên ổ đĩa hiện hành hay sử dụng được ổ đĩa cứng mới, ta phải tạo phần chia bằng lệnh `fdisk` và sau đó phải định dạng phần chia mới tạo bằng lệnh `mkfs`.  

## Kiểm tra và khôi phục hệ thống tập tin Linux - lệnh fsck 
- Để sửa lỗi cho một hệ thống tập tin, ta có thể sử dụng lệnh fsck

## Thông tin về tình trạng sử dụng đĩa - lệnh df, du 
- Để tìm xem không gian còn trống trên một hệ thống tập tin, ta có thể sử dụng lệnh `df`.  
- Lệnh `du` thực hiện tính toán mức chiếm dụng đĩa của các tập tin  

# 5. Cập nhật Linux và các ứng dụng khác 
## Cài đặt và cập nhật với RPM  
- RPM - RedHat Packet Manager - là một chương trình quản lý các gói phần mềm của Linux, là một hệ thống ‘gói’ mở, sẵn dùng cho bất kỳ người sử dụng nào.  
- Nó cho phép người dùng lấy được mã nguồn của phần mềm mới và/hoặc đóng gói nó vào thành dạng nguồn hay tập tin nhị phân.  
- Nó cũng quản lý một cơ sở dữ liệu của tất cả các gói phần mềm và các tập tin của chúng, có thể được sử dụng để xây dựng, cài đặt, truy vấn, kiểm tra, nâng cấp và xoá bỏ chương trình.  

## Biên dịch phần mềm 
Thông thường, để biên dịch và cài đặt phần mềm, ta chỉ cần thực hiện hai lệnh sau: 
```
# make 
# make install
```
> Lệnh make thực hiện biên dịch, và lệnh make install thực hiện cài đặt chương trình vào.

# 6. Sao lưu và khôi phục 
## Tiện ích lưu trữ - lệnh tar 
- Tiện ích tar được thiết kế với mục đích để sao lưu các tập tin hoặc kết hợp nhiều tập tin vào thành một tập tin đơn. 

## Nén và giải nén tập tin 
|Công cụ nén|Tên mở rộng của tập tin|Công cụ giải nén|  
|:--:|:---:|:---:|  
|bzip2| 	.bz2| 	bunzip2 |  
|gzip| 	.gz| 	gunzip |  
|zip| 	.zip| 	unzip |  

# 7. Chương trình nạp khởi động 
## LILO
- Linux có cung cấp một chương trình quản lý khởi động là *LInux LOader (LILO)* dùng để khởi động Linux cũng như cho phép người dùng lựa chọn hệ điều hành muốn sử dụng, trong trường hợp máy tính có cài nhiều hệ điều hành.
- Cú pháp lệnh:   
> `lilo [options]`

## GRUB
- GRUB (Grand Unified Bootloader) có chứa một số đặc tính quan trọng khác biệt so với LILO như sau: 
•	GRUB cung cấp một môi trường trước hệ điều hành (pre-OS), dựa trên lệnh.  
•	GRUB hỗ trợ chế độ Logical Block Addressing (LBA). LBA chuyển giao quá trình chuyển đổi địa chỉ được dùng để tìm các tập tin cho phần sụn (firmware) của ổ đĩa cứng, do đó nó sẽ không gặp phải vấn đề giới hạn dưới 1024-cylinder của BIOS.   
•	GRUB có thể đọc các phần chia ext2.  

### Giao diện GRUB
GRUB có ba giao diện, mỗi giao diện cung cấp một mức chức năng khác nhau. Mỗi giao diện đều cho phép người dùng khởi động hệ điều hành, và chuyển đổi tới các giao diện khác trong môi trường của GRUB. 
- Giao diện menu  
Giao diện menu là giao diện được hiển thị một cách mặc định nếu GRUB được cấu hình tự động trong quá trình cài đặt Red Hat Linux.  
Từ giao diện menu, nhấn [e] để chuyển tới giao diện soạn thảo mục từ menu hay nhấn [c] để gọi giao diện dòng lệnh.   
- Giao diện soạn thảo menu   
Trong giao diện này, GRUB sẽ hiển thị danh sách các lệnh và người dùng có thể thay đổi các dòng lệnh này trước khi khởi động hệ điều hành bằng cách thêm một dòng lệnh ([o] hay [O]), sửa một dòng lệnh ([e]), hay xoá một dòng lệnh ([d]). 
Sau khi đã thực hiện các thay đổi, nhấn phím [b] để thi hành các lệnh và khởi động hệ điều hành. Trường hợp muốn loại bỏ tất cả các thay đổi và nạp lại giao diện menu chuẩn, nhấn phím [Esc]. Nhấn [c] để gọi giao diện dòng lệnh. 
- Giao diện dòng lệnh  
Dòng lệnh là giao diện cơ bản nhất của GRUB và nó cũng được cung cấp quyền điều khiển nhiều nhất. Giao diện dòng lệnh có thể cho phép ta thi hành bất kỳ lệnh nào của GRUB. 

# 8. Thông tin hệ thống, hệ thống tập tin /proc/ 
## Hệ thống tập tin /proc/ 
- Thư mục /proc/ có chứa các tập tin tin đặc biệt đại diện cho trạng thái hiện hành của nhân hệ điều hành – cho phép các ứng dụng và người dùng ‘nhìn thấy’ nhân hệ thống: thông tin về phần cứng hệ thống và bất kỳ tiến trình đang thi hành nào. 
- Trong thư mục này cũng có chứa một số tập tin cho phép người dùng và ứng dụng thay đổi cấu hình tới nhân hệ điều hành.  

## Hệ thống tập tin giả 
- Thư mục `/proc/` có chứa một kiểu tập tin khác được gọi là tập tin giả. Do đó, thư mục `/proc/` thường được gọi là một hệ thống tập tin giả.  
- Những tập tin giả này có đặc tính riêng biệt. Phần lớn các tập tin này có kích thước bằng 0, tuy nhiên chúng có chứa một số lượng lớn thông tin.  

## Thiết lập tham số nhân hệ điều hành - lệnh sysctrl 
- Lệnh sysctl được sử dụng để xem, thiết lập và tự động hoá các thiết lập nhân hệ điều hành trong thư mục /proc/sys/.  

# 9. Các vấn đề quản trị khác 
## Biến môi trường
- Một khái niệm quan trọng trên linux đó là môi trường (environment) được định nghĩa qua các biến môi trường. Một số biến được đặt bởi hệ thống, số khác do bạn đặt, hoặc set bởi shell (các lệnh) hay một chương trình nào đó được load.  
- Một biến môi trường có tên là một dãy chữ cái và nhận một giá trị nhất định, giá trị này có thể là số, chữ, tên file, thiết bị (device) hay một kiểu dữ liệu nào đó.  

## Tạo đĩa mềm khởi động 
- Đĩa mềm khởi động hệ điều hành Linux có thể giúp ta khởi động hệ thống trong trường hợp có hư hỏng, nó có thể giúp ta kiểm tra một nhân hệ điều hành mới, và nó có thể giúp ta khởi động hệ điều hành Linux trong trường hợp máy tính sử dụng nhiều hệ điều hành.  

## Shutdown hệ thống
- Cú pháp lệnh như sau: 
> `shutdown [options] time [warning-message] `  

## Tạo tên hiệu cho lệnh - lệnh alias
## Hiển thị/thay đổi ngày giờ hệ thống - lệnh date 
## Hiển thị thông tin hệ thống - lệnh uname 

# LAMP
LAMP stack là một bộ phần mềm sửa dụng trên Linux (L) bao gồm Apache (A), Mysql (M) và PHP (P)  
- Linux: Hệ điều hành.  
- Apache: Đây là phần mềm webserver phổ biến hiện nay. Apache được cài đặt trên server để giúp xử lý các request với giao thức HTTP gửi tới máy chủ. Do đó, Apache còn được gọi là HTTP webserver. Lưu ý: HTTPS cũng là một giao thức mà Apache có thể sử lý.  
- Mysql: Là phần mềm database server giúp lưu trữ và truy xuất dữ liệu một cách hiệu quả trên server.  
- Python: Ngôn ngữ lập trình.  
