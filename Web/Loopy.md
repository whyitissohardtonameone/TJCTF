![Screenshot 2025-06-08 223222](https://github.com/user-attachments/assets/b7fae42c-b52f-4d92-bded-e66ae7a987ec)
Đề bài yêu cầu ta truy cập vào page admin bằng cổng 5000

Đầu tiên ấn vào trang web

![image](https://github.com/user-attachments/assets/b601ac7c-0b58-4561-b8bb-3d502f19796c)

Trang web này trả về cho ta HTML content của 1 trang web bất kì 

![image](https://github.com/user-attachments/assets/838d6be6-4951-4250-8f96-825b97427884)

Có vẻ trang web phải lấy dữ liệu từ một trang web bên ngoài (HTML content). Điển hình của lỗ hổng SSRF (Server Side Request Forgery).

Ta thử một payload để truy cập vào page admin. 

`http://127.0.0.1:5000/admin`

![image](https://github.com/user-attachments/assets/0818c1f2-912f-42c3-a057-403bc7a8d30c)

Có vẻ trang web đã filter url, chặn các thành phần liên quan đến truy cập vào máy chủ.

Anw, cái gì khó có cheatsheat lo, ta đi tìm một payload không bao gồm các chuỗi bị filter kia, và ta có:

`https://highon.coffee/blog/ssrf-cheat-sheet/`

`0x7f000001/` - Một phiên bản mã hóa HEX của 127.0.0.1

Thay vào payload ban đầu:
`http://0x7f000001:5000/admin`
![image](https://github.com/user-attachments/assets/c8ee0c6c-eb55-4b69-8b88-d02ea9875b7a)
tjctf{i_l0v3_ssssSsrF_9o4a8}
