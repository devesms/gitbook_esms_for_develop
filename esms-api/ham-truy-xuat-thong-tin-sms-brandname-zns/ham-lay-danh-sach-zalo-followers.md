# Hàm lấy danh sách Zalo Followers

* HTTP request \
  URL: [http://rest.esms.vn/MainService.svc/json/ZNS/GetFollowers/](http://rest.esms.vn/MainService.svc/json/ZNS/GetFollowers/)\
  Method: POST \
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/ZNS/GetFollowers/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=ghob0j1dr00pujmvzhk5w4nk' \
--data-raw '{
 "ApiKey":"{{ApiKey}}",
 "SecretKey":"{{SecretKey}}",
 "OAID":"......",
 "Offset": ...,
 "Count": ...
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                                                                                                        |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                                                                                              |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản                                                                                                                                                                                                           |
| OAID <mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. <br>Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này.<br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| Offset <mark style="color:red;">\*</mark>    | Lấy bắt đầu từ đánh giá thứ bao nhiêu                                                                                                                                                                                             |
| Limit <mark style="color:red;">\*</mark>     | Số lượng đánh giá cần xem                                                                                                                                                                                                         |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "Followers": [
        {
            "User_Id": "7800378501923859642"
        },
        {
            "User_Id": "4176617840488517388"
        },
        {
            "User_Id": "7000997455428487634"
        },
        {
            "User_Id": "5889364632581220929"
        }
    ],
    "Total": 208
}
```

* Thông tin kết quả trả về

| Biến      | Định nghĩa                      |
| --------- | ------------------------------- |
| Followers | Danh sách UserId Zalo follow OA |
| Total     | Tổng UserId follow OA           |
