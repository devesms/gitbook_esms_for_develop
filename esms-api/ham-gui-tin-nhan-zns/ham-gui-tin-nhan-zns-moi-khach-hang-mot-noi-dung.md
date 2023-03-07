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
"CallbackUrl":"{OAID}"
}
```



* Thông tin request

| Biến                                                                                                              | Định nghĩa                                                                                                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Phone <mark style="color:red;">\*</mark>                                                                          | Số điện thoại người nhận                                                                                                                                                                                                       |
| ApiKey **** <mark style="color:red;">\*</mark>                                                                    | ApiKey của tài khoản                                                                                                                                                                                                           |
| SecretKey <mark style="color:red;">****</mark> <mark style="color:red;"></mark><mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                                                                                                                                                                        |
| CallbackUrl                                                                                                       | eSMS sẽ trả về kết quả của tin nhắn.                                                                                                                                                                                           |
| OAID <mark style="color:red;">****</mark> <mark style="color:red;"></mark><mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| TempID <mark style="color:red;">****</mark> <mark style="color:red;"></mark><mark style="color:red;">\*</mark>    | Template của Zalo OA mà khách hàng đăng kí với eSMS                                                                                                                                                                            |
| Params <mark style="color:red;">****</mark> <mark style="color:red;"></mark><mark style="color:red;">\*</mark>    | <p></p><p>Giá trị cần truyền cho các biến trong Template *Lưu ý:</p><ol><li>Các tham số truyền vào phải đúng thứ tự như template bạn đăng ký</li><li>Nếu tham số trùng nhau chỉ cần truyền vào một tham số</li></ol>           |

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
