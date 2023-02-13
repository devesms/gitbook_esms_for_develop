# Gửi tin chăm sóc khách hàng (TypeSMS 2) dạng POST X-Form

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post/](http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post\_json/)\
  Method: POST\
  Content Type: application/x-www-form-urlencoded

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post/' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'Phone={Phone}' \
--data-urlencode 'Content={Content}' \
--data-urlencode 'Apikey={ApiKey}' \
--data-urlencode 'SecretKey={SecretKey}' \
--data-urlencode 'SmsType=2' \
--data-urlencode 'Brandname={Brandname}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                              |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Phone <mark style="color:red;">\*</mark>     | Số điện thoại nhận tin                                                                                                                                  |
| Content <mark style="color:red;">\*</mark>   | Nội dung tin nhắn                                                                                                                                       |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                    |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                                                                                                 |
| SmsType <mark style="color:red;">\*</mark>   | <p>Loại tin nhắn<br>2: Tin CSKH</p>                                                                                                                     |
| Brandname <mark style="color:red;">\*</mark> | <p>Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |

* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

* Thông tin kết quả trả về

|       |                                                                                                   |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |

