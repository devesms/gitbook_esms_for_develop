# Hàm gửi tin Zalo Follower dạng Media

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

| Biến                                              | Định nghĩa                                                                                                                                                                                                                     |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ApiKey <mark style="color:red;">\*</mark>         | ApiKey của tài khoản.                                                                                                                                                                                                          |
| SecretKey <mark style="color:red;">\*</mark>      | Secretkey của tài khoản.                                                                                                                                                                                                       |
| OAID <mark style="color:red;">\*</mark>           | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| User\_id <mark style="color:red;">\*</mark>       | Userid cần gửi đến, đây là userid của zalo.                                                                                                                                                                                    |
| Content <mark style="color:red;">\*</mark>        | <p>Nội dung tin nhắn<br>Lưu ý: Khi gửi dạng tin nhắn này khách hàng vui lòng liên hệ cho nhân viên kinh doanh để được hỗ trợ về content.</p>                                                                                   |
| Template\_type <mark style="color:red;">\*</mark> | Loại template                                                                                                                                                                                                                  |
| Url                                               | Link hình ảnh, chấp nhận link đuôi PNG và JPG                                                                                                                                                                                  |
| CallbackUrl                                       | eSMS sẽ trả về kết quả của tin nhắn này.                                                                                                                                                                                       |

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
