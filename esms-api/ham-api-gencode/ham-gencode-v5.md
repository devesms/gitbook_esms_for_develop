---
description: >-
  Khác với gencode v4, gencode v5 sẽ là multichanel. Nếu tin ZNS thất bại sẽ về
  tin nhắn SMS brandname với cùng một mã OTP.
---

# Hàm gencode V5

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V5](http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V5)\
  Method: POST\
  Content Type: application/json

{% code overflow="wrap" %}
```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode_V5' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=nsvdja0b4rcfjf1o4szjxno0' \
--data-raw '{
 "ApiKey": "{ApiKey}",
 "Phone": "{Phone}",
 "TimeAlive": "{TimeAlive}",
 "SecretKey": "{SecretKey}",
 "MultiChannelTempId": "{MultiChannelTempId}",
 "TypeId":"{TypeId}"
}'
```
{% endcode %}

* Thông tin request

| Biến               | Định nghĩa                                                                                                                                         |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Phone              | Số điện thoại nhận tin                                                                                                                             |
| ApiKey             | ApiKey của tài khoản                                                                                                                               |
| SecretKey          | Secretkey của tài khoản                                                                                                                            |
| TimeAlive          | Thời gian hiệu lực của mã code. Đơn vị tính: Phút. Giới hạn từ 2 phút đến 15 phút                                                                  |
| MultiChannelTempId | Id do ViHAT cung cấp. Khi muốn sử dụng hàm này tài khoản của bạn phản có OA ZNS và brandname. Bạn cung cấp tempid của ZNS và template của tin SMS. |
| Type               | <p>1: Chỉ tạo ra mã Code<br>2: Tạo ra và gửi tin nhắn về máy</p>                                                                                   |

* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

* Thông tin kết quả trả về

| Biến  | Định nghĩa                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |

