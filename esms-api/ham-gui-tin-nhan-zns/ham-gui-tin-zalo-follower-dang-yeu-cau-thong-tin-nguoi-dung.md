# Hàm gửi tin Zalo Follower dạng Yêu cầu thông tin người dùng

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage\_V5\_post\_json/](http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage\_V5\_post\_json/)\
  Method: POST\
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage_V5_post_json/' \
--header 'Content-Type: text/plain' \
--header 'Cookie: ASP.NET_SessionId=qvprszqzkp5ocznen3koqgko' \
--data-raw '{
"ApiKey": "{ApiKey}",
"SecretKey": "{SecretKey}",
"OAID": "{OAID}",
"Sandbox":0,
"CallbackUrl":"{CallbackURL}",
    "Payload": {
        "recipient": {
            "user_id": "{UserID}"
        },
        "message": {
            "attachment": {
                "type": "template",
                "payload": {
                    "template_type": "request_user_info",
                    "elements": [
                        {
                            "title": "{Title}",
                            "subtitle": "{Subtitle}",
                            "image_url": "{ImageURL}"
                        }
                    ]
                }
            }
        }
    }
}'
```



* Thông tin request

<table><thead><tr><th width="236">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản.</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản.</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>User_id <mark style="color:red;">*</mark></td><td>Userid cần gửi đến, đây là userid của zalo.</td></tr><tr><td>Title<mark style="color:red;">*</mark></td><td>Tiêu đề hiển thị của template<br>Lưu ý: Hỗ trợ tối đa 100 ký tự</td></tr><tr><td>Subtitle<mark style="color:red;">*</mark></td><td>Tiêu đề phụ của template<br>Lưu ý: Hỗ trợ tối đa 500 ký tự</td></tr><tr><td>ImageUrl<mark style="color:red;">*</mark></td><td>Link hình ảnh, chấp nhận link đuôi PNG và JPG</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn này.</td></tr><tr><td>Sandbox</td><td>1: Tin thử nghiệm, không gửi tin nhắn, chỉ trả về kết quả SMS, tin không lưu hệ thống và không trừ tiền.<br>0: Không thử nghiệm, tin đi thật.</td></tr></tbody></table>

* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "f829b7a6687e4a9282f2a02e157fc40386"
}
```

* Thông tin kết quả trả về

|       |                                                                                                   |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |
