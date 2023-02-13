---
description: >-
  API dùng để gửi tin Quảng cáo đến khách hàng. Mỗi request tối thiểu 30 số để
  được duyệt tin và tối đa 5000 số.
---

# Gửi tin Quảng cáo (TypeSMS 1)

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname](http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname)\
  Method: POST\
  Content Type: text/plain

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname' \
--header 'Content-Type: text/plain' \
--data-raw '<RQST>
<APIKEY>{APIKEY}</APIKEY>
<SECRETKEY>{SECRETKEY}</SECRETKEY>
<CONTENT>{CONTENT}</CONTENT>
<SMSTYPE>1</SMSTYPE>
<BRANDNAME>{BRANDNAME}</BRANDNAME>
<CONTACTS>
<CUSTOMER><PHONE>{PHONE}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{PHONE}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{PHONE}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{PHONE}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{PHONE}</PHONE></CUSTOMER>
</CONTACTS>
</RQST>'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                              |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| APIKEY <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                    |
| SECRETKEY <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                                                                                                 |
| CONTENT <mark style="color:red;">\*</mark>   | Nội dung tin nhắn                                                                                                                                       |
| SMSTYPE <mark style="color:red;">\*</mark>   | <p>Loại tin nhắn<br>1: Tin quảng cáo</p>                                                                                                                |
| BRANDNAME <mark style="color:red;">\*</mark> | <p>Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| PHONE <mark style="color:red;">\*</mark>     | Số điện thoại nhận tin nhắn.                                                                                                                            |
| SENDDATE                                     | <p>Thời gian hẹn gửi của tin. <br>Không truyền khi tin muốn tin nhắn gửi đi liền.<br>Định dạng: yyyy-mm-dd hh:MM:ss</p>                                 |
| CALLBACKURL                                  | [https://developers.esms.vn/esms-api/callback-url](https://developers.esms.vn/esms-api/callback-url)                                                    |

* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

* Thông tin kết quả trả về

| Biến  | Định nghĩa                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |
