---
description: Hàm cho phép bạn gọi API check code xem đã sử dụng, hết hạn.
---

# Hàm check code

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V5](http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V5)\
  Method: GET

```
curl --location --request GET 'http://rest.esms.vn/MainService.svc/json/CheckCodeGen_V4_get?Phone={Phone}&ApiKey={ApiKey}&SecretKey={SecretKey}&Code={Code}' \
--header 'Cookie: ASP.NET_SessionId=nsvdja0b4rcfjf1o4szjxno0'
```

* Thông tin request

| Biến      | Định nghĩa                    |
| --------- | ----------------------------- |
| ApiKey    | ApiKey của tài khoản          |
| SecretKey | Secretkey của tài khoản       |
| Phone     | Số điện thoại người nhận code |
| Code      | Mã code cần check             |

* Kết quả trả về

```
{
 "CodeResult": "100",
 "CountRegenerate": 0,
 "ErrorMessage": "0901888484, Content: Success!"
}
```

* Thông tin kết quả trả về

| Biến | Định nghĩa                             |
| ---- | -------------------------------------- |
| 100  | Code hợp lệ                            |
| 117  | Code không hợp lệ hoặc đã được sử dụng |

