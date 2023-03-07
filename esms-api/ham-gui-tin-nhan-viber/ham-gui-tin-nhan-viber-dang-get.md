---
description: Cho phép bạn gửi tin nhắn đến số điện thoại đang sử sụng Viber
---

# Hàm gửi tin nhắn Viber dạng GET

<figure><img src="../../.gitbook/assets/z3805790275867_46e18e1f7da57a7b7dff1484f0d4e7c2.jpg" alt=""><figcaption><p>Tin mẫu Viber</p></figcaption></figure>

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_get?SmsType={SmsType}\&OTTUrl={OTTUrl}\&OTTImgUrl={OTTImgUrl}\&Phone={Phone}\&Content={Content}\&ApiKey={ApiKey}\&SecretKey={SecretKey}\&Brandname={Brandname}\&OTTLabel={OTTLabel}\&CallbackUrl={CallbackUrl}](http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_get?SmsType={SmsType}\&OTTUrl={OTTUrl}\&OTTImgUrl={OTTImgUrl}\&Phone={Phone}\&Content={Content}\&ApiKey={ApiKey}\&SecretKey={SecretKey}\&Brandname={Brandname}\&OTTLabel={OTTLabel}\&CallbackUrl={CallbackUrl})\
  Method: GET

```
curl --location --request GET 'http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_get?SmsType={SmsType}&OTTUrl={OTTUrl}&OTTImgUrl={OTTImgUrl}&Phone={Phone}&Content={Content}&ApiKey={ApiKey}&SecretKey={SecretKey}&Brandname={Brandname}&OTTLabel={OTTLabel}&CallbackUrl={CallbackUrl}' \
--header 'Cookie: ASP.NET_SessionId=hv0fnv0mv4i0qnmx2zrxetvf'
```

*
* Thông tin request

| Biến                                         | Định nghĩa                                                                                                                             |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| SmsType <mark style="color:red;">\*</mark>   | <p>Loại tin nhắn<br>23: Tin nhắn OTT Viber</p>                                                                                         |
| OTTUrl                                       | Đường dẫn tên nút                                                                                                                      |
| OTTImgUrl                                    | Đường dẫn hình ảnh                                                                                                                     |
| Phone <mark style="color:red;">\*</mark>     | Số điện thoại người nhận                                                                                                               |
| Content <mark style="color:red;">\*</mark>   | Nội dung gửi đến người nhận                                                                                                            |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản                                                                                                                   |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản                                                                                                                |
| Brandname <mark style="color:red;">\*</mark> | Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn đó). Chú ý: sẽ phải đăng ký trước khi sử dụng.            |
| OTTLabel                                     | Tên nút                                                                                                                                |
| RequestId                                    | <p>ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. <br>Ví dụ: RequestId=123456</p> |
| CallbackUrl                                  | eSMS sẽ trả về kết quả của tin nhắn.                                                                                                   |

* **Lưu ý:** Tin nhắn OTT có thể có các lựa chọn sau:\
  \- OTTUrl – OTTImgUrl – Content – OTTLabel\
  \- Content – OTTLabel – OTTUrl\
  \- OTTImgUrl\
  \- Content
* Kết quả trả về

```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

* Thông tin kết quả trả về

|       |                                                                                                   |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của tin nhắn mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái tin nhắn. |
