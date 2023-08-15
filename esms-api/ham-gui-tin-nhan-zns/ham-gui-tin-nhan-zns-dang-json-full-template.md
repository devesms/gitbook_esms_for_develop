# Hàm gửi tin nhắn ZNS dạng Json Full template

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post\_json/](http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post\_json/)\
  Method: POST\
  Content Type: application/json

{% code overflow="wrap" %}
```
curl --location 'http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "SmsType": "{{SmsType}}",
    "OAID": "{{OAID}}",
    "Phone": "{{Phone}}",
    "Content": "{{Content}}",
    "IsUnicode": "1"
}'
```
{% endcode %}



* Thông tin request

<table><thead><tr><th width="236">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>Phone <mark style="color:red;">*</mark></td><td>Số điện thoại người nhận.</td></tr><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản.</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản.</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>Content <mark style="color:red;">*</mark></td><td>Nội dung tin nhắn sẽ được gửi full content.<br>Lưu ý: Khi gửi dạng tin nhắn này khách hàng vui lòng liên hệ cho nhân viên kinh doanh để được hỗ trợ về content.</td></tr><tr><td>Smstype <mark style="color:red;">*</mark></td><td>Loại tin nhắn:<br>24: Zalo ưu tiên<br>25: Zalo bình thường</td></tr><tr><td>IsUnicode</td><td>Gửi nội dung có dấu<br>1: Có dấu<br>0: Không dấu</td></tr></tbody></table>

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
