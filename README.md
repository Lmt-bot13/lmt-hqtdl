Họ & tên: Lưu Minh Trí
MSSV: K235480106008
Lớp: K59KMT.K01
1. Tải xuống và cài đặt SQL Server 2025, tải xuống phiên bản Developer Link: (https://www.microsoft.com/vi-vn/sql-server/sql-server-downloads) Chọn phiên bản SQL Server 2025 Developer Không chọn Azure (nặng, không dùng đến), các tính năng mở rộng khác (tính năng) chọn tất cả Cài đặt với 2 kiểu đăng nhập (Chế độ hỗn hợp): Windows Authentication (nhớ Add Current User) và SQL Server Authentication (tên người dùng mặc định là sa, chỉ cần nhập mật khẩu 123 , ô ghi nhớ 2: Enter pass and Verify pass)
2. Cấu hình cho SQL Server làm việc ở cổng động (Cổng động), TCP: Enable+active có cho 127.0.0.1, chọn cổng động là 3xxxx với xxxx là 4 số cuối của sv mã hóa, (nếu cổng này đã mở sẵn trước đó bởi 1 ứng dụng khác thì hãy chọn cổng là 4xxxx hoặc 5xxxx)
   <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/52667008-2c45-4605-afe6-f782c7c02240" />
3. Kiểm tra xem dịch vụ SQL Server có đang chạy và mở cổng đã chọn đúng hay không? Sử dụng lệnh trên cmd: netstat -ano | findstr LISTENING để liệt kê các cổng mà máy tính đang mở, Nếu tìm thấy dòng: TCP 0.0.0.0:xxxx với xxxxx là cổng đã chọn ở bước 2 là OK.
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/2e12c83b-352e-4690-b2fc-bed8d9a8f651" />

4. Cài đặt SQL Server Management Studio Link tải SSMS: [https://learn.microsoft.com/en-us/ssms/install/install](https://learn.microsoft.com/en-us/ssms/install/install) 
5. Chạy phần mềm ssms để Đăng nhập vào SQL Server bằng 2 cách: Xác thực Windows và Xác thực máy chủ SQL. Tên máy chủ: localhost,xxxxx (với xxxxx là cổng đã chọn ở bước 2)
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/da081a05-a61b-411a-95d4-d933adfd83c4" />
 6. Sử dụng giao diện đồ họa của ssms: Tạo cơ sở dữ liệu mới (tạo cơ sở dữ liệu) với tên tùy ý, chọn Đường dẫn (nơi lưu trữ db) cho tệp lưu dữ liệu và tệp lưu nhật ký ở ổ ​​đĩa khác với ổ C. mở đường dẫn đã chọn xem 2 tệp đã tạo ra.
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/8d4ac0aa-143b-4a55-8000-4cdb1262fb3d" />
 7. Sử dụng giao diện đồ họa của ssms: Tạo bảng dữ liệu (tạo và thiết kế bảng) với tên bảng tùy ý, có các trường dữ liệu phù hợp với dữ liệu của mẫu dữ liệu tệp (CSV), với Khoá chính (Primary Key) là trường masv
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/80090325-ef06-4864-9d0e-19438c1cb433" />

8. Sử dụng họa tiết giao diện của ssms: Tìm cách nhập dữ liệu từ mẫu vào bảng vừa tạo.
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/79c6a415-31b7-4ae9-87a0-dbf76cb22a7e" />

9. Mở cửa sổ mới để nhập lệnh trong ssms: Lệnh kiểm tra xem số dòng của dữ liệu bảng sau khi nhập, kết quả sẽ ổn trong khoảng 12020 dòng.
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/5d28f552-4dd8-4e20-aa10-064c2eeff7b3" />

10. Trong cửa sổ mới để nhập lệnh: Gõ lệnh để thêm (chèn) 1 hàng vào bảng, với dữ liệu là thông tin cá nhân của sv đang làm bài (mỗi sv sẽ luôn khác nhau ở bước này).
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/61cd1c0e-8f3a-4a8d-856e-c4e1bb1c0318" />

11. Trong cửa sổ mới để nhập lệnh: Gõ lệnh để cập nhật(update) trường noisinh thành 'Sao Hoaả' cho những dòng có noisinh và diachi đều là NULL.
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/9019f824-0e4d-4a3b-bb55-b3afa2efaa9d" />

12. Sử dụng giao diện đồ họa của ssms: Tạo bảng SaoHoa bao gồm những sinh viên có nơi sinh ở 'Sao Hoa', từ khóa gợi ý: sử dụng 1 câu lệnh: SELECT + INTO
<img width="1919" height="1078" alt="image" src="https://github.com/user-attachments/assets/eb9c1380-ffde-42d4-8d35-81c505ef38b7" />

13. Trong cửa sổ mới để gõ lệnh: Gõ lệnh xóa (xóa) trong bảng SaoHoa những sinh viên cùng họ với em, em họ Luu sẽ xóa những sinh viên Luu.
<img width="1919" height="1071" alt="image" src="https://github.com/user-attachments/assets/ba1d11c0-e22e-4567-b57e-c59b9fc1e26e" />

14. Sử dụng giao diện đồ họa của ssms: Xuất toàn bộ kết quả của các bước 6,7,8,9,10,11,12,13 ra file dulieu.sql , từ khóa mẹo ý: sử dụng tính năng GEN SCRIPT struct+data cho cơ sở dữ liệu
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/774ba4e8-0533-41d2-91a2-2e03966e35b9" />


15. Sử dụng giao diện hoạt động của ssms: Xóa csdl đã tạo, sau khi xóa thành công, kiểm tra tại đường dẫn (đường dẫn chọn ở bước 6) xem còn tồn tại 2 file của bước 6 không?
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/f40dd645-85d9-4812-a5c5-17aa6ac9e5b4" />


16. Tạo mới cửa sổ để nhập lệnh: mở tệp dulieu.sql của bước 15, chạy toàn bộ các lệnh này. LÀM MỚI danh sách cơ sở dữ liệu cây => kiểm tra kết quả được tạo tương thích với các bước 6,7,8,9,10,11,12,13.

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/4ac71b02-5009-4095-bbc6-9056bdf9493c" />

17. Upload file dulieu.sql lên github repo của em (repository mà em đang edit file README.md)
