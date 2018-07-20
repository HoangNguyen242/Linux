# Thông dịch và biên dịch  

|Thông dịch|Biên dịch|
|---|---|
|Khi chương trình chạy đến dòng lệnh nào sẽ chuyển thành ngôn ngữ máy tính đến đó để máy tính có thể thực thi.|Chương trình sẽ dịch toàn bộ thành mã máy rồi mới tiến hành thực thi.|  

# Nhân hệ điều hành (Kernel)
- Là thành phần trung tâm của các OS.  
- Quản lý các tài nguyên phần cứng và phần mềm
- Nhân có thể cung cấp *các tầng trừu tượng mức thấp nhất* cho các tài nguyên máy tính (đặc biệt là bộ nhớ, CPU, và các thiết bị vào ra mà phần mềm ứng dụng cần điều khiển để thực hiện các chức năng của mình).  
- Nhân hệ điều hành thường cung cấp các tiện ích xử lý này cho các tiến trình của các phần mềm ứng dụng qua các cơ chế liên lạc giữa các *tiến trình* (inter-process communication) và *các hàm hệ thống* (system call).  
>  Nhân hệ điều hành dưới một khía cạnh nào đó là một cái tên đơn giản *biếu thị cho* **tầng trừu tượng ở mức thấp nhất** được xử lý trong các phần mềm trước khi đi qua trình biên dịch ngôn ngữ assembly sang ngôn ngữ máy và đưa đến phần cứng của máy tính để thi hành.  
  
