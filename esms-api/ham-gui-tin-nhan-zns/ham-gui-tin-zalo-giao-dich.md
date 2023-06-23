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
                        "image_icon": "{image_icon}",
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

<table><thead><tr><th width="206">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản.</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản.</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>user_id <mark style="color:red;">*</mark></td><td>Userid cần gửi đến, đây là userid của zalo.</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn này.</td></tr><tr><td>template_type<mark style="color:red;">*</mark></td><td><p>Loại template:<br>1. transaction_billing<br>2. transaction_order<br>3. transaction_reward<br>4. transaction_contract<br>5. transaction_booking<br>6. transaction_membership<br>7. transaction_event<br>8. transaction_transaction<br>9. transaction_account<br>10. transaction_internal<br>11. transaction_partnership<br>12. transaction_education<br>13. transaction_rating</p><p></p></td></tr><tr><td>language</td><td><p>Ngôn ngữ sử dụng của tin<br>Giá trị nhận vào:</p><ul><li>language = <strong>VI</strong></li></ul><p>hoặc</p><ul><li>language = <strong>EN</strong></li></ul><p>Khi chọn ngôn ngữ các nội dung mặc định của mẫu tin sẽ chuyển sang ngôn ngữ tương ứng</p></td></tr><tr><td>image_url<mark style="color:red;">*</mark></td><td>Đường link hình ảnh đính kèm.</td></tr><tr><td>align</td><td><p></p><p>Chấp nhận 3 giá trị</p><ul><li>left (hoặc để trống): canh lề bên trái</li><li>center: canh lề giữa</li><li>right: canh lề bên phải</li></ul></td></tr><tr><td>table<mark style="color:red;">*</mark></td><td><p><strong>Cấu trúc 1 phần tử trong table là:</strong><br>{<br> "key": "giá trị của key" // maxlength = 25 <br>"value": "giá trị của value" // maxlength = 100<br> }<br><mark style="color:red;">Trong đó bắt buộc phải có 1 trong 2 phần tử dưới đây:</mark><br>VI: <br>{ "key": "Mã..." // bắt đầu là "Mã", dùng định danh người nhận "value": "Giá trị tự do" }</p><p>EN:<br> { "key": "...Code..." // bắt buộc có chứa "Code" trong key "value": "Giá trị tự do" }<br><mark style="color:red;">Hoặc:</mark><br>VI:</p><p> { "key": "Tên khách hàng" // key có giá trị cố định "Tên khách hàng" "value": "Giá trị tự do" }</p><p>EN:</p><p> { "key": "Customer Name" // key có giá trị cố định "Customer Name" "value": "Giá trị tự do" }<br><mark style="color:red;">Key “Trạng thái” / “Status” là key duy nhất hiện tại được phép sử dụng tham số “Style”:</mark><br>VN: { "key": "Trạng thái" // key có giá trị cố định "Trạng thái" "value": "Giá trị tự do" "style": "yellow" // Giá trị hợp lệ: green, blue, yellow, red, grey }</p><p>EN: { "key": "Status" // key có giá trị cố định "Status" "value": "Giá trị tự do" "style": "yellow" // Giá trị hợp lệ: green, blue, yellow, red, grey }<br><em><strong>****Lưu ý: có thể khai báo thêm tối đa 5 phần tử tùy ý.</strong></em><br></p></td></tr><tr><td>button</td><td>Có thể thêm tối đa 4 dòng</td></tr></tbody></table>

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
