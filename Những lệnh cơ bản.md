# Tra cứu ứng dụng
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
===
