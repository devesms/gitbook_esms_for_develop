---
description: >-
  Đối với các Brandname SMS, các doanh nghiệp sẽ cần đăng ký Template là các tin
  nhắn mẫu với nhà mạng trước khi được gửi. Hàm này cho phép lấy về danh sách
  các Template của 1 Brandname thuộc tài khoản
---

# Hàm lấy danh sách template tin chăm sóc khách hàng

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetTemplate/](http://rest.esms.vn/MainService.svc/json/GetTemplate/)\
  Method: POST\
  Content Type: application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/GetTemplate/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=owevtxyrtqm5gvj5zwjfeb2z' \
--data-raw '{
 "ApiKey":"{{ApiKey}}",
 "SecretKey":"{{SecretKey}}",
 "SmsType":"2",
 "Brandname":"Baotrixemay"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                              |
| -------------------------------------------- | ------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                    |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                 |
| SmsType <mark style="color:red;">\*</mark>   | <p>Loại tin nhắn<br>2: Loại tin Chăm sóc khách hàng</p> |
| BrandName <mark style="color:red;">\*</mark> | Tên brandname                                           |

* Mẫu kết quả trả về

```
{
    "BrandnameTemplates": [
        {
            "NetworkID": 6,
            "TempContent": "{P1,20} la ma xac minh dang ky Baotrixemay cua ban",
            "TempId": 458
        },
        {
            "NetworkID": 4,
            "TempContent": "Baotrixemay da nhan duoc so tien thanh toan {P2,20} VND luc {P2,20} cho don hang {P1,20}. Cam on quy khach!",
            "TempId": 466
        },
        {
            "NetworkID": 2,
            "TempContent": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "TempId": 12640
        },
        {
            "NetworkID": 5,
            "TempContent": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "TempId": 12647
        },
        {
            "NetworkID": 3,
            "TempContent": "Chuc mung sinh nhat {P2,50}. Kinh chuc QK co nhieu suc khoe, thanh cong va hanh phuc! Nhan dip sinh nhat xin gui den {P2,50} coupon {P2,20}. Tran trong.",
            "TempId": 12899
        },
        {
            "NetworkID": 1,
            "TempContent": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "TempId": 12884
        }
    ],
    "CodeResult": "100",
    "ErrorMessage": "success"
}
```

* Thông tin kết quả trả về

| Biến        | Định nghĩa                                                                                         |
| ----------- | -------------------------------------------------------------------------------------------------- |
| NetworkID   | <p>1: Viettel<br>2: Mobi<br>3: Vinaphone<br>4: Vietnammobile<br>5: Gtel<br>6: Itel<br>7: Reddi</p> |
| TempContent | Content đã đăng ký với nhà mạng                                                                    |
| TempId      | TempId của nhà mạng                                                                                |
