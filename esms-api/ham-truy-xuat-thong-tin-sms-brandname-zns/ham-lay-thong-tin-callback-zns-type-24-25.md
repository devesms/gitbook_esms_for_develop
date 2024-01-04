# Hàm lấy thông tin callback ZNS  (Type 24, 25)

* HTTP request \
  URL: [http://status-sms.esms.vn/ZaloCallback/GetCallback](http://status-sms.esms.vn/ZaloCallback/GetCallback)\
  Method: POST\
  Content Type: application/json

```
curl --location 'http://status-sms.esms.vn/ZaloCallback/GetCallback' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey":"{{ApiKey}}",
    "SecretKey":"{{SecretKey}}",
    "ListRefid": [
        "41a35814-81d7-4ad1-9cce-1ac7fddd5f34196",
        "41a35814-81d7-4ad1-9cce-1ac7fddd5f34197",
        "41a35814-81d7-4ad1-9cce-1ac7fddd5f34198"
    ],
    "OAId": "{{OAId}}"
}
```

* Thông tin request

| Biến      | Định nghĩa                                                                                                                                    |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| ListRefid | <p>Danh sách ReferenceId đã gửi tin.<br>Giới hạn 200 RefId, truyền nhiều hơn sẽ chỉ lấy callback của 200 RefId theo thứ tự từ trên xuống.</p> |
| OAId      | Id của OA đã gửi tin                                                                                                                          |
| ApiKey    | ApiKey của tài khoản                                                                                                                          |
| SecretKey | SecretKey của tài khoản                                                                                                                       |

* Mẫu kết quả trả về

```
{
    "Code": 100,
    "Message": "Success",
    "Data_callback": [
        {
            "SMSID": "4a496110-9fd3-4838-ac8b-bcaa36616f7011",
            "SendFailed": 1,
            "SendSuccess": 0,
            "SendStatus": 5,
            "TotalPrice": 0.0,
            "TotalReceiver": 1,
            "TotalSent": 1,
            "RequestId": null,
            "TypeId": 25,
            "Telcoid": 1,
            "PhoneNumber": "0909090909",
            "CallbackUrl": "https://api.esms.vn/zalo-zns/zns/receive-callback",
            "Partnerids": "7984e9b198c40e9957d6",
            "ErrorInfo": "{\"error\":-124,\"message\":\"Access token is invalid\"}Object reference not set to an instance of an object.",
            "OAId": "1090257973118325189",
            "ZnsTempId": "228386"
        } 
                    ]
  } 
```

* Thông tin kết quả trả về&#x20;

| Biến          | Định nghĩa                                                                                                                                                                                                 |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SMSID         | ReferenceId của tin nhắn muốn xem callback                                                                                                                                                                 |
| SendFailed    | Tổng số tin thất bại                                                                                                                                                                                       |
| SendSuccess   | Tổng số tin thành công                                                                                                                                                                                     |
| SendStatus    | Trạng thái tin nhắn                                                                                                                                                                                        |
|               | <ul><li>Trạng thái 2: Chờ gửi </li><li>Trạng thái 5: Đã gửi </li></ul>                                                                                                                                     |
| TotalPrice    | Tổng số tiền của tin                                                                                                                                                                                       |
| TotalReceiver | Tổng số tin                                                                                                                                                                                                |
| TotalSent     | Tổng số tin đã gửi                                                                                                                                                                                         |
| RequestId     | Request mà KH truyền vào API để gửi tin                                                                                                                                                                    |
| TypeId        | Loại tin nhắn                                                                                                                                                                                              |
|               | <ul><li>Type 24: Zalo Ưu Tiên</li><li>Type 25: Zalo Bình Thường</li></ul>                                                                                                                                  |
| Telcoid       | Mạng viễn thông của thuê bao nhận tin                                                                                                                                                                      |
|               | <ul><li>Mạng số 1: Viettel</li><li>Mạng số 2: Mobifone</li><li>Mạng số 3: Vinaphone</li><li>Mạng số 4: Vietnammobile</li><li>Mạng số 5: Gmobile</li><li>Mạng số 6: Itel</li><li>Mạng số 7: Reddi</li></ul> |
| PhoneNumber   | Số điện thoại nhận tin                                                                                                                                                                                     |
| CallbackUrl   | Link nhận callback                                                                                                                                                                                         |
| Partnerids    | Mã của tin nhắn vừa được gửi (do Zalo trả về)                                                                                                                                                              |
| ErrorInfo     | Mã lỗi và thông tin lỗi của tin nhắn                                                                                                                                                                       |
| OAId          | Id của OA mà KH gửi tin                                                                                                                                                                                    |
| ZnsTempId     | Id của template KH gửi tin                                                                                                                                                                                 |

{% hint style="info" %}
Chú ý:

* Hiện tại số lần request là 1s cho 1 lần request
* Số ReferenceId tối đa cho 1 lần request là 100
* Thời gian request là vào lúc 01:00 đến 02:00 AM mỗi ngày
{% endhint %}

