# Cách Sử Dụng Vi
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
