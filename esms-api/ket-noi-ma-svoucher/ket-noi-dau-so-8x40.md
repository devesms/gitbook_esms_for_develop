# Kết nối đầu số 8X40

_**1: Thông tin kết nối:**_\
_****_\
_****_**Bước 1:** Khi khách hàng gửi tin nhắn lên đầu số 8x41, phía eSMS sẽ gọi 1 request như bên dưới sang đối tác **http://domain.abc/receive\_mo?cpid=CP\_XXXX\&sign=XXXXX=\&smsid=XX\&sender=XXXX\&serviceNumber=XXXX \&keyword=XXXX\&content=XXXX\&receiverTime=20140715110554**\
****Trong đó: http://domain.abc/receive\_mo là link mà đối tác cung cấp cho eSMS để nhận các request

| Tham số       | Kiểu   |                                                                                                                                                             |
| ------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| cpid          | string | Là cpid do eSMS.vn cấp cho khách hàng                                                                                                                       |
| sign          | string | chữ ký số, tạo bởi chuỗi bí mật của ứng dụng tương ứng cpid                                                                                                 |
| smsid         | string | là một chuỗi do eSMS.vn cung cấp. Đây là số duy nhất tương ứng với một tin nhắn. Số này dùng để kiểm tra các trường hợp trùng và đối chiếu đối soát về sau. |
| sender        | string | số điện thoại khách hàng, định dạng quốc tế (có 84)                                                                                                         |
| serviceNumber | string | đầu số dịch vụ (8041,8141…)                                                                                                                                 |
| keyword       | string | từ đầu tiên trong cú pháp MO                                                                                                                                |
| content       | string | nội dung mà khách hàng nhắn                                                                                                                                 |
| receiverTime  | string | Thời gian nhận được MO, có format yyyyMMddhhmmss                                                                                                            |

**Bước 2:** Đối tác xử lý request này và trả về thông tin có dạng sau:

```
<ClientResponse>
   <Message>Nội dung tin nhắn trả về</Message>
   <Smsid>ID của tin nhắn gửi lên</Smdid>
   <Receiver>Số điện thoại người nhận</Receiver>
</ClientResponse>
```

_**2. Thông tin kết nối:**_\
_****_\
_****_Sign: được băm từ 5 tham số: Cpid, smsid, content, receiveTime và PrivateKey \
hashValue(value1, value2,…) = MD5(value1 + value2 + … + private\_key) \
\
Ví dụ: đối tác A sử dụng dịch vụ X có khóa bí mật là 17417a0d20114d36a902e49cad0e97f3 thì giá trị băm được tính như sau: \
hash("abcdef", "1234", "xyz") = MD5("abcdef1234xyz17417a0d20114d36a902e49cad0e97f3");\
\
Format thời gian: giá trị thời gian được truyền dưới định dạng sau: yyyyMMddhhmmss. Ví dụ ngày 28 tháng 2 năm 2013, lúc 13 giờ 01 phút 01 giây: 20130228130101\
\
**Mã lệnh mẫu**\
&#x20;     ****      Trong việc giao tiếp giữa client và server, có một giá trị băm gửi gửi kèm để đảm bảo toàn bộ các thông tin là chính xác. Đoạn lệnh mẫu tính giá trị băm xin tham khảo dưới đây.

* **.NET**

```
string GetHash(string s)
{
UTF8Encoding ue = new UTF8Encoding();
byte[] v = ue.GetBytes(s);
byte[] hashValue = new MD5CryptoServiceProvider().ComputeHash(v);
return Convert.ToBase64String(hashValue);
}
```

* **Java**

```
String getHash(String sSrc)
throws Exception {
Charset utf8Charset = Charset.forName("UTF-8");
Tài liệu hướng dẫn kết nối
4
byte[] textBytes = sSrc.getBytes(utf8Charset);
MessageDigest m = MessageDigest.getInstance("MD5");
byte[] digest = m.digest(textBytes);
String sEncodedText = B64.b64encode(digest);
return sEncodedText;
} 
```

* **PHP**

```
<?php
$str = 'qwertyuiop';
$hash = base64_encode(md5($str, true));
?>
```
