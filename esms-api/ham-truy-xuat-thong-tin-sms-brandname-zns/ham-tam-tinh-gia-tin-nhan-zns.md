# Hàm tạm tính giá tin nhắn ZNS

* HTTP request \
  URL: [http://rest.esms.vn/MainService.svc/json/SummaryZaloMessage\_V4\_post\_json/](http://rest.esms.vn/MainService.svc/json/SummaryZaloMessage\_V4\_post\_json/)\
  Method: POST \
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SummaryZaloMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=ghob0j1dr00pujmvzhk5w4nk' \
--data-raw '{
 "ApiKey": "{{ApiKey}}",
 "SecretKey": "{{SecretKey}}",
 "Phone": "0901888484",
 "Params": ["value1","value2","value3"],
 "TempID": "......",
 "OAID": "......"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                                                                                                                               |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                                                                                                                     |
| SecretKey <mark style="color:red;">\*</mark> | SecretKey của tài khoản                                                                                                                                                                                                                                  |
| Phone <mark style="color:red;">\*</mark>     | Số điện thoại nhận tin                                                                                                                                                                                                                                   |
| Params <mark style="color:red;">\*</mark>    | <p></p><p>Nội dung gửi đến người nhận <br><strong>*Lưu ý:</strong></p><ol><li><strong>Các tham số truyền vào phải đúng thứ tự như template bạn đăng ký</strong></li><li><strong>Nếu tham số trùng nhau chỉ cần truyền vào một tham số</strong></li></ol> |
| TempID <mark style="color:red;">\*</mark>    | Template của Zalo OA mà khách hàng đăng kí với eSMS                                                                                                                                                                                                      |
| OAID <mark style="color:red;">\*</mark>      | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. <br>Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này.<br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p>                        |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "TotalPrice": 660.0000,
    "TotalReceiver": 1
}
```

* Thông tin kết quả trả về

| Biến          | Định nghĩa                  |
| ------------- | --------------------------- |
| TotalPrice    | Tổng tiền tin               |
| TotalReceiver | Tổng số điện thoại nhận tin |
