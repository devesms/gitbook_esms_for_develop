---
description: API cho phép đối tác lấy sản lượng tin nhắn trong một khoảng thời gian
---

# Hàm kiểm tra trạng thái tin nhắn theo khoảng thời gian

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetSmsSentData\_V1](http://rest.esms.vn/MainService.svc/json/GetSmsSentData\_V1)\
  Method: POST\
  Content Type: text/plain

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/GetSmsSentData_V1' \
--header 'Content-Type: text/plain' \
--header 'Cookie: ASP.NET_SessionId=owevtxyrtqm5gvj5zwjfeb2z' \
--data-raw '<RQST>
 <APIKEY>{{ApiKey}}</APIKEY>
 <SECRETKEY>{{SecretKey}}</SECRETKEY>
 <FROM>2022/07/26 00:00:00</FROM>
 <TO>2022/07/26 11:00:00</TO>
</RQST>'
```

* Thông tin request

| Biến                                         | Định nghĩa              |
| -------------------------------------------- | ----------------------- |
| APIKEY <mark style="color:red;">\*</mark>    | ApiKey của tài khoản    |
| SECRETKEY <mark style="color:red;">\*</mark> | Secretkey của tài khoản |
| FROM <mark style="color:red;">\*</mark>      | Ngày bắt đầu lấy tin    |
| TO <mark style="color:red;">\*</mark>        | Ngày kết thúc lấy tin   |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "SentData": [
        {
            "Content": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "Phone": "0901888484",
            "RefercenceId": "ea6a83e0-9f9d-44cf-a561-46814324a86f40",
            "SellPrice": 820.0000,
            "SentStatus": true,
            "SentTime": "/Date(1659410201873+0700)/",
            "SmsId": 497819097,
            "SmsType": 2
        },
        {
            "Content": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "Phone": "0901888484",
            "RefercenceId": "51c685ab-e1af-4069-86de-3ab902ed0bc647",
            "SellPrice": 790.0000,
            "SentStatus": false,
            "SmsId": 497819096,
            "SmsType": 2
        }
                ]
        }
```

* Thông tin kết quả trả về

| Biến         | Định nghĩa                           |
| ------------ | ------------------------------------ |
| Content      | Nội dung tin nhắn                    |
| Phone        | Số điện thoại nhận tin nhắn          |
| RefercenceId | SmsId trả về từ các hàm gửi tin nhắn |
| Sellprice    | Giá của tin                          |
| Sendstatus   | Trạng thái gửi tin                   |
| SentTime     | Thời gian gửi tin                    |
| SmsId        | Id của tin nhắn trên giao diện       |
| SmsType      | Loại tin nhắn                        |
