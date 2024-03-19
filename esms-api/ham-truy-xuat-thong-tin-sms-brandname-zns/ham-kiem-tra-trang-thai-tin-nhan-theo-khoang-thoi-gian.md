---
description: API cho phép đối tác lấy sản lượng tin nhắn trong một khoảng thời gian.
---

# Hàm kiểm tra trạng thái tin nhắn theo khoảng thời gian

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetSmsSentData\_V2](http://rest.esms.vn/MainService.svc/json/GetSmsSentData\_V2')\
  Method: POST\
  Content Type:  application/json

```
curl --location 'http://rest.esms.vn/MainService.svc/json/GetSmsSentData_V2' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey":"{{ApiKey}}",
    "SecretKey":"{{SecretKey}}",
    "SmsType":{{SmsType}},
    "From": "2023-11-10 14:00:00",
    "To":"2023-11-30 14:00:00",
    "Page":1,
    "PageSize":500
}'
```

* Thông tin request

<table><thead><tr><th width="172">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản.</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản.</td></tr><tr><td>From <mark style="color:red;">*</mark></td><td>Ngày bắt đầu lấy tin.<br> Định dạng: yyyy-MM-dd HH:mm:ss.</td></tr><tr><td>To <mark style="color:red;">*</mark></td><td>Ngày kết thúc lấy tin.<br>Định dạng: yyyy-MM-dd HH:mm:ss.</td></tr><tr><td>Page</td><td>Lấy bắt đầu từ trang bao nhiêu.</td></tr><tr><td>PageSize</td><td>Số lượng tin nhắn cần xem (tối đa 500 tin nhắn).</td></tr><tr><td>SmsType <mark style="color:red;">*</mark></td><td>Loại tin nhắn<br>1: Tin quảng cáo.<br>2: Tin CSKH.<br>8: Tin Cố định giá rẻ.<br>23: Tin Viber.<br>24: Zalo ưu tiên.<br>25: Zalo bình thường.<br>26: Zalo Follower.</td></tr></tbody></table>



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
            "ReferenceId": "35781d6c25524e40a035c26663189549",
            "SellPrice": 345.0,
            "SendResult": 0,
            "SendStatus:5,
            "SentTime": "/Date(1705484048995+0700)/",
            "SmsId": 29028845,
            "SmsType": 2
        },
        {
            "Campaign": "Chiến dịch 02/10/2023",
            "Content": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "Phone": "0901888484",
            "ReferenceId": "0aac72e0-ba9b-4348-8530-d18d105778db18",
            "SellPrice": 790.0000,
            "SendResult": 1,
            "SendStatus:5,
            "SentTime": "/Date(1705484048995+0700)/",
            "SmsId": 29028845,
            "SmsType": 2
        }
    ]
}
```

* Thông tin kết quả trả về

| Biến         | Định nghĩa                                                                                                                                                                |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CountTotal   | Tổng số tin nhắn.                                                                                                                                                         |
| Campaign     | Tên chiến dịch.                                                                                                                                                           |
| Content      | Nội dung tin nhắn.                                                                                                                                                        |
| Phone        | Số điện thoại nhận tin nhắn.                                                                                                                                              |
| RefercenceId | SmsId trả về từ các hàm gửi tin nhắn.                                                                                                                                     |
| Sellprice    | Giá của tin.                                                                                                                                                              |
| SendResult   | <p>Trạng thái tin nhắn:</p><p>1: Tin đã được gửi thành công.<br>0: Tin thất bại.<br>2: Tin chưa xác định trạng thái.</p>                                                  |
| SendStatus   | <p>0: Đang soạn thảo.<br>1: Chờ duyệt.<br>2: Chờ gửi.<br>4: Từ chối.<br>5: Đã gửi xong.<br>7: Đã gửi chờ báo cáo</p>                                                      |
| SentTime     | Thời gian gửi tin.                                                                                                                                                        |
| SmsId        | Id của tin nhắn trên giao diện.                                                                                                                                           |
| SmsType      | <p>Loại tin nhắn<br>1: Tin quảng cáo.<br>2: Tin CSKH.<br>8: Tin Cố định giá rẻ.<br>23: Tin Viber.<br>24: Zalo ưu tiên.<br>25: Zalo bình thường.<br>26: Zalo Follower.</p> |
