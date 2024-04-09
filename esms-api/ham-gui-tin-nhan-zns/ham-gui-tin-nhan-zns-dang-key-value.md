# Hàm gửi tin nhắn ZNS dạng Key - Value

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendZaloMessage\_V5\_post/](http://rest.esms.vn/MainService.svc/json/SendZaloMessage\_V5\_post/)\
  Method: POST\
  Content Type: application/json

{% code overflow="wrap" %}
```
curl --location --request POST 
'http://rest.esms.vn/MainService.svc/json/SendZaloMessage_V5_post/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=t4fvukdmjjn2bqytjdgqvkks' \
--data '{
    "ApiKey": "{ApiKey}",
    "SecretKey": "{SecretKey}",
    "OAID": "{OAID}",
    "Phone": "{Phone}",
    "TempData": [
        {
            "key": "{key1}",
            "value": "{value1}"
        },
        {
            "key": "{key2}",
            "value": "{value2}"
        }
    ],
    "SendDate": "{SendDate}",
    "TempID": "{TempID}",
    "campaignid": "{campaignid}",
    "Sandbox": "0",
    "CallbackUrl": "{CallbackUrl}"
}'
```
{% endcode %}



* Thông tin request

<table><thead><tr><th width="236">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>Phone <mark style="color:red;">*</mark></td><td>Số điện thoại người nhận.</td></tr><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản.</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản.</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>TempData<mark style="color:red;">*</mark></td><td>Bao gồm tên biến và giá trị biến trong Template:<br>key: Tên biến (bắt buộc phải giống trong Template đã đăng ký)<br>value: Giá trị biến</td></tr><tr><td>SendDate</td><td>Thời gian hẹn gửi của tin. <br>Không truyền khi tin muốn tin nhắn gửi đi liền.<br>Định dạng: yyyy-mm-dd hh:MM:ss.</td></tr><tr><td>TempID <mark style="color:red;">*</mark></td><td>Template của Zalo OA mà khách hàng đăng kí với eSMS.</td></tr><tr><td>campaignid</td><td>Tên chiến dịch gửi tin, tối đa 254 ký tự.</td></tr><tr><td>Sandbox</td><td>0: Gửi tin đi thật<br>1: Tin thử nghiệm, không lưu tin và không đi tin. Chỉ để kiểm tra kết nối.</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn.</td></tr></tbody></table>

\


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
