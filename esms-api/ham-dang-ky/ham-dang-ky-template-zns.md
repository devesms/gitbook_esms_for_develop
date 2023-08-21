---
description: Đây là hàm dùng để đăng ký template ZNS
---

# Hàm đăng ký template ZNS



* HTTP request\
  URL: [http://rest.esms.vn](http://rest.esms.vn/MainService.svc/json/GetBalance\_json)/MainService.svc/json/RegisZNSTemplateJson/\
  Method: POST\
  Content Type: application/json
* Request mẫu

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/RegisZNSTemplateJson/' \
--header 'Content-Type: application/json' 
--data-raw '{
    "ApiKey":"ApiKey",
    "SecretKey":"SecretKey",
    "Content":"Content",
    "ImageUrl":"ImageURL",
    "CTA1":"CTA 1",
    "CTA2":"CTA 2",
    "OAID":"OAID",
    "SmsType":"smstype"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                                                                                                     |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                                                                                           |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản                                                                                                                                                                                                        |
| Content<mark style="color:red;">\*</mark>    | Nội dung mẫu của template cần đăng ký                                                                                                                                                                                          |
| ImageURL <mark style="color:red;">\*</mark>  | Link hình ảnh, chấp nhận link đuôi PNG và JPG                                                                                                                                                                                  |
| CTA 1                                        | Link CTA thứ nhất                                                                                                                                                                                                              |
| CTA 2                                        | Link CTA thứ hai                                                                                                                                                                                                               |
| OAID <mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| SmsType<mark style="color:red;">\*</mark>    | <p>24: khi đăng ký template zalo ưu tiên<br>25: khi đăng ký template zalo bình thường</p>                                                                                                                                      |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "ViHAT is censoring trademark ownership",
    "ServicePreviewId": 52330
}

```

* Thông tin kết quả trả về

| Biến             | Định nghĩa                   |
| ---------------- | ---------------------------- |
| CodeResult       | Kết quả của Request          |
| ErrorMessage     | Thông báo kết quả trả về     |
| ServicepreviewId | ID đăng ký template phía eSM |

*