-  Khi *boot loader* bắt đầu thực thi nhân hệ điều hành trong *supervisor mode*, nhân hệ điều hành sau đó được *nạp phần đầu* của nó và thi hành tiến trình đầu tiên. 
- Sau khi khởi động hoàn tất, nhân hệ điều hành *không được thực thi ngay lập tức*, nó chỉ nằm trong *lời trả lời cho sự kiện bên ngoài*.
- Ngoài ra, nhân hệ điều hành còn cung cấp một vòng lặp được thực thi bất cứ lúc nào mà không có tiến trình nào được thực thi; được gọi là *tiến trình nhàn rỗi*.  
![](https://www.google.com.vn/search?q=Nhân+hệ+điều+hành&tbm=isch&tbs=rimg:CaMqyFfuSYZcIjixYUjkD0x9VwV3nTbABLo05xStMHosizJ4A7_1G3m5_1dCF7cNKRi0UM1I9rYgi7_1UkkPkp9yAZTZioSCbFhSOQPTH1XEeanz0tJIq_1zKhIJBXedNsAEujQR1fOQ6Igkxg8qEgnnFK0weiyLMhH_16298Fhqd8CoSCXgDv8bebn90EWuEwx0uPerZKhIJIXtw0pGLRQwRfIcGLwFBE2UqEgnUj2tiCLv9SREdEHb8N9ITfyoSCSQ-Sn3IBlNmEXJOuOigJSti&tbo=u&sa=X&ved=2ahUKEwi2renMwqrcAhWJwI8KHT0-BVcQ9C96BAgBEBs&biw=1366&bih=635&dpr=1#imgrc=GKXm47WukF_atM:)  

# Hệ thống file
- Một hệ thống tập tin (file system - fs) là các phương pháp và cấu trúc dữ liệu mà một hệ điều hành sử dụng để lưu trữ các thông tin của các tập tin hay phần chia trên đĩa.  
- Linux được thiết kế và thi hành hệ thống tập tin mới được chứa trong nhân hệ điều hành Linux chuẩn được gọi là Second Extended File System (Ext2 fs).

|Hệ thống file|Chức năng|
|---|---|
|Ext2|**Không phải là file hệ thống *journaling***. Kế thừa các thuộc tính của file hệ thống cũ. Hỗ trợ dung lượng ổ cứng lên tới 2 TB. Phù hợp với những thiết bị lưu trữ bên ngoài.|  
|Ext3|**Căn bản chỉ là Ext2 đi kèm với journaling**. Ổ đĩa, phân vùng có thể dễ dàng được chuyển đổi giữa 2 chế độ mà không cần phải format như trước kia. Không hỗ trợ tính năng tạo disk snapshot, file được khôi phục sẽ rất khó để xóa bỏ sau này.|
|Ext4|Giảm bớt hiện tượng phân mảnh dữ liệu trong ổ cứng, hỗ trợ các file và phân vùng có dung lượng lớn..., Thích hợp với ổ SSD|
|XFS|Quản lý được file có kích thước là 9 Exabyte. Cho phép các ứng dụng duy trì được tốc độ truy xuất dữ liệu trên đĩa|  
> Journaling chỉ được sử dụng khi ghi dữ liệu lên ổ cứng và ghi thông tin vào phân vùng. Đồng thời, nó cũng khắc phục vấn đề xảy ra khi ổ cứng gặp lỗi trong quá trình này, nếu không có journal thì hệ điều hành sẽ không thể biết được file dữ liệu có được ghi đầy đủ tới ổ cứng hay chưa.

# Cấu trúc vật lý
- Tất cả các cấu trúc dữ liệu được đặt kích cỡ dựa trên kích thước một khối (block).  
- Hệ thống tập tin được chia thành những nhóm khối (block group)  
Tại đầu của mỗi nhóm khối có chứa các thông tin xác định vị trí, số khối và của các thông tin mô tả trạng thái hệ thống tập tin hiện hành, bao gồm các thông tin sau: 
  - Superblock: Chứa các thông tin cơ bản nhất và các thuộc tính của hệ thống tập tin, thí dụ như tổng số i-node, tổng số khối, trạng thái hệ thống tập tin … 
  - Group descriptors: Là một mảng cấu trúc, mỗi cấu trúc mô tả một nhóm khối, vị trí bảng i-node của nó, bản đồ khối và i-node …. 
  - Block bitmap: đặt tại khối đầu tiên của nhóm khối. Mỗi bit đại diện cho trạng thái hiện hành của khối trong nhóm khối đó.
  -	I-node bitmap: có chức năng tương tự như block bitmap, mỗi bit đại diện cho một i-node trong bảng i-node (i-node table). Mỗi một nhóm khối có một i- node bitmap 
  - I-node table: Bảng i-node được sử dụng để lưu vết tất cả các tập tin; vị trí, kích thước, kiểu và các quyền truy nhâp của tập tin đều được lưu trữ trong các i-node. Mỗi i-node có chứa thông tin về một tập tin vật lý riêng rẽ trên hệ thống. I-node có thể được xem như là một khối thông tin mô tả vị trí của nó trên đĩa, kích thước và chủ nhân của nó.  
  - Data block: Được sử dụng để lưu trữ nội dung của các tập tin, bao gồm danh sách các thư mục, các thuộc tính mở rộng, các symbolic link … 

# I-node
- I-node là một bảng có kích thước cố định được sử dụng để lưu trữ tất cả các thông tin về một tập tin, và mỗi tập tin chỉ có một i-node duy nhất.  

# Liên kết cứng và liên kết mềm
- Liên kết mềm chỉ chứa các thông tin của file vật lí mà nó trỏ đến, nó hoàn toàn không tham chiếu trực tiếp đến điểm nhập i-node của file này. Khi bạn xóa file gốc, file liên kết không còn ý nghĩa gì nữa, nhưng nếu xóa file liên kết mềm thì file gốc không ảnh hưởng.  
- Liên kết cứng sẽ tạo ra 1 file vật lí cùng trỏ đến mục nhập i-node của file vật lí gốc. Hai fle này hoàn toàn đồng đẳng với nhau. Nếu xóa file gốc thì dữ liệu không bị mất, nó chỉ mất khi không còn liên kết nào đến i-node nữa.  

# Hệ thống tập tin ảo
## Nguyên lý
- Nhân Linux có một lớp hệ thống tập tin ảo (Virtual File System – VFS).  
- VFS là một lớp gián tiếp, quản lý các lời gọi hệ thống hướng tập tin và gọi những chức năng cần thiết trong mã hệ thống tập tin vật lý để thực hiện nhập/xuất.  
> Khi một tiến trình phát sinh một lời gọi hệ thống hướng tập tin, nhân hệ điều hành gọi một chức năng được chứa trong VFS. Chức năng này quản lý các thao tác độc lập cấu trúc và chuyển hướng lời gọi tới một chức năng chứa trong mã hệ thống tập tin vật lý, nó có khả năng quản lý các thao tác phụ thuộc cấu trúc. Mã hệ thống tập tin sử dụng các chức năng trữ bộ đệm để yêu cầu nhập/xuất trên các thiết bị.  

## Cấu trúc
- VFS định nghĩa một bộ các chức năng mà  mọi hệ thống tập tin phải thực thi. Giao diện  này được tạo bởi một tập hợp các thao tác  liên kết với ba kiểu của đối tượng: hệ thống  tập tin, i-node, và các tập tin mở.  

# Thư mục
- Các thư mục được cấu trúc trong một cây có thứ bậc. Mỗi một thư mục có thể chứa các tập tin và các thư mục khác.  
- Mỗi một mục từ có cấu trúc rất đơn giản, bao gồm có hai trường: số i-node của tập tin và tên tập tin đó.  

# MEAN Stack
- MEAN Stack là sự kết hợp hài hoà của [M]ongoDB, [E]xpressJS,  [A]ngularJS, [N]odeJS và khiến cho việc xây dựng những ứng dụng web trở nên mạnh mẽ và đơn giản hơn.