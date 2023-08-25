---
description: Đây là hàm dùng để đăng ký template ZNS
---

# Hàm đăng ký template SMS



* HTTP request\
  URL: [http://rest.esms.vn](http://rest.esms.vn/MainService.svc/json/GetBalance\_json)[/MainService.svc/json/RegisZNSTemplateJson/](http://rest.esms.vn/MainService.svc/json/SubServicePreviewJson/)\
  Method: POST\
  Content Type: application/json
* Request mẫu

```
curl --location 'http://rest.esms.vn/MainService.svc/json/SubServicePreviewJson/' \
--header 'Content-Type: application/json' \
--data-raw '{
    "ApiKey": "{{ApiKey}}",
    "AssetsUrl": "{{AssetsUrl}}",
    "Brandname": "{{Brandname}}",
    "CallbackUrl": "{{CallbackUrl}}",
    "Content": "{{Content}}",
    "IsUnicode": "0",
    "CustomerEmail": "{{CustomerEmail}}",
    "CustomerName": "{{CustomerName}}",
    "CustomerPhone": "{CustomerPhone}}",
    "SecretKey": "{{SecretKey}}",
    "ServiceType": 2,
    "SmsType": {{SmsType}}
}'
```

* Thông tin request

| Biến                                           | Định nghĩa                                                                                                                                  |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>      | ApiKey của tài khoản                                                                                                                        |
| SecretKey <mark style="color:red;">\*</mark>   | SecretKey của tài khoản                                                                                                                     |
| Content <mark style="color:red;">\*</mark>     | <p>Nội dung mẫu của template cần đăng ký<br>Ví dụ: {<strong>Biến</strong>:<strong>Số lượng ký tự mong muốn</strong>}</p>                    |
| AssetsUrl                                      | Là đường dẫn để tài 1 tài liệu nào đó ở server của đối tác. tài liệu này phục vụ cho việc xác thực đăng ký.                                 |
| Brandname <mark style="color:red;">\*</mark>   | BrandName cần đăng ký template (lưu ý: Brandname này phải được add vào tài khoản thì mới đăng ký được)                                      |
| IsUnicode                                      | <p>Đăng ký nội dung có dấu<br>1: Có dấu<br>0: Không dấu</p>                                                                                 |
| CustomerEmail                                  | Email tài khoản KH cuối cần đăng ký brandname                                                                                               |
| CustomerName                                   | Số điện thoại KH cuối cần Đăng ký brandname                                                                                                 |
| CustomerPhone                                  | CustomerPhone                                                                                                                               |
| ServiceType <mark style="color:red;">\*</mark> | ServiceType = 2 là đăng ký Template CSKH hoặc Cố định giá rẻ                                                                                |
| SmsType <mark style="color:red;">\*</mark>     | <p>2: khi đăng ký template CSKH <br>8: khi đăng ký template Cố định giá rẻ</p>                                                              |
| CallbackUrl                                    | <p>Sẽ nhận kết quả trả về của eSMS sau khi yêu cầu đăng ký brandname. <br>0: Thất bại <br>1: Thành công eSMS <br>2: Thành công nhà mạng</p> |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "ViHAT is moderating your template",
    "ServicePreviewId": 52353
}

```

* Thông tin kết quả trả về

| Biến             | Định nghĩa               |
| ---------------- | ------------------------ |
| CodeResult       | Kết quả của Request      |
| ErrorMessage     | Thông báo kết quả trả về |
| ServicepreviewId | ID brandname phía eSMS   |

*
