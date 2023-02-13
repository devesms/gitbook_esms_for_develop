---
description: >-
  API dùng để gửi tin Quảng cáo đến khách hàng. Mỗi request tối thiểu 30 số để
  được duyệt tin và tối đa 5000 số.
---

# Gửi tin Quảng cáo (TypeSMS 1) dạng POST

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname\_json/](http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname\_json/)\
  Method: POST\
  Content Type: application/json

```json
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname_json/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=nnkmnp1hqg4qiy2ar5x4owjq' \
--data-raw '{
    "ApiKey":"{{SecretKey}}",
    "SecretKey":"{{SecretKey}}",
    "Brandname":"{{Brandname}}",
    "Content":"{{Content}}", 
    "Phones":[ "{{Phones}}","{{Phones}}","{{Phones}}"],
    "CallbackUrl": "{{CallbackUrl}}",
    "SmsType":"1"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                              |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                    |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                                                                                                 |
| Content <mark style="color:red;">\*</mark>   | Nội dung tin nhắn                                                                                                                                       |
| SmsType <mark style="color:red;">\*</mark>   | <p>Loại tin nhắn<br>1: Tin quảng cáo</p>                                                                                                                |
| Brandname <mark style="color:red;">\*</mark> | <p>Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| Phones <mark style="color:red;">\*</mark>    | Số điện thoại nhận tin nhắn.                                                                                                                            |
| SendDate                                     | <p>Thời gian hẹn gửi của tin. <br>Không truyền khi tin muốn tin nhắn gửi đi liền.<br>Định dạng: yyyy-mm-dd hh:MM:ss</p>                                 |
| CallbackUrl                                  | [https://developers.esms.vn/esms-api/callback-url](https://developers.esms.vn/esms-api/callback-url)                                                    |

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
