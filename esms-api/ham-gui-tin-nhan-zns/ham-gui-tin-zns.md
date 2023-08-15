# Hàm gửi tin ZNS

Hàm cho phép bạn gửi tin nhắn đến 1 hoặc nhiều số điện thoại đã đăng kí Zalo. Để có thể gửi được tin ZNS bạn cần tiến hành:\
\- Đăng ký và xác thực Zalo Offical Account (Zalo OA)\
\- Đăng ký template tin nhắn\
Để hoàn thành các việc trên vui lòng liên hệ nhân viên kinh doanh hỗ trợ của bạn hoặc Hotline 0901888484\
Ví dụ 1 mẫu tin ZNS\


<figure><img src="../../.gitbook/assets/Untitled.png" alt=""><figcaption><p>Một tin ZNS mẫu</p></figcaption></figure>

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/SendZaloMessage\_V4\_post\_json/](http://rest.esms.vn/MainService.svc/json/SendZaloMessage\_V4\_post\_json/)\
  Method: POST\
  Content Type: application/json

{% code overflow="wrap" %}
```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendZaloMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=hv0fnv0mv4i0qnmx2zrxetvf' \
--data-raw '{
"ApiKey":"{ApiKey}",
"SecretKey":"{SecretKey}",
"Phone":"{Phone}",
"Params":["{value1}","{value2}","{value3}"],
"TempID":"{TempID}",
"OAID":"{OAID}",
"SendDate":"{SendDate}",
"Sandbox":"0",
"RequestId": "{RequestId}",
"campaignid": "{campaignid}",
"CallbackUrl":"{CallbackUrl}"
}'

```
{% endcode %}

* Thông tin request

<table><thead><tr><th width="236">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApiKey <mark style="color:red;">*</mark></td><td>ApiKey của tài khoản</td></tr><tr><td>SecretKey <mark style="color:red;">*</mark></td><td>Secretkey của tài khoản</td></tr><tr><td>Phone <mark style="color:red;">*</mark></td><td>Số điện thoại nhận tin</td></tr><tr><td>Params <mark style="color:red;">*</mark></td><td><p></p><p>Giá trị cần truyền cho các biến trong Template *Lưu ý:</p><ol><li>Các tham số truyền vào phải đúng thứ tự như template bạn đăng ký</li><li>Nếu tham số trùng nhau chỉ cần truyền vào một tham số</li></ol></td></tr><tr><td>TempID <mark style="color:red;">*</mark></td><td>Template của Zalo OA mà khách hàng đăng kí với eSMS</td></tr><tr><td>OAID <mark style="color:red;">*</mark></td><td>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này. <br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></td></tr><tr><td>SendDate</td><td>Thời gian hẹn gửi của tin. <br>Không truyền khi tin muốn tin nhắn gửi đi liền.<br>Định dạng: yyyy-mm-dd hh:MM:ss</td></tr><tr><td>Sandbox</td><td>0: Gửi tin đi thật<br>1: Tin thử nghiệm. không lưu tin và không đi tin. Chỉ để kiểm tra kết nối.</td></tr><tr><td>RequestId</td><td>ID Tin nhắn của đối tác, dùng để kiểm tra ID này đã được hệ thống esms tiếp nhận trước đó hay chưa. <br>Ví dụ: RequestId=123456</td></tr><tr><td>campaignid</td><td>Tên chiến dịch gửi tin, tối đa 254 ký tự</td></tr><tr><td>CallbackUrl</td><td>eSMS sẽ trả về kết quả của tin nhắn.</td></tr></tbody></table>

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
