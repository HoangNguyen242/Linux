# Những lệnh cơ bản

## I. Tra cứu ứng dụng
- Phụ thuộc vào các bản phân phối, chương trình và các phần mềm được cài đặt trong các thư mục khác nhau. Tóm lại, các chương trình thực thi phải nằm trong các thư mục sau:  

> /bin  
/usr/bin  
/sbin  
/usr/sbin  
/opt.  

- Một cách để định vị chương trình là dùng tiện ích which.  

> $ which diff  
/usr/bin/diff

- Nếu which không tìm được chương trình, whereis là lựa chọn tốt vì phạm vi tìm kiếm của nó rộng hơn các mục hệ thống.  

> $ whereis diff  
diff: /usr/bin/diff /usr/share/man/man1/diff.1.gz.  
  
## II. Truy cập thư mục  

|Lệnh|Chức năng|  
|-------------|-------------|  
|cd|Trở về thư mục chính|  
|cd ..| Trở về thư mục gốc|  
|cd -|Trở về thư mục trước|  
|cd /|Từ thư mục hiện tại vào thư mục gốc (/)|  
  
## III. Khám phá thư mục
  
|Lệnh|Chức năng|  
|-------|-----------|  
|ls 	  |Liệt kê nội dung thư mục|  
|ls –a  |Liệt kê tất cả các tệp bao gồm các tệp và thư mục ẩn|  
|tree   |Hiển thị cây của thư mục|  
|tree -d|Liệt kê các thư mục và loại bỏ tên tệp|  
  
## IV. Liên kết cứng và liên kết tượng trưng
  
- Lệnh `ln` có thể được sử dụng để tạo liên kết cứng hoặc liên kết mềm, gọi là liên kết tượng trưng (Symbolic links) hay symlinks.  

> Giả sử file1.txt đã tồn tại, một liên kết cứng, gọi là file2.txt được tạo bằng lệnh:  
``` # ln file1.txt file2.txt ```  

- Hại tệp này bây giờ gần như tồn tại. Nhưng việc kiểm tra danh sách tệp cho thấy điều này không hoàn toàn chính xác  

```# ls -l file*
-rw-r--r--. 2 root root 604 Feb 16 11:49 file1.txt
-rw-r--r--. 2 root root 604 Feb 16 11:49 file2.txt
# ls -li file*
134415251 -rw-r--r--. 2 root root 604 Feb 16 11:49 file1.txt
134415251 -rw-r--r--. 2 root root 604 Feb 16 11:49 file2.txt
```
- -i trong dòng đầu tiên dùng để in ra i-nút, có số lượng khác nhau duy nhất với mỗi tệp, và trường này giống nhau với cả 2 tệp.* **Điều thực sự xảy ra ở đây là một tập tin nhưng có hai tên liên kết** *.

- Liên kết mềm có thể trỏ đến các đối tượng ngay cả trên các tập tin khác nhau (hoặc các phân vùng) có thể có hoặc không tồn tại. Trong trường hợp liên kết không trỏ đến một đối tượng đang tồn tại, bạn sẽ có được một liên kết treo lơ lửng.

> Nguồn: [Basic Commands](https://github.com/lacoski/linux-notes/blob/master/content/basic_commands.md)
