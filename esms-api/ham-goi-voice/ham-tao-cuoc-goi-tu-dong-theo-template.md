---
description: >-
  Hàm cho phép bạn gửi tin nhắn thoại đến 1 số điện thoại bởi mẫu cuộc gọi đã
  được tạo sẵn trên hệ thống.
---

# Hàm tạo cuộc gọi tự động theo Template

* HTTP request\
  URL: [http://voiceapi.esms.vn/MainService.svc/json/MakeCallTemplate\_V2?ApiKey={ApiKey}\&SecretKey={SecretKey}\&TemplateId={TemplateId}\&Phone={Phone}\&VariableListStr={VariableListStr}\&SendDate={SendDate}\&Voice={Voice}\&Speed={Speed}\&CallbackUrl={CallbackUrl}\&RequestId={RequestId}](http://voiceapi.esms.vn/MainService.svc/json/MakeCallTemplate\_V2?ApiKey={ApiKey}\&SecretKey={SecretKey}\&TemplateId={TemplateId}\&Phone={Phone}\&VariableListStr={VariableListStr}\&SendDate={SendDate}\&Voice={Voice}\&Speed={Speed}\&CallbackUrl={CallbackUrl}\&RequestId={RequestId})[  ](http://voiceapi.esms.vn/MainService.svc/json/MakeCallTemplate\_V2?ApiKey={ApiKey}\&SecretKey={SecretKey}\&TemplateId={TemplateId}\&Phone={Phone}\&VariableListStr={VariableListStr}\&SendDate={SendDate}\&Voice={Voice}\&Speed={Speed}\&CallbackUrl={CallbackUrl}\&RequestId={RequestId})\
  Method: GET

```
curl --location -g --request GET 'http://voiceapi.esms.vn/MainService.svc/json/MakeCallTemplate_V2?ApiKey={ApiKey}&SecretKey={SecretKey}&TemplateId={TemplateId}&Phone={Phone}&VariableListStr={VariableListStr}&SendDate={SendDate}&Voice={Voice}&Speed={Speed}&CallbackUrl={CallbackUrl}&RequestId={RequestId}'
```

* Thông tin request

| Biến            | Định nghĩa                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ApiKey          | ApiKey của tài khoản                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| SecretKey       | Secretkey của tài khoản                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| TemplateId      | Id kịch bản cuộc gọi đăng ký trên trang account.esms.vn                                                                                                                                                                                                                                                                                                                                                                                                         |
| Phone           | Số điện thoại nhận tin                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| VariableListStr | Chuỗi biến chứa danh sách giá trị các biến của mẫu cuộc gọi, cách nhau bởi dấu “\|\|”, thứ tự các biến từ trái sang phải. Ví dụ: Trung\|\|20000 (Giá trị biến 1: Trung, Giá trị biến 2: 20000)                                                                                                                                                                                                                                                                  |
| SendDate        | Đặt lịch gửi tin (định dạng: yyyy/MM/dd hh:mm:ss) Ví dụ: 2017/12/12 14:00:00                                                                                                                                                                                                                                                                                                                                                                                    |
| Voice           | <p></p><p>Giọng đọc biến, có các giá trị sau đây:</p><ul><li>male: giọng nam miền Bắc</li><li>female: giọng nữ miền Bắc</li><li>hatieumai: giọng nữ miền Nam</li><li>ngoclam: giọng nữ Huế</li></ul>                                                                                                                                                                                                                                                            |
| Speed           | <p></p><p>Tốc độ đọc biến, có các giá trị sau đây:</p><ul><li>-3: rất chậm</li><li>-2: khá chậm</li><li>-1: chậm</li><li>0: bình thường</li><li>1: nhanh</li><li>2: khá nhanh</li><li>3: rất nhanh</li></ul>                                                                                                                                                                                                                                                    |
| CallbackUrl     | <p></p><p>Url nhận callback kết quả cuộc gọi (mẫu: http://xxxx.com?ReferenceId=&#x26;CallDuration=&#x26;CallSt atus=&#x26;Ivr=&#x26;Price=&#x26;SentResult&#x26;CID= )</p><ul><li>CallDuration: độ dài cuộc gọi</li><li>CallStatus: kết quả cuộc gọi (ANSWERED, NO ANSWER)</li><li>Ivr: phím bấm của khách hàng</li><li>Price: giá cuộc gọi</li><li>SentResult: Kết quả gửi tin qua nhà mạng (0: thất bại, 1: thành công)</li><li>CID: đầu số gửi tin</li></ul> |
| RequestId       | ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. Ví dụ: requestid=123456                                                                                                                                                                                                                                                                                                                                     |

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
