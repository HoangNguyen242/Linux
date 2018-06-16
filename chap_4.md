# File permissions
- Trong Linux và các hệ điều hành UNIX khác, mọi tệp đều được liên kết với người dùng là chủ sở hữu. 
- Mỗi tệp cũng được liên kết với nhóm có sở thích trong tệp và một số quyền hoặc quyền nhất định: đọc, ghi và thực thi.
|Lệnh|Chức năng|
|-------|-----------|
|chown|Được sử dụng để thay đổi quyền sở hữu người dùng của tệp hoặc thư mục|  
|chgrp|Được sử dụng để thay đổi quyền sở hữu nhóm|  
|chmod|Được sử dụng để thay đổi quyền trên tệp|  

- Tệp có ba loại quyền: đọc (r), viết (w), thực thi (x). Chúng thường được biểu diễn theo thứ tự sau rwx.  
- Các quyền này ảnh hưởng đến ba nhóm chủ sở hữu: người dùng (u), nhóm (g) và những người khác (o). Có ba nhóm sau:  
|rwx:|rwx:|rwx|  
|----|----|---|  
|u:|g:|o|  
