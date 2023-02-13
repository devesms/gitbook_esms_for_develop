# Hàm lấy danh sách template Zalo OTT

* HTTP request\
  URL: [https://rest.esms.vn/MainService.svc/json/GetTemplate/](https://rest.esms.vn/MainService.svc/json/GetTemplate/)\
  Method: POST\
  Content Type: application/json

```
curl --location --request POST 'https://rest.esms.vn/MainService.svc/json/GetTemplate/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=x04tc1ao4ggn2g5nghk25ogr' \
--data-raw '{
  "ApiKey": "{{ApiKey}}",
  "SecretKey": "{{SecretKey}}",
  "OAId": "4097311281936189049",
  "SmsType": "24"
}'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                  |
| -------------------------------------------- | ----------------------------------------------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                        |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                     |
| OAId <mark style="color:red;">\*</mark>      | ID của OA cần lấy template                                  |
| SmsType <mark style="color:red;">\*</mark>   | <p>Loại tin<br>24: Zalo ưu tiên<br>25: Zalo bình thường</p> |

* Mẫu kết quả trả về

```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "ZNSTemplates": [
        {
            "TempContent": "<div class=\"group-desc\" style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); color: #131820; font-family: Muli, sans-serif; font-size: 16px;\"> <p style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); margin: 0px; padding: 0px; color: #394e60; font-size: 0.875rem; line-height: 20px;\">Mã OTP của bạn là</p> </div> <p><span class=\"otp-code\" style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); font-weight: bold; color: #131820; font-size: 1.5rem; letter-spacing: 3.75px; line-height: 24px; display: block; padding: 12px 0px; font-family: Muli, sans-serif;\">{{otp}}</span></p> <div class=\"group-desc\" style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); color: #131820; font-family: Muli, sans-serif; font-size: 16px;\"> <p style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); margin: 0px; padding: 0px; color: #394e60; font-size: 0.875rem; line-height: 20px;\">Không tiết lộ cho bất kỳ ai, Mã xác nhận sẽ có hiệu lực trong 5 phút.</p> </div>",
            "TempId": 205644,
            "TempName": "Xác nhận đăng ký dịch vụ",
            "ZNSTempDetail": [
                {
                    "Limit": 10,
                    "Param": "otp",
                    "ParamLevel": 1,
                    "RequireType": "type_text"
                }
            ]
        }
    ]
}
```

* Thông tin kết quả trả về

|               |                       |
| ------------- | --------------------- |
| TempContent   | Nội dung của template |
| Tempid        | Template ID           |
| TempName      | Tên template          |
| ZNSTempDetail | Chi tiết của template |
| Limit         | Độ dài của template   |
| Param         | Tên biến              |
| ParamLevel    | Thứ tự biến           |
| RequireType   | Kiểu dữ liệu của biến |
