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
    "SmsType":"smstype",
    "CallbackUrl":"CallbackUrl"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                                                                                                     |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                                                                                           |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản                                                                                                                                                                                                        |
| Content <mark style="color:red;">\*</mark>   | Nội dung mẫu của template cần đăng ký                                                                                                                                                                                          |
| ImageURL <mark style="color:red;">\*</mark>  | Link hình ảnh LOGO OA, chấp nhận link đuôi PNG, kích thước 400x69, tách nền màu nền đen hoặc trắng.                                                                                                                            |
| CTA 1                                        | Link CTA thứ nhất                                                                                                                                                                                                              |
| CTA 2                                        | Link CTA thứ hai                                                                                                                                                                                                               |
| OAID <mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| SmsType<mark style="color:red;">\*</mark>    | <p>24: khi đăng ký template zalo ưu tiên<br>25: khi đăng ký template zalo bình thường</p>                                                                                                                                      |
| CallbackUrl                                  | <p>Link nhận trạng thái template đăng ký<br>0: Đăng ký thất bại.<br>1: eSMS tiếp nhận thành công.<br>2: Đăng ký thành công.</p>                                                                                                |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "ViHAT is censoring trademark ownership",
    "ServicePreviewId": 52330
}

```

* Thông tin kết quả trả về

| Biến             | Định nghĩa                  |
| ---------------- | --------------------------- |
| CodeResult       | Kết quả của Request         |
| ErrorMessage     | Thông báo kết quả trả về    |
| ServicepreviewId | ID template yêu cầu đăng ký |

*
