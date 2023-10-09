---
description: >-
  Hàm cho phép bạn gọi API tự động tạo ra mã code OTP và sau đó gửi đến người
  dùng bằng brandname. Với OTP code là ngẫu nhiên. Phần code này do ViHAT xử lí.
---

# Hàm gencode V4

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V4\_get?Phone={Phone}\&ApiKey={ApiKey}\&SecretKey={SecretKey}\&TimeAlive={TimeAlive}\&NumCharOfCode={NumCharOfCode}\&Brandname={Brandname}\&Type=2\&message={Content}](http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V4\_get?Phone={Phone}\&ApiKey={ApiKey}\&SecretKey={SecretKey}\&TimeAlive={TimeAlive}\&NumCharOfCode={NumCharOfCode}\&Brandname={Brandname}\&Type=2\&message={Content})\
  Method: GET

{% code overflow="wrap" %}
```
curl --location -g --request GET 'http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode_V4_get?Phone={Phone}&ApiKey={ApiKey}&SecretKey={SecretKey}&TimeAlive={TimeAlive}&NumCharOfCode={NumCharOfCode}&Brandname={Brandname}&Type=2&message={Content}&IsNumber=0'
```
{% endcode %}

* Thông tin request

| Biến          | Định nghĩa                                                                                                                                                                                                                                                |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Phone         | Số điện thoại nhận tin                                                                                                                                                                                                                                    |
| ApiKey        | ApiKey của tài khoản                                                                                                                                                                                                                                      |
| SecretKey     | Secretkey của tài khoản                                                                                                                                                                                                                                   |
| TimeAlive     | Thời gian hiệu lực của mã code. Đơn vị tính: Phút. Giới hạn từ 2 phút đến 15 phút                                                                                                                                                                         |
| NumCharOfCode | Số lượng ký tự của mã code. Mặc định khi không truyền là 6 ký tự                                                                                                                                                                                          |
| Brandname     | <p>Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p>                                                                                                   |
| Type          | 2: Gửi chăm sóc khách hàng                                                                                                                                                                                                                                |
| message       | <p>Nội dung tin nhắn<br>Thay thế mã code OTP bằng {OTP}<br>- Ví dụ: <br>Muốn nhận tin nhắn về máy với nội dung:<br>"686868 la ma xac minh dang ky Baotrixemay cua ban". Thì ở mục message truyền: "{OTP} la ma xac minh dang ky Baotrixemay cua ban".</p> |
| IsNumber      | <p>0: code chứa chữ và số<br>1: code chỉ chứa số</p>                                                                                                                                                                                                      |

* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

* Thông tin kết quả trả về

| Biến  | Định nghĩa                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |

