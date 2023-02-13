# Hàm tạm tính giá tin nhắn CSKH

* HTTP request \
  URL: http://rest.esms.vn/MainService.svc/json/SummaryMultipleMessage\_V4\_get?ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}} \&Brandname=Baotrixemay\&SmsType=2\&Phone=0901888484\&Content=Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh! \
  Method: GET

```
curl --location --request GET 'http://rest.esms.vn/MainService.svc/json/SummaryMultipleMessage_V4_get?Phone=0901888484&Content=Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&SmsType=2&BrandName=Baotrixemay' \
--header 'Cookie: ASP.NET_SessionId=hxev0olj4ur555cahsba5lso'
```

* Thông tin request

| Biến                                         | Định nghĩa                                               |
| -------------------------------------------- | -------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                     |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản                                  |
| Brandname <mark style="color:red;">\*</mark> | Tên thương hiệu                                          |
| SmsType <mark style="color:red;">\*</mark>   | Loại tin nhắn, SmsType = 2: Loại tin chăm sóc khách hàng |
| Phone <mark style="color:red;">\*</mark>     | Số điện thoại nhận tin                                   |
| Content <mark style="color:red;">\*</mark>   | Nội dung tin nhắn                                        |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "TotalPrice": 850,
    "TotalReceiver": 1
}
```

* Thông tin kết quả trả về

| Biến          | Định nghĩa                  |
| ------------- | --------------------------- |
| TotalPrice    | Tổng tiền tin               |
| TotalReceiver | Tổng số điện thoại nhận tin |
