# Hàm gửi tin Zalo Follower dạng Button

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage\_V5\_post\_json/](http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage\_V5\_post\_json/)\
  Method: POST\
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage_V5_post_json/' \
--header 'Content-Type: text/plain' \
--header 'Cookie: ASP.NET_SessionId=asfgp2dj1kt4kbg1yzuo35ky' \
--data-raw '{
    "ApiKey": "{ApiKey}",
    "SecretKey": "{SecretKey}",
    "OAID": "{OAID}",
    "CallbackUrl": "{CallbackUrl}",
    "Payload": {
        "recipient": {
            "user_id": "{user_id}"
        },
        "message": {
            "text": "{text}",
            "attachment": {
                "type": "template",
                "payload": {
                    "buttons": [
                        {
                            "title": "{title}",
                            "payload": {
                                "url": "{url}"
                            },
                            "type": "oa.open.url"
                        },
                        {
                            "title": "{title}",
                            "type": "oa.query.show",
                            "payload": "{payload}"
                        },
                        {
                            "title": "{title}",
                            "type": "oa.query.hide",
                            "payload": "{payload}"
                        },
                        {
                            "title": "{title}",
                            "type": "oa.open.sms",
                            "payload": {
                                "content": "{content}",
                                "phone_code": "{phone_code}"
                            }
                        },
                        {
                            "title": "{title}",
                            "type": "oa.open.phone",
                            "payload": {
                                "phone_code": "{phone_code}"
                            }
                        }
                    ]
                }
            }
        }
    }
}'
```



* Thông tin request

| Biến                                              | Định nghĩa                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>         | ApiKey của tài khoản.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| SecretKey <mark style="color:red;">\*</mark>      | Secretkey của tài khoản.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| OAID <mark style="color:red;">\*</mark>           | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| User\_id <mark style="color:red;">\*</mark>       | Userid cần gửi đến, đây là userid của zalo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Content <mark style="color:red;">\*</mark>        | <p>Nội dung tin nhắn<br>Lưu ý: Khi gửi dạng tin nhắn này khách hàng vui lòng liên hệ cho nhân viên kinh doanh để được hỗ trợ về content.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Template\_type <mark style="color:red;">\*</mark> | Loại template                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Elements <mark style="color:red;">\*</mark>       | <p></p><ul><li>Tittle: mô tả của action.</li><li>Default_action<br>- Type oa.open.url: Url sẽ được mở trong ứng dụng Zalo khi người quan tâm bấm vào action<br>- Type oa.open.sms: Khi người quan tâm click vào action, cửa sổ sms trên điện thoại của người quan tâm sẽ được mở với 2 thông tin sẵn có là phone code và nội dung tin nhắn trong data.<br>- Type oa.query.hide: Payload là một chuỗi ký tự ví dụ “#eSMS”. Khi người quan tâm bấm vào action, hệ thống sẽ gửi một tin nhắn có nội dung chứa trong data từ người quan tâm đến Official Account. Tin nhắn này sẽ bị ẩn trên cửa sổ chat trên máy của người quan tâm.<br>- Type oa.query.show: Payload là một chuỗi ký tự ví dụ “#eSMS”. Khi người quan tâm bấm vào action, hệ thống sẽ gửi một tin nhắn có nội dung chứa trong data từ người quan tâm đến Official Account. Tin nhắn này sẽ hiện trên cửa sổ chat trên máy của người quan tâm.<br>- Type oa.open.phone: Khi người quan tâm click vào action, cửa sổ call trên điện thoại của người quan tâm sẽ được mở với thông tin số điện thoại là giá trị của phone_code. </li></ul> |
| CallbackUrl                                       | eSMS sẽ trả về kết quả của tin nhắn này.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

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
