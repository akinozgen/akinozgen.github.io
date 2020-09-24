---
layout: post
title: Centos'ta SMTP Connection Refused Hatası Çözümü
---

### Hata
`Connection could not be established with host smtp.yandex.com :stream_socket_client(): unable to connect to ssl://smtp.yandex.com:465 (Permission denied)`

### Sebep
SELinux engellemesi. Sadece mail değil her türlü cURL bağlantınında çıkıyor.

### Çözüm
```bash
# setsebool -P httpd_can_network_connect on
```
