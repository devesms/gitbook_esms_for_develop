---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Hàm gửi tin Zalo Tư Vấn dạng Media

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage\_V4\_post\_json/](http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage\_V4\_post\_json/)\
  Method: POST\
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=3hhvrcacfm1pg13pd1ionirz' \
--data-raw '{
 "ApiKey":"{ApiKey}",
 "SecretKey":"{SecretKey}",
 "OAID":"{OAID}",
 "User_id":"{User_id}",
 "Content":"{Content}",
 "Template_type":"{Template_type}",
 "Url": "{Url}",
 "CallbackUrl": "{CallbackUrl}"
}'
```



* Thông tin request

<table><thead><tr><th width="236">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản.</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản.</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>User_id <mark style="color:red;">*</mark></td><td>Userid cần gửi đến, đây là userid của zalo.</td></tr><tr><td>Content <mark style="color:red;">*</mark> </td><td>Nội dung tin nhắn<br>Lưu ý: Khi gửi dạng tin nhắn này khách hàng vui lòng liên hệ cho nhân viên kinh doanh để được hỗ trợ về content.</td></tr><tr><td>Template_type <mark style="color:red;">*</mark></td><td>Loại template</td></tr><tr><td>Url</td><td>Link hình ảnh, chấp nhận link đuôi PNG và JPG</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn này.</td></tr></tbody></table>

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
