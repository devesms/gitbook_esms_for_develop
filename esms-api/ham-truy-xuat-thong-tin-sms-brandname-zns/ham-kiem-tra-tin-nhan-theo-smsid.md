---
description: Hàm giúp bạn kiểm tra trạng thái của tin nhắn đã gửi đi.
---

# Hàm kiểm tra tin nhắn theo SMSID

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetSendStatus?RefId=\{{SMSID\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}](http://rest.esms.vn/MainService.svc/json/GetSendStatus?RefId=\{{SMSID\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}})\
  Method: GET

```
curl --location -g --request GET 'http://rest.esms.vn/MainService.svc/json/GetSendStatus?RefId={{SMSID}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}' \
--header 'Cookie: ASP.NET_SessionId=owevtxyrtqm5gvj5zwjfeb2z' \
--data-raw ''
```

* Thông tin request

| Biến                                         | Định nghĩa                                    |
| -------------------------------------------- | --------------------------------------------- |
| RefId <mark style="color:red;">\*</mark>     | SmsId hệ thống trả về từ mỗi hàm gửi tin nhắn |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                          |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                       |

* Mẫu kết quả trả về

```
{
    "CodeResponse": "100",
    "SMSID": "434a124c-7818-4f45-bdf2-7f7b07fff210100",
    "SendFailed": 0,
    "SendStatus": 5,
    "SendSuccess": 1,
    "TotalPrice": 850.0000,
    "TotalReceiver": 1,
    "TotalSent": 1
}
```

* Thông tin kết quả trả về

| Biến          | Định nghĩa                                                                 |
| ------------- | -------------------------------------------------------------------------- |
| SMSID         | SmsId kiểm tra                                                             |
| SendFailed    | Số lượng tin thất bại                                                      |
| SendStatus    | <p>Trạng thái tin nhắn<br>1: Chờ Duyệt<br>2: Chờ gửi<br>5: Đã gửi xong</p> |
| SendSuccess   | Số lượng tin thành công                                                    |
| TotalPrice    | Tổng tiền của đơn                                                          |
| TotalReceiver | Số lượng người nhận                                                        |
| TotalSent     | Số lượng gửi                                                               |
