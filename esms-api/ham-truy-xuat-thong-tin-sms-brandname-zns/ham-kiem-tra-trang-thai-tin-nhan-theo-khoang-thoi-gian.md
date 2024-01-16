---
description: API cho phép đối tác lấy sản lượng tin nhắn trong một khoảng thời gian
---

# Hàm kiểm tra trạng thái tin nhắn theo khoảng thời gian

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetSmsSentData\_V2'](http://rest.esms.vn/MainService.svc/json/GetSmsSentData\_V2')\
  Method: POST\
  Content Type:  application/json

```
curl --location 'http://rest.esms.vn/MainService.svc/json/GetSmsSentData_V2' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey":"{{ApiKey}}",
    "SecretKey":"{{SecretKey}}",
    "SmsType":2,
    "From": "2023-11-10 14:00:00",
    "To":"2023-11-30 14:00:00",
    "Page":1,
    "PageSize":500
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                     |
| -------------------------------------------- | ------------------------------------------------------------------------------ |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                           |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                        |
| From <mark style="color:red;">\*</mark>      | <p>Ngày bắt đầu lấy tin<br> Định dạng: yyyy-MM-dd HH:mm:ss</p>                 |
|                                              |                                                                                |
| To <mark style="color:red;">\*</mark>        | <p>Ngày kết thúc lấy tin (tối đa 3 ngày)<br>Định dạng: yyyy-MM-dd HH:mm:ss</p> |
| <pre><code>Page
</code></pre>                | Lấy bắt đầu từ trang bao nhiêu                                                 |
| <pre><code>PageSize
</code></pre>            | Số lượng tin nhắn cần xem (tối đa 500 tin nhắn)                                |
| SmsType <mark style="color:red;">\*</mark>   | Loại tin nhắn                                                                  |



* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "CountTotal": 518,
    "SentData": [
        {
            "Campaign": "Chiến dịch 02/10/2023",
            "Content": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "Phone": "0901888484",
            "ReferenceId": "02e26dff-edc0-4726-8614-e425c21915f3152",
            "SellPrice": 790.000,
            "SendStatus": 5,
            "SentResult": true,
            "SentTime": "23/11/2023 17:06:37",
            "SmsId": 860903326,
            "SmsType": 2
        },
        {
            "Campaign": "Chiến dịch 02/10/2023",
            "Content": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "Phone": "0901888484",
            "ReferenceId": "0aac72e0-ba9b-4348-8530-d18d105778db18",
            "SellPrice": 790.0000,
            "SendStatus": 5,
            "SentResult": true,
            "SentTime": "23/11/2023 17:45:23",
            "SmsId": 862970481,
            "SmsType": 2
        }
    ]
}
```

* Thông tin kết quả trả về

| Biến         | Định nghĩa                                                                                                                   |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| CountTotal   | Tổng số tin nhắn                                                                                                             |
| Campaign     | Tên chiến dịch                                                                                                               |
| Content      | Nội dung tin nhắn                                                                                                            |
| Phone        | Số điện thoại nhận tin nhắn                                                                                                  |
| RefercenceId | SmsId trả về từ các hàm gửi tin nhắn                                                                                         |
| Sellprice    | Giá của tin                                                                                                                  |
| SendStatus   | <p>Trạng thái gửi tin</p><p>1: Chờ duyệt</p><p>2: Chờ gửi</p><p>3: Đang gửi</p><p>4: Từ chối</p><p>5: Thành công</p>         |
| SentResult   | <p>Kết quả gửi tin:<br>true: Tin thành công<br>false: Tin thất bại</p>                                                       |
| SentTime     | Thời gian gửi tin                                                                                                            |
| SmsId        | Id của tin nhắn trên giao diện                                                                                               |
| SmsType      | <p>Loại tin nhắn<br>1: Tin quảng cáo<br>2: Tin CSKH<br>8: Tin Cố định giá rẻ<br>24: Zalo ưu tiên<br>25: Zalo bình thường</p> |
