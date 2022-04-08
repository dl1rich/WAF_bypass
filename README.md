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
  
HTML entities are usually not reflected back and can be beaten seamlessly replacing hex encodes to encode & and; signs. Put all these pieces together and you’ll be able to fully bypass the Sucuri XSS filter. 

If that sounds too daunting and complex for you, there is one more way to bypass the Sucuri XSS filter. You need to find a way to bypass its attributes. On a basic level, it’s possible to break every blacklist filter. Few could be easy while few could be tough to break out of. But, breaking down is possible. 

The only thing one needs is a deeper understanding of Unicode and ASCII sort of character sets and distinctive separators. Those who don’t know about separators, they are special characters analyzed as space characters. 

To bypass a filter attribute, one can make it happen by finding the non-space valid separator in the given filter attribute. For instance, the [on\w+\s*] RegExp is active for filtering the on* attributes and it can be bypassed by locating the non-space valid separator. 

The most suitable approach for this action is to fuzz the valid separators for every browser. 

![image](https://user-images.githubusercontent.com/94630001/162407183-fb7e290d-2ade-4053-a519-1e4781d631f7.png)


3. Space can be bypassed with 
```
:
<a:href=hello>click me</a>

or

/
<a/href=hello>click me</a>

```

## Help 

https://github.com/0xInfection/Awesome-WAF  
https://github.com/vincentcox/bypass-firewalls-by-DNS-history  


