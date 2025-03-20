---
description: >-
  Giải pháp Multi-Channel Messaging API cho phép bạn gửi tin nhắn đến khách hàng
  đi qua các kênh giao tiếp khác nhau như Zalo, SMS, Viber theo các thứ tự ưu
  tiên.
---

# Hàm gửi tin nhắn MultiChanel

* HTTP request\
  URL: [https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/](https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/)\
  Method: POST\
  Content Type: application/json

{% code overflow="wrap" %}
```
curl --location --request POST 'https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/' \
--header 'Content-Type: application/json' \
--data-raw '{
    "ApiKey": "{ApiKey}",
    "SecretKey": "{SecretKey}",
    "Phone": "{Phone}",
    "Channels": [
        "zalo",
        "sms"
    ],
    "Data": [
        {
            "TempID": "{TempID}",
            "Params": ["param1","param2","param3",....],
            "OAID": "{OAID}",
            "campaignid": "{campaignid}",
            "CallbackUrl": "{CallbackUrl}",
            "RequestId":"{{RequestId}}",
            "Sandbox":"{{Sandbox}}"
        },
        {
            "Content": "{Content}",
            "IsUnicode": {IsUnicode},
            "SmsType": {SmsType},
            "Brandname": "{Brandname}",
            "CallbackUrl": "{CallbackUrl}",
            "RequestId":"{{RequestId}}",
            "Sandbox":"{{Sandbox}}"
        }
    ]
}'
```
{% endcode %}

* Thông tin request

<table><thead><tr><th width="236">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản</td></tr><tr><td>Phone <mark style="color:red;">*</mark></td><td>Số điện thoại nhận tin</td></tr><tr><td>Params <mark style="color:red;">*</mark></td><td><p></p><p>Giá trị cần truyền cho các biến trong Template *Lưu ý:</p><ol><li>Các tham số truyền vào phải đúng thứ tự như template bạn đăng ký</li><li>Nếu tham số trùng nhau chỉ cần truyền vào một tham số</li></ol></td></tr><tr><td>TempID <mark style="color:red;">*</mark></td><td>Template của Zalo OA mà khách hàng đăng kí với eSMS</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>RequestId</td><td>ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. <br>Ví dụ: RequestId=123456</td></tr><tr><td>campaignid</td><td>Tên chiến dịch gửi tin, tối đa 254 ký tự</td></tr><tr><td>RequestId</td><td>ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. <br>Ví dụ: RequestId=123456</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn.</td></tr><tr><td>Content <mark style="color:red;">*</mark></td><td>Nội dung tin nhắn</td></tr><tr><td>IsUnicode</td><td>Gửi tin nhắn có dấu<br>0: Gửi tin không dấu<br>1: Gửi tin nhắn có dấu</td></tr><tr><td>Brandname <mark style="color:red;">*</mark></td><td>Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>SmsType <mark style="color:red;">*</mark></td><td>2: Tin CSKH</td></tr><tr><td> Sandbox</td><td>0: Gửi tin đi thật <br>1: Tin thử nghiệm. không lưu tin và không đi tin. Chỉ để kiểm tra kết nối.</td></tr></tbody></table>

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
