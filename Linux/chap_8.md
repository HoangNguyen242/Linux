# Bộ nhớ trao đổi
- Linux chia RAM thành các vùng nhớ được gọi là các trang liên kết.  
- **Swapping** là quá trình mà một trang của bộ nhớ được sao chép vào một không gian có sẵn trên đĩa cứng, được gọi là không gian hoán đổi, để tự giải phóng khỏi bộ nhớ.  
- Trao đổi là cần thiết vì hai lý do:  
  1. Khi hệ thống yêu cầu nhiều bộ nhớ hơn bộ nhớ cứng, hạt nhân sẽ di chuyển các trang ít được sử dụng hơn vào vùng trao đổi và cấp bộ nhớ ram cho ứng dụng tại thời điểm đó yêu cầu bộ nhớ.  
  2. Một số lượng đáng kể các trang được ứng dụng sử dụng trong giai đoạn khởi động của nó và sau đó không bao giờ được sử dụng lại.  

# Hoán đổi kích thước (Swap dimensioning)
|Dung lượng Ram trong hệ thống|Recommended swap space|Recommended swap space if allowing for hibernation|
|---|---|---|
| <2GB | Gấp 2 lần dung lượng Ram | Gấp 3 lần dung lượng Ram |
| >2GB - 8GB | Bằng dung lượng Ram | Gấp 2 lần dung lượng Ram |
| >8GB - 64GB | Bằng một nửa dung lượng Ram | Gấp 1.5 lần dung lượng Ram |
| > 64GB | 4GB dung lượng trao đổi | Không cần thêm dung lượng |

# Thêm vùng trao đổi dưới dạng tệp
```
dd if=/dev/zero of=/var/swapfile bs=1M count=2048
chmod 600 /var/swapfile
mkswap /var/swapfile
echo /var/swapfile none swap defaults 0 0 | sudo tee -a /etc/fstab
swapon -a
```