# Hàm gửi tin SMS CSKH



**\* **<mark style="color:red;">**Lấy code mẫu các ngôn ngữ trên Postman:**</mark> [**linkpostman**](https://esms.vn/)

**\* **<mark style="color:red;">**Hướng dẫn lấy code mẫu:**</mark> [**video**](https://esms.vn/)

## HTTP request

<mark style="color:green;">`POST`</mark> `/`MainService.svc/json/SendMultipleMessage\_V4\_post\_json/

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



Cấu trúc body của request

| Tham số     | Kiểu dữ liệu | Tính bắt buộc  | Mô tả                                                                                                                     |
| ----------- | ------------ | -------------- | ------------------------------------------------------------------------------------------------------------------------- |
| ApiKey      | string       | Bắt buộc       | ApiKey eSMS cung cấp                                                                                                      |
| Content     | string       | Bắt buộc       | Nội dung tin nhắn                                                                                                         |
| `Phone`     | number       | Bắt buộc       | Số điện thoại nhận tin nhắn                                                                                               |
| SecretKey   | string       | Bắt buộc       | SecretKey eSMS cung cấp                                                                                                   |
| Brandname   | string       | Bắt buộc       | Tên Brandname (tên công ty hay tổ chức khi gửi tin sẽ hiển thị trên tin nhắn). **Chú ý: Phải đăng ký trước khi sử dụng.** |
| SmsType     | string       | Bắt buộc       | Loại tin nhắn ID 2 là CSKH                                                                                                |
| IsUnicode   | string       | Không bắt buộc | <p>Gửi nội dung có dấu 1: Có dấu </p><p>0: Không dấu</p>                                                                  |
| CallbackUrl | string       | Không bắt buộc | URL nhận kết quả gửi tin                                                                                                  |
| RequestId   | string       | Không bắt buộc | ID đối tác truyền sang để chặn trùng và đối soát khi cần                                                                  |
| SendDate    | string       | Không bắt buộc | <p>Thời gian hẹn giờ gửi tin.<br><strong>Đề xuất: Không nên truyền tham số này để tin được đi nhanh nhất</strong></p>     |
| campaignid  | string       | Không bắt buộc | Tên chiến dịch                                                                                                            |
|             |              |                |                                                                                                                           |

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
{% endtab %}

{% tab title="99" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}



Cấu trúc body của response:

| Thuộc tính   | Kiểu dữ liệu | Mô tả                             |
| ------------ | ------------ | --------------------------------- |
| CodeResult   | String       | Mã trả về                         |
| SMSID        | String       | ID tin nhắn do esms trả về        |
| ErrorMessage | String       | Thông tin lỗi trả về (nếu có lỗi) |

_**\*Chi tiết mã lỗi xem ở trang "**_[_**Mã Lỗi**_](../ham-gui-tin-nhan-zns/ham-gui-tin-nhan-zns-moi-khach-hang-mot-noi-dung.md)_**"**_