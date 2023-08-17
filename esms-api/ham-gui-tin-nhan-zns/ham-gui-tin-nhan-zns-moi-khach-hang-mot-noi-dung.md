---
description: >-
  Giải pháp Multi-Channel Messaging API cho phép bạn gửi tin nhắn đến khách hàng
  đi qua các kênh giao tiếp khác nhau như Zalo, SMS, Viber theo các thứ tự ưu
  tiên.
---

# Hàm gửi tin nhắn ZNS mỗi khách hàng một nội dung

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/Send\_zns\_bulk\_v4\_post\_json/](http://rest.esms.vn/MainService.svc/json/Send\_zns\_bulk\_v4\_post\_json/)\
  Method: POST\
  Content Type: application/json

```
{
"ApiKey": "{ApiKey}",
"SecretKey": "{SecretKey}",
"TempID": "{TempID}",
"Data": [
{"Phone":"{Phone}","Params":["value1","value2","value3"]},
{"Phone":"{Phone}","Params":["value1","value2","value3"]},
{"Phone":"{Phone}","Params":["value1","value2","value3"]}
],
"OAID":"{OAID}",
"CallbackUrl":"{CallbackUrl}"
}
```



* Thông tin request

<table><thead><tr><th width="236">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>Phone <mark style="color:red;">*</mark></td><td>Số điện thoại người nhận</td></tr><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn.</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>TempID <mark style="color:red;">*</mark></td><td>Template của Zalo OA mà khách hàng đăng kí với eSMS</td></tr><tr><td>Params <mark style="color:red;">*</mark></td><td><p></p><p>Giá trị cần truyền cho các biến trong Template *Lưu ý:</p><ol><li>Các tham số truyền vào phải đúng thứ tự như template bạn đăng ký</li><li>Nếu tham số trùng nhau chỉ cần truyền vào một tham số</li></ol></td></tr></tbody></table>

* Kết quả trả về

```
{
    "CodeResult": "100",
    "Message": "Sucess",
    "TotalSuccess": 2,
    "detail": [
        {
            "CodeResult": "100",
            "Phone": "{Phone}",
            "SMSID": "a037b928-cb7e-4bfc-bdf9-0286318163aa264"
        },
        {
            "CodeResult": "100",
            "Phone": "{Phone}",
            "SMSID": "b83ff06e-8989-4b0d-818e-795b96699e86264"
        }
    ]
}
```

* Thông tin kết quả trả về

|       |                                                                                                   |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |
