# Hàm lấy Quota ZNS

* HTTP request \
  URL: [http://rest.esms.vn/MainService.svc/json/ZNS/GetQuota/](http://rest.esms.vn/MainService.svc/json/ZNS/GetQuota/)\
  Method: POST \
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/ZNS/GetQuota/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=ghob0j1dr00pujmvzhk5w4nk' \
--data-raw '{
 "ApiKey": "{{ApiKey}}",
 "OAID": "{{SecretKey}}",
 "SecretKey": "....."
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                                                                                                        |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                                                                                              |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản                                                                                                                                                                                                           |
| OAID <mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. <br>Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này.<br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "DailyQuota": 500,
    "RemainingQuota": 500
}
```

* Thông tin kết quả trả về

| Biến           | Định nghĩa                      |
| -------------- | ------------------------------- |
| DailyQuota     | Tổng số tin được gửi trong ngày |
| RemainingQuota | Số tin còn lại                  |
