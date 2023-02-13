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
    "Data": [
        {
            "feedbacks": [
                "Nhân viên tư vấn nhiệt tình, thái độ vui vẻ, dễ thương",
                "Chính sách hỗ trợ rõ ràng, đầy đủ và dễ hiểu",
                "Chất lượng sản phẩm rất tốt",
                "Giao hàng nhanh",
                "Dịch vụ chăm sóc rất tốt"
            ],
            "msgId": "5dcf84fe1fd8bd85e4ca",
            "note": "Tuyệt vời",
            "rate": 5,
            "submitDate": "1659750276218",
            "trackingId": "0d22e763-adef-4d33-a612-76e63f7c1b58"
        }
    ],
    "Total": 1
}    
```

* Thông tin kết quả trả về

| Biến       | Định nghĩa                                                                                                                                                                                                                          |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| feedbacks  | Tổng số tin được gửi trong ngày                                                                                                                                                                                                     |
| msgId      | SmsId của Zalo                                                                                                                                                                                                                      |
| note       | Ghi chút của khách hàng cho đánh giá                                                                                                                                                                                                |
| rate       | Số sao khách hàng đánh giá                                                                                                                                                                                                          |
| submitDate | <p>submitDate: Thời điểm khách hàng submit đánh giá. Biến submitDate sẽ có giá trị trong khoảng thời gian từ from_time đến to_time (được truyền vào từ request). <br><strong>Lưu ý: Tính theo timestamp (millisecond).</strong></p> |
| trackingId | Tracking ID từ phía đối tác truyền vào khi gửi ZNS                                                                                                                                                                                  |
| Total      | Tổng số lượt đánh giá                                                                                                                                                                                                               |
