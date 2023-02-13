# Hàm gửi tin nhắn ZNS dạng X-Form

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post/](http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post/)\
  Method: POST\
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post/' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'Apikey={Apikey}' \
--data-urlencode 'SecretKey={SecretKey}' \
--data-urlencode 'Phone={Phone}' \
--data-urlencode 'Content={Content}' \
--data-urlencode 'Smstype={Smstype}' \
--data-urlencode 'OAID={OAID}'
```



* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                                                                                                     |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Phone <mark style="color:red;">\*</mark>     | Số điện thoại người nhận.                                                                                                                                                                                                      |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản.                                                                                                                                                                                                          |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản.                                                                                                                                                                                                       |
| OAID <mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| Content <mark style="color:red;">\*</mark>   | <p>Nội dung tin nhắn<br>Lưu ý: Khi gửi dạng tin nhắn này khách hàng vui lòng liên hệ cho nhân viên kinh doanh để được hỗ trợ về content.</p>                                                                                   |
| Smstype <mark style="color:red;">\*</mark>   | <p>Loại tin nhắn:<br>24: Zalo ưu tiên<br>25: Zalo bình thường</p>                                                                                                                                                              |

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
