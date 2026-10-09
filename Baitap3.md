\## Sơ đồ luồng IPO



* Input

\- Yêu cầu thiết lập hạ tầng smart-farm



\- Các tên thư mục lồng nhau (data\\logs, code)



\- Các tệp cần tạo (config.json, sensors.py, .env)



\- Yêu cầu sao lưu dữ liệu



* &#x20;Process



New-Item với tham số -Force để tạo cây thư mục lồng nhau.



Chuyển hướng hoặc tạo hàng loạt tệp cấu hình bằng New-Item.



Copy-Item với tham số -Recurse để sao chép toàn bộ thư mục kèm dữ liệu bên trong.



* Out put



Sử dụng các câu lệnh PowerShell tối ưu:



Cây thư mục hoàn chỉnh smart-farm



Các tệp cấu hình, file ẩn đầy đủ

\---



\## Danh sách các câu lệnh Powershell đã sử dụng

Yêu Cầu 1 đã sử dụng lệnh

* New-Item -ItemType Directory -Force -Path "smart-farm\\data\\logs", "smart-farm\\code"
* 

Yêu Cầu 2 đã sử dụng lệnh

* New-Item config.json, sensors.py, .env; (Get-Item .env).Attributes = 'Hidden'



Yêu cầu 3 đã sử dụng lệnh

* Copy-Item -Recurse -Force "smart-farm\\code" -Destination "smart-farm\\backup\\code\_v1"





\---

\#GIẢI THÍCH 



\-New-Item: Đây là lệnh dùng để tạo mới một đối tượng (có thể là file hoặc thư mục).



\-ItemType Directory: Khai báo rõ loại đối tượng muốn tạo là Thư mục (Directory).



\-Force: Tham số tương tự cờ -p trong lệnh mkdir -p của Linux/macOS.



\-Path ...: Đường dẫn tới các thư mục cần tạo. Bạn có thể truyền nhiều đường dẫn cách nhau bởi dấu phẩy để tạo cùng lúc nhiều nhánh thư mục.



\-get-item là tìm và chỉ định chính xác file đó. attributes là truy cập vào danh sách đặc tính



\-Copy-Item: Lệnh chuyên dụng để sao chép file hoặc thư mục trong PowerShell (tương tự lệnh cp trên Linux).



\-Recurse: Đây là tham số bắt buộc khi bạn muốn sao chép một thư mục mà bên trong nó vẫn còn chứa các file hoặc thư mục con khác (sao chép đệ quy toàn bộ cây thư mục). Nếu thiếu -Recurse, PowerShell sẽ bỏ qua các file bên trong và chỉ báo lỗi hoặc sao chép rỗng.



\-Force: Ép buộc ghi đè nếu thư mục đích code\_v1 đã tồn tại từ trước.



\-Destinat\\-on: Đường dẫn đích đến nơi chứa bản sao (backup\\code\_v1).

