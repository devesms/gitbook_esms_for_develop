# Callback Url

* Khi có trạng thái thực của tin nhắn. eSMS sẽ callback trạng thái về hook của khách hàng theo dạng HTTP GET.&#x20;
* Callback sẽ được retry 5 lần nếu như url của khách hàng trả timeout. Hết 5 lần mà url của khách hàng vẫn timeout thì sẽ ngừng callback.\


## Callback mẫu

### Callback mẫu cho loại tin CSKH:

{% code overflow="wrap" %}
```
curl --location --request GET 'https://yourportal.sms/receivecallback/?SMSID=dc712784-9c5f-4c69-b9a8-ea69d56adc9a87&SendFailed=2&SendStatus=5&SendSuccess=0&TotalPrice=0.0000&TotalReceiver=2&TotalSent=2&RequestId=&TypeId=2&telcoid=1&phonenumber=0397840416&switchsmsid='
```
{% endcode %}

### Callback mẫu cho loại tin Quảng cáo:

{% code overflow="wrap" %}
```
curl --location --request GET 'https://yourportal.sms/receivecallback/?SMSID=82b0bb8aed914a0aab8deba567c9b8c2&SendFailed=0&SendStatus=5&SendSuccess=0&TotalPrice=696987.0000&TotalReceiver=169&TotalSent=169&RequestId=&TypeId=1'
```
{% endcode %}

### Callback mẫu cho lại tin ZNS:

{% code overflow="wrap" %}
```
curl --location -g --request GET 'https://yourportal.sms/receivecallback/?SMSID=f66545d2-c7e2-4603-984e-d2238c363c8292&SendFailed=1&SendStatus=5&SendSuccess=0&TotalPrice=0.0000&TotalReceiver=1&TotalSent=0&RequestId=&TypeId=25&telcoid=2&phonenumber=0901888484&partnerids=&error_info="{\"error\":-114,\"message\":\"User is inactive, or reject the message, or using an outdated Zalo version, or other internal errors\"}"&oaid=1397492183140006179&tempid=2056446'
```
{% endcode %}

## Thông tin kết quả trả về của callback

| Biến          | Định nghĩa                                                                                                                                  |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| SMSID         | Mã tin nhắn                                                                                                                                 |
| SendFailed    | Số lượng tin nhắn thất bại                                                                                                                  |
| SendStatus    | <p>Trạng thái tin nhắn<br>1: Chờ duyệt<br>4: Từ chối<br>5: Đã gửi xong</p>                                                                  |
| SendSuccess   | Số lượng tin thành công                                                                                                                     |
| Totalprice    | Tổng tiền đơn                                                                                                                               |
| TotalReceiver | Tổng số người nhận                                                                                                                          |
| TotalSent     | Tổng số lượng tin được gửi                                                                                                                  |
| RequestId     | Mã request của khách hàng                                                                                                                   |
| TypeId        | <p>Loại tin nhắn<br>1: tin quảng cáo<br>2: tin chăm sóc khách hàng<br>23: tin viber<br>24: tin zalo ưu tiên<br>25: tin zalo bình thường</p> |
| telcoid       | <p>Nhà mạng<br>1: Viettel, 2: Mobi, 3: Vina, 4: Vietnammobile, 5: Gtel, 6: Itel, 7: Reddi</p>                                               |
| phonenumber   | Số điện thoại người nhận                                                                                                                    |
| partnerids    | Mã giao dịch của Zalo **(chỉ có đối với tin zalo)**                                                                                         |
| error\_info   | Mã lỗi của tin nhắn **(chỉ có đối với tin zalo)**                                                                                           |
| oaid          | ID của Oa gửi tin **(chỉ có đối với tin zalo)**                                                                                             |
| tempid        | Tempid gửi tin **(chỉ có đối với tin zalo)**                                                                                                |

