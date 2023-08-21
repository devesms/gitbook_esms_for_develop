---
description: Đây là hàm dùng để đăng ký mua gói OA
---

# Hàm đăng ký mua gói OA



* HTTP request\
  URL: [http://rest.esms.vn](http://rest.esms.vn/MainService.svc/json/GetBalance\_json)/MainService.svc/json/RegisOAPackageJson/\
  Method: POST\
  Content Type: application/json
* Request mẫu

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/RegisOAPackageJson/' \
--header 'Content-Type: application/json' \
--data-raw '{
    "ApiKey":"ApiKey",
    "SecretKey":"SecretKey",
    "Dateactive":"dateactive",
    "Duaration":"duaration",
    "OAID":"{OAID}",
    "Package":package
}
```

* Thông tin request

| Biến                                          | Định nghĩa                                                                                                                                                                                                                     |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ApiKey <mark style="color:red;">\*</mark>     | ApiKey của tài khoản                                                                                                                                                                                                           |
| SecretKey <mark style="color:red;">\*</mark>  | SecretKey của tài khoản                                                                                                                                                                                                        |
| Dateactive <mark style="color:red;">\*</mark> | <p>Ngày kích hoạt OA</p><p>Định dạng yyyy- mm - dd</p>                                                                                                                                                                         |
| Duaration <mark style="color:red;">\*</mark>  | Thời gian gia hạn gói OA                                                                                                                                                                                                       |
| OAID <mark style="color:red;">\*</mark>       | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| Package <mark style="color:red;">\*</mark>    | <p>Gói OA<br>- 1: Gói dùng thử<br>- 2: Gói nâng cao<br>- 3: Gói premium</p>                                                                                                                                                    |
|                                               |                                                                                                                                                                                                                                |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "ViHAT is censoring trademark ownership",
    "ServicePreviewId": 52330
}

```

* Thông tin kết quả trả về

| Biến             | Định nghĩa               |
| ---------------- | ------------------------ |
| CodeResult       | Kết quả của Request      |
| ErrorMessage     | Thông báo kết quả trả về |
| ServicepreviewId | ID đăng ký OA phía eSMS  |

*
