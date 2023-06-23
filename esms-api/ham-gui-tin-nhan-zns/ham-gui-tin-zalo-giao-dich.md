# Hàm gửi tin Zalo Giao dịch

* HTTP request\
  URL: [http://rest.esms.vn/mainservice.svc/json/SendZaloFollowerMessage\_V5\_post\_json/](http://rest.esms.vn/mainservice.svc/json/SendZaloFollowerMessage\_V5\_post\_json/)\
  Method: POST\
  Content Type: application/json

<pre><code><strong>curl --location 'http://rest.esms.vn/mainservice.svc/json/SendZaloFollowerMessage_V5_post_json/' \
</strong>--header 'Content-Type: text/plain' \
--header 'Cookie: ASP.NET_SessionId=vhuwzz3ye4h3b34uwlel31b1; ASP.NET_SessionId=vhuwzz3ye4h3b34uwlel31b1' \
--data '{
    "ApiKey": "{ApiKey}",
    "SecretKey": "{SecretKey}",
    "OAID": "{OAID}",
    "CallbackUrl": "{CallbackUrl}",
    "Payload": {
        "recipient": {
            "user_id": "{user_id}"
        },
        "message": {
            "attachment": {
                "type": "template",
                "payload": {
                    "template_type": "{template_type}",
                    "language": "{language}",
                    "elements": [
                        {
                            "image_url": "{image_url}",
                            "type": "banner"
                        },
                        {
                            "type": "header",
                            "content": "{content}",
                            "align": "{align}"
                        },
                        {
                            "type": "text",
                            "align": "{align}",
                            "content": "{content}"
                        },
                        {
                            "type": "table",
                            "content": [
                                {
                                    "value": "{value}",
                                    "key": "{key}"
                                },
                                {
                                    "value": "{value}",
                                    "key": "{key}"
                                },
                                {
                                    "style": "{style}",
                                    "value": "{value}",
                                    "key": "{key}"
                                },
                                {
                                    "value": "{value}",
                                    "key": "{key}"
                                },
                                {
                                    "value": "{value}",
                                    "key": "{key}"
                                },
                                {
                                    "value": "{value}",
                                    "key": "{key}"
                                }
                            ]
                        },
                        {
                            "type": "text",
                            "align": "{align}",
                            "content": "{content}"
                        }
                    ],
                    "buttons": [
                        {
                            "title": "{title}",
                            "image_icon": "{image_icon}",
                            "type": "oa.open.url",
                            "payload": {
                                "url": "{url}"
                            }
                        },
                        {
                            "title": "{title}",
                            "image_icon": "{image_icon}",
                            "type": "oa.query.show",
                            "payload": "{payload}"
                        },
                        {
                            "title": "OPEN SMS",
                            "type": "oa.open.sms",
                            "payload": {
                                "content": "{content}",
                                "phone_code": "{phone_code}"
                            }
                        },
                    
                        {
                        "title": "{title}",
                        "image_icon": "https://minio.esms.vn/shared/ae9c1c34-a429-47a6-89a3-b7031c6b03fc20-png-trai-tim-chat-luong-cao-tuyet-dep-ks687-3.png",
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
</code></pre>



* Thông tin request

<table><thead><tr><th width="206">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản.</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản.</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>User_id <mark style="color:red;">*</mark></td><td>Userid cần gửi đến, đây là userid của zalo.</td></tr><tr><td>Title<mark style="color:red;">*</mark></td><td>Tiêu đề hiển thị của template<br>Lưu ý: Hỗ trợ tối đa 100 ký tự</td></tr><tr><td>Subtitle<mark style="color:red;">*</mark></td><td>Tiêu đề phụ của template<br>Lưu ý: Hỗ trợ tối đa 500 ký tự</td></tr><tr><td>ImageUrl<mark style="color:red;">*</mark></td><td>Link hình ảnh, chấp nhận link đuôi PNG và JPG</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn này.</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr></tbody></table>

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
