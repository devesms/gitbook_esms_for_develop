# Gửi tin chăm sóc khách hàng (TypeSMS 2) dạng POST TEXT

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4/](http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4/)\
  Method: POST\
  Content Type: text/plain

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4/' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Cookie: ASP.NET_SessionId=nsvdja0b4rcfjf1o4szjxno0' \
--data-raw '<RQST><APIKEY><{ApiKey}</APIKEY>
<SECRETKEY>{SecretKey}</SECRETKEY>
<CONTENT>{Content}</CONTENT>
<SMSTYPE>2</SMSTYPE>
<BRANDNAME>{Brandname}</BRANDNAME>
<CONTACTS>
<CUSTOMER><PHONE>{Phone}</PHONE></CUSTOMER>
</CONTACTS>
</RQST>'
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
