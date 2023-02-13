# Hàm lấy danh sách Zalo OA



* HTTP request \
  URL: [http://rest.esms.vn/MainService.svc/json/ZNS/GetListZOA/](http://rest.esms.vn/MainService.svc/json/ZNS/GetListZOA/)\
  Method: POST \
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/ZNS/GetListZOA/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=4zhxi2iaxcyqrlooff2u3vj1' \
--data-raw '{
 "ApiKey":"{{ApiKey}}",
 "SecretKey":"{{SecretKey}}"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa              |
| -------------------------------------------- | ----------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản    |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "ZOAList": [
        {
            "OAID": "745830328927467685",
            "OAName": "Hệ thống ESMS Marketing"
        },
        {
            "OAID": "4097311281936189049",
            "OAName": "SVoucher"
        }
    ]
}   
```

* Thông tin kết quả trả về

| Biến   | Định nghĩa                                                                                                                                                                                                                        |
| ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| OAID   | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. <br>Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này.<br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| OAName | Tên của OA ID                                                                                                                                                                                                                     |
