# Gửi tin Chăm sóc khách hàng (TypeSMS 2) dạng GET

* HTTP request\
  URL: <mark style="color:blue;">http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_get?Phone={Phone}\&Content={Content}\&ApiKey={ApiKey}\&SecretKey={SecretKey}\&IsUnicode={IsUnicode}\&Brandname={Brandname}\&SmsType={SmsType}\&CallbackUrl={CallbackUrl}\&RequestId={RequestId}</mark>\
  Method: GET

```
curl --location -g --request GET 'http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_get?Phone={Phone}&Content={Content}&ApiKey={ApiKey}&SecretKey={SecretKey}&IsUnicode={IsUnicode}&Brandname={Brandname}&SmsType={SmsType}&CallbackUrl={CallbackUrl}&RequestId={RequestId}&SendDate=2022-08-03 10:00:00' \
--header 'Cookie: ASP.NET_SessionId=4zhxi2iaxcyqrlooff2u3vj1'
```

* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                                              |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Phone <mark style="color:red;">\*</mark>     | Số điện thoại nhận tin                                                                                                                                  |
| Content <mark style="color:red;">\*</mark>   | Nội dung tin nhắn                                                                                                                                       |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                                    |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                                                                                                 |
| Unicode                                      | <p>Gửi nội dung có dấu<br>1: Có dấu<br>0: Không dấu</p>                                                                                                 |
| Brandname <mark style="color:red;">\*</mark> | <p>Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |
| SmsType <mark style="color:red;">\*</mark>   | <p>Loại tin nhắn<br>2: Tin CSKH</p>                                                                                                                     |
| CallbackUrl                                  | Kết quả tin nhắn eSMS trả về                                                                                                                            |
| RequestId                                    | <p>ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa.<br>Ví dụ: requestid=123456</p>                   |
| SendDate                                     | <p>Thời gian hẹn gửi của tin. <br>Không truyền khi tin muốn tin nhắn gửi đi liền.<br>Định dạng: yyyy-mm-dd hh:MM:ss</p>                                 |
| SandBox                                      | <p>1: Tin thử nghiệm, không gửi tin nhắn, chỉ trả về kết quả SMS, tin không lưu hệ thống và không trừ tiền.<br>0: Không thử nghiệm, tin đi thật.</p>    |

* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

* Thông tin kết quả trả về

| Biến  | Định nghĩa                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |
