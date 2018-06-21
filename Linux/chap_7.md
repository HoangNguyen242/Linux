# Bản phát hành Linux và thông tin hệ thống
- Quản trị viên hệ thống Linux cần nhận thông tin từ hệ thống.
- Một số lệnh hữu ích: 
  - Phát hành và phân phối Linux:  
    ```
    # cat /etc/*release  
    CentOS Linux release 7.0.1406 (Core)  
    NAME="CentOS Linux"  
    VERSION="7 (Core)"  
    ID="centos"  
    ID_LIKE="rhel fedora"  
    VERSION_ID="7"  
    PRETTY_NAME="CentOS Linux 7 (Core)"  
    ANSI_COLOR="0;31"  
    CPE_NAME="cpe:/o:centos:centos:7"  
    HOME_URL="https://www.centos.org/"  
    BUG_REPORT_URL="https://bugs.centos.org/"  
    CentOS Linux release 7.0.1406 (Core)  
    ```
  - Phiên bản hạt nhân
    ```
    # uname -r
    3.10.0-123.13.2.el7.x86_64
    ```
  - Thông tin bộ nhớ
    ```
    # head /proc/meminfo
    MemTotal:        3776748 kB
    MemFree:         2230496 kB
    MemAvailable:    2782088 kB
    Buffers:            1452 kB
    Cached:           652196 kB
    SwapCached:            0 kB
    Active:          1069616 kB
    Inactive:         193056 kB
    Active(anon):     609504 kB
    Inactive(anon):     8304 kB
    ```
  - Hệ thống file
    ```
    # df -h
    Filesystem         Dimens. Usati Disp. Uso% Montato su
    /dev/sda1          12G     6,2G  4,9G  56%      /
    /dev/small-db02    5,9G    2,6G  3,0G  46%      /db02
    /dev/small-db01    5,0G    3,6G  1,2G  77%      /db01
    /dev/small-db05    7,8G    1,2G  6,2G  17%      /db05
    /dev/small-db03    39G     5,4G   32G  15%      /db03                      
    /dev/small-db04    30G     2,5G   26G   9%      /db04
    ```

  - Đếm số lượng CPU
    ```
    # cat /proc/cpuinfo | grep model | uniq -c
        2 model name      : Intel(R) Core(TM)2 Duo CPU     E8500  @ 3.16GHz
    ```

# Hệ thống tập tin proc (The proc Filesystem)
- Hệ thống tập tin /proc chỉ chưa tệp ảo chỉ tồn tại trong bộ nhớ.  
- Hệ thống tập tin này chứa các tập tin và thư mục bắt chước cấu trúc hạt nhân và thông tin cấu hình.  
- It doesn't contain real files but runtime system information.
>Hệ thống tập tin / proc rất hữu ích vì thông tin mà nó báo cáo chỉ được thu thập khi cần và không cần lưu trữ trên đĩa.  

# Tên máy chủ
- Tên máy chủ xác định máy trong miền.  
`# cat /etc/hostname`  
- Set a new host name
`# hostname NEW_NAME`  