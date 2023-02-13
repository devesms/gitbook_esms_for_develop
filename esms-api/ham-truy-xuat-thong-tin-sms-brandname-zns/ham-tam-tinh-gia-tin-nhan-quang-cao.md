# Hàm tạm tính giá tin nhắn Quảng cáo

* HTTP request \
  URL: [http://rest.esms.vn/MainService.svc/json/SummaryMultipleSMSBrandname/](http://rest.esms.vn/MainService.svc/json/SummaryMultipleSMSBrandname/)\
  Method: POST \
  Content Type: text/plain

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SummaryMultipleSMSBrandname/' \
--header 'Content-Type: text/plain' \
--header 'Cookie: ASP.NET_SessionId=hxev0olj4ur555cahsba5lso' \
--data-raw '<RQST>
<APIKEY>{{ApiKey}}</APIKEY>
<SECRETKEY>{{SecretKey}}</SECRETKEY>
<CONTENT>Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!</CONTENT>
<SMSTYPE>1</SMSTYPE>
<BRANDNAME>QC_ONLINE</BRANDNAME>
<CONTACTS>
<CUSTOMER><PHONE>0901888484</PHONE></CUSTOMER>
<CUSTOMER><PHONE>. . . .</PHONE></CUSTOMER>
<CUSTOMER><PHONE>. . . .</PHONE></CUSTOMER>
<CUSTOMER><PHONE>. . . .</PHONE></CUSTOMER>
<CUSTOMER><PHONE>. . . .</PHONE></CUSTOMER>
<CUSTOMER><PHONE>. . . .</PHONE></CUSTOMER>
</CONTACTS>
</RQST>'
```

* Thông tin request

| Biến                                         | Định nghĩa                                     |
| -------------------------------------------- | ---------------------------------------------- |
| APIKEY <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                           |
| SECRETKEY <mark style="color:red;">\*</mark> | SecretKey của tài khoản                        |
| CONTENT <mark style="color:red;">\*</mark>   | Nội dung tin nhắn                              |
| SMSTYPE <mark style="color:red;">\*</mark>   | Loại tin nhắn, SmsType = 1: Loại tin Quảng cáo |
| BRANDNAME <mark style="color:red;">\*</mark> | Tên thương hiệu                                |
| PHONE <mark style="color:red;">\*</mark>     | Số điện thoại nhận tin                         |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "TotalPrice": 1691300.0000,
    "TotalReceiver": 2997
}
```

* Thông tin kết quả trả về

| Biến          | Định nghĩa                  |
| ------------- | --------------------------- |
| TotalPrice    | Tổng tiền tin               |
| TotalReceiver | Tổng số điện thoại nhận tin |
