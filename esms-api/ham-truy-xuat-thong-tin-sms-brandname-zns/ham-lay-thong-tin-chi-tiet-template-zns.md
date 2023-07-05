# Hàm lấy thông tin chi tiết template ZNS

* HTTP request \
  URL: <mark style="color:blue;">http://rest.esms.vn/MainService.svc/json/GetZnsTemplateInfo?TemplateId=\{{TemplateId\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&OAId=\{{OAId\}}</mark>\
  Method: GET

```
curl --location 'http://rest.esms.vn/MainService.svc/json/GetZnsTemplateInfo?TemplateId={{TemplateId}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&OAId={{OAId}}' \
```

* Thông tin request

| Biến       | Định nghĩa                                                                                                                                                                                                                        |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| TemplateId | Template của Zalo OA mà khách hàng đăng kí với eSMS.                                                                                                                                                                              |
| ApiKey     | ApiKey của tài khoản                                                                                                                                                                                                              |
| SecretKey  | SecretKey của tài khoản                                                                                                                                                                                                           |
| OAId       | <p>Zalo OA ID, là ID của trang Zalo Offical Account của doanh nghiệp. <br>Doanh nghiệp cần đăng nhập vào trang quản trị của Zalo OA để lấy phần Zalo OA ID này.<br><strong>Chú ý: sẽ phải đăng ký trước khi sử dụng.</strong></p> |

* Mẫu kết quả trả về

```
{
    "Data": {
        "ApplyTemplateQuota": false,
        "ListParams": [
            {
                "AcceptNull": false,
                "MaxLength": 10,
                "MinLength": 0,
                "Name": "otp",
                "Require": true,
                "Type": "STRING"
            }
        ],
        "PreviewUrl": "https://zns.oa.zalo.me/znspreview/SZk01CLsjXTYpn_B4agO0g==",
        "Status": "ENABLE",
        "TemplateDailyQuota": null,
        "TemplateId": 205644,
        "TemplateName": "Xác nhận đăng ký dịch vụ",
        "TemplateQuality": "UNDEFINED",
        "TemplateRemainingQuota": null,
        "TemplateTag": "OTP",
        "Timeout": 15000
    },
    "Error": 0,
    "Message": "Success"
}
```

* Thông tin kết quả trả về&#x20;

<table><thead><tr><th width="253">Biến</th><th>Định nghĩa</th></tr></thead><tbody><tr><td>ApplyTemplateQuota</td><td><p>Trường thông tin cho biết template có áp dụng hạn mức Daily Quota hay không.</p><p>Chú thích: Hạn mức Daily Quota chỉ áp dụng cho một số template đặc biệt mang tính thử nghiệm và đã trực tiếp được đăng ký với Zalo. Các template bình thường sẽ không bị ảnh hưởng bởi giới hạn này.</p></td></tr><tr><td>PreviewUrl</td><td>Đường dẫn đến bản xem trước của template.</td></tr><tr><td>Status</td><td>Trạng thái template.</td></tr><tr><td>TemplateDailyQuota</td><td><p>Số tin ZNS thuộc template này OA được gửi trong ngày.</p><p>Lưu ý: Trường thông tin này chỉ được trả về khi applyTemplateQuota = true.</p></td></tr><tr><td>TemplateId</td><td>ID của template.</td></tr><tr><td>TemplateName</td><td>Tên của template.</td></tr><tr><td>TemplateQuality</td><td><p></p><p>Chất lượng gửi tin hiện tại của template.</p><p>Các giá trị trả về:</p><ul><li><strong>HIGH</strong></li><li><strong>MEDIUM</strong></li><li><strong>LOW</strong></li><li><strong>UNDEFINED</strong></li></ul></td></tr><tr><td>TemplateRemainingQuota</td><td><p>Số tin ZNS thuộc template này OA được gửi trong ngày còn lại.</p><p>Lưu ý: Trường thông tin này chỉ được trả về khi applyTemplateQuota = true.</p></td></tr><tr><td>TemplateTag</td><td><p></p><p>Loại nội dung của template. Các giá trị trả về:</p><ul><li><strong>OTP</strong> – OTP</li><li><strong>IN_TRANSACTION</strong> – Xác nhận/Cập nhật giao dịch</li><li><strong>POST_TRANSACTION</strong> – Hỗ trợ dịch vụ liên quan sau giao dịch</li><li><strong>ACCOUNT_UPDATE</strong> – Cập nhật thông tin tài khoản</li><li><strong>GENERAL_UPDATE</strong> – Thay đổi thông tin dịch vụ</li><li><strong>FOLLOW_UP</strong> – Thông báo ưu đãi đến khách hàng cũ</li></ul></td></tr><tr><td>Timeout</td><td>Thời gian timeout của template.</td></tr><tr><td>AcceptNull</td><td>Thông tin cho biết thuộc tính có thể nhận giá trị rỗng hay không.</td></tr><tr><td>MaxLength</td><td>Số kí tự tối đa được truyền vào thuộc tính.</td></tr><tr><td>MinLength</td><td>Số kí tự tối thiểu được truyền vào thuộc tính.</td></tr><tr><td>Name</td><td>Tên thuộc tính.</td></tr><tr><td>Require</td><td>Tính bắt buộc của thuộc tính.</td></tr><tr><td>Type</td><td>Định dạng validate của thuộc tính.</td></tr></tbody></table>

{% hint style="info" %}
* Hiện tại số lần request là 1s cho 1 lần request
* Số ReferenceId tối đa cho 1 lần request là 100
* Thời gian request là vào lúc 01:00 đến 02:00 AM mỗi ngày
{% endhint %}

