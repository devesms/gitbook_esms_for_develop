# Hàm kiểm tra chất lượng OA

* HTTP request \
  URL: [http://rest.esms.vn/MainService.svc/json/ZNS/GetQuality/](http://rest.esms.vn/MainService.svc/json/ZNS/GetQuality/)\
  Method: POST \
  Content Type: application/json

```
curl --location 'http://rest.esms.vn/MainService.svc/json/ZNS/GetQuality/' \
--header 'Content-Type: application/json' \
--data '{
 "ApiKey": "{{ApiKey}}",
 "OAID": "{{OAID}}",
 "SecretKey": "{{SecretKey}}"
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
    "Oa7dayQuality": "UNDEFINED",
    "OaCurrentQuality": "UNDEFINED"
}
```

* Thông tin kết quả trả về

| Biến             | Định nghĩa                                                                                                                                                                                                                                                                                                                                                          |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Oa7dayQuality    | <p>Chất lượng gửi thông báo ZNS trong 7 ngày gần nhất của OA. Các giá trị trả về:</p><p></p><ul><li>HIGH - Mức độ chất lượng tốt</li><li>MEDIUM - Mức độ chất lượng trung bình</li><li>LOW - Mức độ chất lượng kém</li><li>UNDEFINED - Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá)</li></ul> |
| OaCurrentQuality | <p>Chất lượng gửi thông báo ZNS trong 48 giờ gần nhất của OA. Các giá trị trả về:</p><ul><li>HIGH - Mức độ chất lượng tốt </li><li>MEDIUM - Mức độ chất lượng trung bình </li><li>LOW - Mức độ chất lượng kém </li><li>UNDEFINED - Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá)</li></ul>     |

