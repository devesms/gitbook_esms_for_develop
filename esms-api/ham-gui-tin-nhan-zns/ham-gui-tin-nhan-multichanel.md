---
description: >-
  Giải pháp Multi-Channel Messaging API cho phép bạn gửi tin nhắn đến khách hàng
  đi qua các kênh giao tiếp khác nhau như Zalo, SMS, Viber theo các thứ tự ưu
  tiên.
---

# Hàm gửi tin nhắn MultiChanel

* HTTP request\
  URL: [https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/](https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/)\
  Method: POST\
  Content Type: application/json

```
curl --location --request POST 'https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=mhcur4ewhxeqmqv1jj2qsb23' \
--data-raw '{
    "ApiKey": "{ApiKey}",
    "SecretKey": "{SecretKey}",
    "Phone": "{Phone}",
    "Channels": [
        "zalo",
        "sms"
    ],
    "Data": [
        {
            "TempID": "{TempID}",
            "Params": ["param1","param2","param3",....],
            "OAID": "{OAID}",
            "campaignid": "{campaignid}",
            "CallbackUrl": "{CallbackUrl}",
            "RequestId":"{{RequestId}}"
        },
        {
            "Content": "{Content}",
            "IsUnicode": {IsUnicode},
            "SmsType": {SmsType},
            "Brandname": "{Brandname}",
            "CallbackUrl": "{CallbackUrl}"
        }
    ]
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                                                                                                     |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                                                                                           |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                                                                                                                                                                        |
| Phone <mark style="color:red;">\*</mark>     | Số điện thoại nhận tin                                                                                                                                                                                                         |
| Params <mark style="color:red;">\*</mark>    | <p></p><p>Giá trị cần truyền cho các biến trong Template *Lưu ý:</p><ol><li>Các tham số truyền vào phải đúng thứ tự như template bạn đăng ký</li><li>Nếu tham số trùng nhau chỉ cần truyền vào một tham số</li></ol>           |
| TempID <mark style="color:red;">\*</mark>    | Template của Zalo OA mà khách hàng đăng kí với eSMS                                                                                                                                                                            |
| OAID <mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| RequestId                                    | <p>ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. <br>Ví dụ: RequestId=123456</p>                                                                                         |
| campaignid                                   | Tên chiến dịch gửi tin, tối đa 254 ký tự                                                                                                                                                                                       |
| RequestId                                    | <p>ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. <br>Ví dụ: RequestId=123456</p>                                                                                         |
| CallbackUrl                                  | eSMS sẽ trả về kết quả của tin nhắn.                                                                                                                                                                                           |
| Content <mark style="color:red;">\*</mark>   | Nội dung tin nhắn                                                                                                                                                                                                              |
| IsUnicode                                    | <p>Gửi tin nhắn có dấu<br>0: Gửi tin không dấu<br>1: Gửi tin nhắn có dấu</p>                                                                                                                                                   |
| Brandname <mark style="color:red;">\*</mark> | <p>Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p>                                                                        |

* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

* Thông tin kết quả trả về

|       |                                                                                                   |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |
