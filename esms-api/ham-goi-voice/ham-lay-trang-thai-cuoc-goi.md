---
description: >-
  Hàm cho phép bạn gửi tin nhắn thoại đến 1 số điện thoại bởi file ghi âm đã
  tạo.
---

# Hàm lấy trạng thái cuộc gọi

* HTTP request\
  URL: [http://voiceapi.esms.vn/MainService.svc/json/GetSendStatus?ApiKey={ApiKey}\&SecretKey={SecretKey}\&ReferenceId={SMSID}](http://voiceapi.esms.vn/MainService.svc/json/GetSendStatus?ApiKey={ApiKey}\&SecretKey={SecretKey}\&ReferenceId={SMSID})[  ](http://voiceapi.esms.vn/MainService.svc/json/MakeCallTemplate\_V2?ApiKey={ApiKey}\&SecretKey={SecretKey}\&TemplateId={TemplateId}\&Phone={Phone}\&VariableListStr={VariableListStr}\&SendDate={SendDate}\&Voice={Voice}\&Speed={Speed}\&CallbackUrl={CallbackUrl}\&RequestId={RequestId})\
  Method: GET

{% code overflow="wrap" %}
```
curl --location --request GET 'http://voiceapi.esms.vn/MainService.svc/json/GetSendStatus?ApiKey={ApiKey}&SecretKey={SecretKey}&ReferenceId={SMSID}' \
--header 'Cookie: ASP.NET_SessionId=b31sfztncr4yoznoxr2dpve1'
```
{% endcode %}

* Thông tin request

| Biến        | Định nghĩa               |
| ----------- | ------------------------ |
| ApiKey      | ApiKey của tài khoản.    |
| SecretKey   | Secretkey của tài khoản. |
| ReferenceId | SMSID khi gọi trả về.    |

* Kết quả trả về

```
{
    "CallDuration": 13,
    "CallStatus": "ANSWERED",
    "CodeResponse": "100",
    "Ivr": "",
    "ReferenceId": "505139D7-54F8-48A9-88FA-9460A78731DD",
    "SendStatus": 5,
    "SentResult": 1
}
```

* Thông tin kết quả trả về

| Biến         | Định nghĩa                                                                                                  |
| ------------ | ----------------------------------------------------------------------------------------------------------- |
| CallDuration | ID của cuộcgoji mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái cuộc gọi.           |
| CallStatus   | Kết quả của cuộc gọi (ANSWERED: cuộc gọi được trả lời, NOANSWERED: cuộc gọi thất bại hoặc không ai bắt máy) |
| Ivr          | Phím phản hồi của người nghe                                                                                |
| ReferenceId  | SMSID tin nhắn check trạng thái                                                                             |
| SendStatus   | <p>Trạng thái tin nhắn<br>5: Đã gửi xong</p>                                                                |
| SentResult   | <p>Kết quả tin nhắn<br>0: Thất bại<br>1: Thành công</p>                                                     |
