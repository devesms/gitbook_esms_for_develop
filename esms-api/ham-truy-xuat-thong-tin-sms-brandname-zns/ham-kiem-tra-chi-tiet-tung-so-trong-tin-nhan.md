---
description: >-
  Hàm lấy danh sách SĐT của một tin nhắn đã gửi (dựa trên SmsID hệ thống trả về)
  kèm theo trạng thái gửi (SĐT đó đã gửi thành công chưa?). Lưu ý: Chỉ lấy dữ
  liệu các tin trong vòng 7 ngày gần nhất.
---

# Hàm kiểm tra chi tiết từng số trong tin nhắn

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetSmsReceiverStatus\_get?\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&RefId=\{{SMSID\}}](http://rest.esms.vn/MainService.svc/json/GetSmsReceiverStatus\_get?\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&RefId=\{{SMSID\}})\
  Method: GET

```
curl --location -g --request GET 'http://rest.esms.vn/MainService.svc/json/GetSmsReceiverStatus_get?&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&RefId={{SMSID}}' \
--header 'Cookie: ASP.NET_SessionId=owevtxyrtqm5gvj5zwjfeb2z'
```

* Thông tin request

| Biến                                          | Định nghĩa                                    |
| --------------------------------------------- | --------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>     | ApiKey của tài khoản                          |
| SecretKey <mark style="color:red;">\*</mark>  | Secretkey của tài khoản                       |
| RefId <mark style="color:red;">\*</mark>      | SmsId hệ thống trả về từ mỗi hàm gửi tin nhắn |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ReceiverList": [
        {
            "IsSent": true,
            "NetworkName": "Viettel",
            "Phone": "0901888484",
            "Retry": 0,
            "SentResult": true
        }
    ]
}
```

* Thông tin kết quả trả về

| Biến        | Định nghĩa                                                                    |
| ----------- | ----------------------------------------------------------------------------- |
| IsSent      | <p>Trạng thái đi tin<br>true: tin đã được gửi<br>false: tin chưa được gửi</p> |
| NetworkName | Nhà mạng của số điện thoại                                                    |
| Phone       | Số điện thoại                                                                 |
| Retry       | Số lần gửi lại tin nhắn                                                       |
| SentResult  | <p>Kết quả tin nhắn<br>True: Gửi thành công<br>False: Gửi thất bại</p>        |
