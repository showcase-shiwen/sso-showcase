# 标准Oauth2 授权协议模式

## authorization_code 授权码模式
+ 浏览器打开
```
请求地址
http://localhost:9401/oauth/authorize?response_type=code&client_id=admin&redirect_uri=https://www.baidu.com&scope=all
```
+ 输入用户明密码
![img_4.png](../doc/image/img_4.png)
+ 确认授权
![img.png](../doc/image/img.png)
  
+ 获取授权码
![img_1.png](../doc/image/img_1.png)

+ 授权码换取access_token
```
请求地址
http://localhost:9401/oauth/token?grant_type=authorization_code&code=opIM7B&redirect_uri=https://www.baidu.com&scope=all

请求头
Authoriztion: basic Base64(clinet:secret)

```
![img_2.png](../doc/image/img_2.png)


## password 密码授权模式
+ 用户密码直接获取access_token
```
请求地址
http://localhost:9401/oauth/token?grant_type=password&redirect_uri=https://www.baidu.com&scope=all

请求头
Authoriztion: basic Base64(clinet:secret)

```  
![img_3.png](../doc/image/img_3.png)
