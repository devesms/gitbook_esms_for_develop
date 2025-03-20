# Gửi tin nhắn SMS OTP/CSKH



## HTTP request

<mark style="color:green;">**`POST`**</mark> **http://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post\_json/**

* **Content Type:** application/json
* **Response Type:** application/json

```
curl --location --request POST 'http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--data-raw '{
   "ApiKey": "{{ApiKey}}",
   "Content": "{{Content}}",
   "Phone": "{{Phone}}",
   "SecretKey": "{{SecretKey}}",
   "Brandname": "{{Brandname}}",
   "SmsType": "2",
   "IsUnicode": 0,
   "Sandbox": 0,
   "campaignid": "{{campaignid}}",
   "RequestId": "{{RequestId}}",
   "CallbackUrl": "{{CallbackUrl}}"
}'
```



**Cấu trúc body của request**

| Tham số     | Kiểu dữ liệu | Tính bắt buộc  | Mô tả                                                                                                                                                              |
| ----------- | ------------ | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ApiKey      | string       | Bắt buộc       | ApiKey eSMS cung cấp                                                                                                                                               |
| Content     | string       | Bắt buộc       | Nội dung tin nhắn                                                                                                                                                  |
| Phone       | number       | Bắt buộc       | Số điện thoại nhận tin nhắn                                                                                                                                        |
| SecretKey   | string       | Bắt buộc       | SecretKey eSMS cung cấp                                                                                                                                            |
| Brandname   | string       | Bắt buộc       | Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn). **Chú ý: Phải đăng ký trước khi sử dụng.**                                          |
| SmsType     | string       | Bắt buộc       | Loại tin nhắn ID 2 là CSKH                                                                                                                                         |
| IsUnicode   | string       | Không bắt buộc | <p>Gửi nội dung có dấu<br>1: Có dấu </p><p>0: Không dấu</p>                                                                                                        |
| Sandbox     |              |                | <p>1: Tin gửi ở môi trường test, dùng để kiểm tra kết nối và các thông số tích hợp, không về tin nhắn <br>0: Tin gửi ở môi trường bình thường, có về tin nhắn.</p> |
| RequestId   | string       | Không bắt buộc | ID đối tác truyền sang để chặn trùng và đối soát khi cần                                                                                                           |
| SendDate    | string       | Không bắt buộc | <p>Thời gian hẹn giờ gửi tin.<br><strong>Đề xuất: Không nên truyền tham số này để tin được đi nhanh nhất</strong></p>                                              |
| campaignid  | string       | Không bắt buộc | Tên chiến dịch                                                                                                                                                     |
| CallbackUrl | string       | Không bắt buộc | URL nhận kết quả gửi tin                                                                                                                                           |
|             |              |                |                                                                                                                                                                    |

**Response**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "d533459ee42b2b9525ba9eabf6a8156"
}
```

**\*Request hợp lệ**
{% endtab %}

{% tab title="104" %}
```json
{
    "CodeResult": "104",
    "CountRegenerate": 0,
    "ErrorMessage": "Brand name code is not exist"
}
```

**\*Brandname truyền chưa đúng hoặc chưa được active**
{% endtab %}

{% tab title="101" %}
```json
{
    "CodeResult": "101",
    "CountRegenerate": 0,
    "ErrorMessage": "Authorize Failed"
}
```

**\*Sai thông tin ApiKey hoặc SecretKey**
{% endtab %}

{% tab title="99" %}
```json
{
  "error": "Invalid request"
}
```

**\*Kiểm tra lại thông tin kết nối hoặc liên hệ bộ phận chăm sóc khách hàng để được hỗ trợ khi gặp lỗi này.**
{% endtab %}
{% endtabs %}



**Cấu trúc body của response**

| Thuộc tính   | Kiểu dữ liệu | Mô tả                             |
| ------------ | ------------ | --------------------------------- |
| CodeResult   | String       | Mã trả về                         |
| SMSID        | String       | ID tin nhắn do esms trả về        |
| ErrorMessage | String       | Thông tin lỗi trả về (nếu có lỗi) |

_**\***<mark style="color:red;">**Chi tiết mã lỗi xem ở trang:**</mark>_ [_**Mã Lỗi**_](../ham-gui-tin-nhan-zns/ham-gui-tin-nhan-zns-moi-khach-hang-mot-noi-dung.md)

**\*&#x20;**_<mark style="color:red;">**Lấy code mẫu các ngôn ngữ trên Postman:**</mark>_ [**link code mẫu**](https://postman.esms.vn/#b62c8cec-0728-4402-bb6a-4ee272fe73fc)

**\*&#x20;**_<mark style="color:red;">**Hướng dẫn lấy code mẫu:**</mark>_ [**video**](https://esms.vn/)
