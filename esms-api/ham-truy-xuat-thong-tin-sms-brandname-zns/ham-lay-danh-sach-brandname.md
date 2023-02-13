# Hàm lấy danh sách Brandname

* HTTP request\
  URL: [http://rest.esms.vn/MainService.svc/json/GetListBrandname/\{{ApiKey\}}/\{{SecretKey\}}](http://rest.esms.vn/MainService.svc/json/GetListBrandname/%7B%7BApiKey%7D%7D/%7B%7BSecretKey%7D%7D)\
  Method: GET

```
curl --location -g --request GET 'http://rest.esms.vn/MainService.svc/json/GetListBrandname/{{ApiKey}}/{{SecretKey}}' \
--header 'Cookie: ASP.NET_SessionId=owevtxyrtqm5gvj5zwjfeb2z'
```

* Thông tin request

|                                              |                         |
| -------------------------------------------- | ----------------------- |
| ApiKey <mark style="color:red;">\*</mark>    | ApiKey của tài khoản    |
| SecretKey <mark style="color:red;">\*</mark> | Secretkey của tài khoản |

* Mẫu kết quả trả về

```
{
    "CodeResponse": "100",
    "ListBrandName": [
        {
            "Brandname": "Baotrixemay",
            "Type": 2
        },
        {
            "Brandname": "QC_ONLINE",
            "Type": 1
        },
        {
            "Brandname": "BAT DONG SAN GIA TOT",
            "Type": 23
        }
    ]
}
```

* Thông tin kết quả trả về

| Biến      | Định nghĩa                                                                                  |
| --------- | ------------------------------------------------------------------------------------------- |
| Brandname | Tên brandname                                                                               |
| Type      | <p>Loại brandname<br>1: brandname quảng cáo<br>2: brandname CSKH<br>23: brandname Viber</p> |
|           |                                                                                             |
