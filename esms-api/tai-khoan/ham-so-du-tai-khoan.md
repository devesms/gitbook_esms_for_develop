---
description: >-
  Đây là hàm cơ bản đầu tiên mà bạn nên thử, hàm giúp bạn lấy về số dư trong tài
  khoản của bạn.
---

# Hàm số dư tài khoản



* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetBalance\_json](http://rest.esms.vn/MainService.svc/json/GetBalance\_json)\
  Method: POST\
  Content Type: application/json
* Request mẫu

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/GetBalance_json' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=owevtxyrtqm5gvj5zwjfeb2z' \
--data-raw '{
"ApiKey":"{{ApiKey}}",
"SecretKey":"{{SecretKey}}"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa              |
| -------------------------------------------- | ----------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản    |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản |

* Mẫu kết quả trả về

```
{
    "Balance": 36693,
    "CodeResponse": "100",
    "UserID": 9999
}
```

* Thông tin kết quả trả về

| Biến         | Định nghĩa                     |
| ------------ | ------------------------------ |
| Balance      | Số dư tài khoản chính          |
| CodeResponse | Mã lỗi                         |
| UserID       | Id user tài khoản của hệ thống |

*
