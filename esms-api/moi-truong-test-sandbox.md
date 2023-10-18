# Môi trường test ( Sandbox)

* Để gửi tin ở môi trường thử nghiệm, eSMS đã cung cấp cho khách hàng môi trường test tin. Khách hàng truyền thêm trường Sandbox vào body gửi. Tin nhắn sẽ không được lưu ở hệ thống eSMS, không tính phí và không về máy khách hàng.
* Truyền Sandbox = 1 cho các api có hỗ trợ môi trường Sandbox.
* Body mẫu cho gửi thử nghiệm tin nhắn Chăm sóc khách hàng:

{% code overflow="wrap" %}
```
curl --location -g --request GET 'curl --location --request GET '\''http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_get?Sandbox=1&SmsType=2&ApiKey={ApiKey}&SecretKey={SecretKey}&Brandname=Baotrixemay&Phone=0901888484&Content=Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!'\'' \
--header '\''Cookie: ASP.NET_SessionId=asfgp2dj1kt4kbg1yzuo35ky'\''' \
--header 'Cookie: ASP.NET_SessionId=asfgp2dj1kt4kbg1yzuo35ky'
```
{% endcode %}

* Body mẫu cho gửi thử nghiệm tin nhắn ZNS:

{% code overflow="wrap" %}
```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendZaloMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--header 'Cookie: ASP.NET_SessionId=asfgp2dj1kt4kbg1yzuo35ky' \
--data-raw '{
"ApiKey":"{ApiKey}",
"SecretKey":"{SecretKey}",
"Phone":"0901888484",
"Params":["686868"],
"TempID":"205644",
"OAID":"4097311281936189049",
"Sandbox":1,
"CallbackUrl":"https://enduxb9xt2ektmj.m.pipedream.net"
}'
```
{% endcode %}

