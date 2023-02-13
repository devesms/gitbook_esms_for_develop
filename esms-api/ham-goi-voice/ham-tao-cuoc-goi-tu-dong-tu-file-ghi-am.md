---
description: >-
  Hàm cho phép bạn gửi tin nhắn thoại đến 1 số điện thoại bởi file ghi âm đã
  tạo.
---

# Hàm tạo cuộc gọi tự động từ file ghi âm

* HTTP request\
  URL: [http://voiceapi.esms.vn/MainService.svc/json/MakeCallRecord\_V2?ApiKey={ApiKey}\&SecretKey={SecretKey}\&TemplateId={RecordId}\&Phone={Phone}\&SendDate={SendDate}\&NumberForward={NumberForward}\&MaxRepeat={MaxRepeat}\&MaxRetry={MaxRetry}\&Ivr={Ivr}\&TimeWaitToIvr={TimeWaitToIvr}\&WaitRetry={WaitRetry}\&CallbackUrl={CallbackUrl}\&RequestID={RequestId}](http://voiceapi.esms.vn/MainService.svc/json/MakeCallRecord\_V2?ApiKey={ApiKey}\&SecretKey={SecretKey}\&TemplateId={RecordId}\&Phone={Phone}\&SendDate={SendDate}\&NumberForward={NumberForward}\&MaxRepeat={MaxRepeat}\&MaxRetry={MaxRetry}\&Ivr={Ivr}\&TimeWaitToIvr={TimeWaitToIvr}\&WaitRetry={WaitRetry}\&CallbackUrl={CallbackUrl}\&RequestID={RequestId})[  ](http://voiceapi.esms.vn/MainService.svc/json/MakeCallTemplate\_V2?ApiKey={ApiKey}\&SecretKey={SecretKey}\&TemplateId={TemplateId}\&Phone={Phone}\&VariableListStr={VariableListStr}\&SendDate={SendDate}\&Voice={Voice}\&Speed={Speed}\&CallbackUrl={CallbackUrl}\&RequestId={RequestId})\
  Method: GET

```
curl --location -g --request GET 'http://voiceapi.esms.vn/MainService.svc/json/MakeCallRecord_V2?ApiKey={ApiKey}&SecretKey={SecretKey}&TemplateId={RecordId}&Phone={Phone}&SendDate={SendDate}&NumberForward={NumberForward}&MaxRepeat={MaxRepeat}&MaxRetry={MaxRetry}&Ivr={Ivr}&TimeWaitToIvr={TimeWaitToIvr}&WaitRetry={WaitRetry}&CallbackUrl={CallbackUrl}&RequestID={RequestId}'
```

* Thông tin request

| Biến          | Định nghĩa                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey        | ApiKey của tài khoản                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| SecretKey     | Secretkey của tài khoản                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| TemplateId    | Id file ghi âm tạo trên trang account.esms.vn                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Phone         | Số điện thoại nhận tin                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| NumberForward | Số điện thoại được chuyển đến khi nhập đúng Ivr                                                                                                                                                                                                                                                                                                                                                                                                                 |
| SendDate      | Đặt lịch gửi tin (định dạng: yyyy/MM/dd hh:mm:ss) Ví dụ: 2017/12/12 14:00:00                                                                                                                                                                                                                                                                                                                                                                                    |
| MaxRepeat     | Số lần lặp lại file ghi âm khi nghe                                                                                                                                                                                                                                                                                                                                                                                                                             |
| MaxRetry      | Số lần gọi lại khi người nhận không bắt máy                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Ivr           | Phím quy định khi người nhận bấm để chuyển số (phím từ: 0-9)                                                                                                                                                                                                                                                                                                                                                                                                    |
| TimeWaitToIvr | Thời gian chờ tối đa để người gọi nhấn phím                                                                                                                                                                                                                                                                                                                                                                                                                     |
| WaitRetry     | Khoảng cách giữa các lần gọi lại khi người nhận không bắt máy (đơn vị: giây)                                                                                                                                                                                                                                                                                                                                                                                    |
| CallbackUrl   | <p></p><p>Url nhận callback kết quả cuộc gọi (mẫu: http://xxxx.com?ReferenceId=&#x26;CallDuration=&#x26;CallSt atus=&#x26;Ivr=&#x26;Price=&#x26;SentResult&#x26;CID= )</p><ul><li>CallDuration: độ dài cuộc gọi</li><li>CallStatus: kết quả cuộc gọi (ANSWERED, NO ANSWER)</li><li>Ivr: phím bấm của khách hàng</li><li>Price: giá cuộc gọi</li><li>SentResult: Kết quả gửi tin qua nhà mạng (0: thất bại, 1: thành công)</li><li>CID: đầu số gửi tin</li></ul> |
| RequestId     | ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. Ví dụ: requestid=123456                                                                                                                                                                                                                                                                                                                                     |

* Kết quả trả về

```
{
 "CodeResult": "100",
 "SMSID": "8eb2af6d-fb4c4814-b9cc-4c0e3ed32edf "
}
```

* Thông tin kết quả trả về

| Biến  | Định nghĩa                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------- |
| SMSID | ID của cuộcgoji mới được tạo ra trên hệ thống eSMS. Dùng ID này để query lấy trạng thái cuộc gọi. |
