# 标准Oauth2 授权协议模式之jwt 实现

## authorization_code 授权码模式
+ 浏览器打开
```
请求地址
http://localhost:9401/oauth/authorize?response_type=code&client_id=baidu&redirect_uri=https://www.baidu.com&scope=all
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
+ 示例

![img_2.png](../doc/image/img_2.png)

## implicit 简化模式
```
请求地址 浏览器打开
http://localhost:9401/oauth/authorize?response_type=token&client_id=baidu&scope=all

```
+ 输入用户密码

![img.png](../doc/image2/img.png)
+ 跳转回app回调页面

![img_1.png](../doc/image2/img_1.png)


## password 密码授权模式
+ 用户密码直接获取access_token
```
请求地址
http://localhost:9401/oauth/token?grant_type=password&redirect_uri=https://www.baidu.com&scope=all

请求头
Authoriztion: basic Base64(clinet:secret)

```  
+ 获取token

![img_2.png](../doc/image2/img_2.png)

+ 刷新token
```

请求地址

http://localhost:9401/oauth/token?grant_type=refresh_token&refresh_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX25hbWUiOiJzaG93Y2FzZSIsInNjb3BlIjpbImFsbCJdLCJhdGkiOiJjODgzYTRlZS1iMTQ4LTQzZGYtYjcyYi1lZTRiMTU0YmQ1NWIiLCJleHAiOjE2NzA1NjkwNDIsImF1dGhvcml0aWVzIjpbImFkbWluIl0sImp0aSI6IjVkNDNhNzFiLWYwNGMtNDEyZS05MjZlLWE0M2E2MjQ3YTE0MCIsImNsaWVudF9pZCI6ImJhaWR1IiwiZW5oYW5jZSI6ImVuaGFuY2UgaW5mbyJ9.2ODGa0Yz3YfyEfeud9PUfOmBUzecLH1U94s1nm6LYOA&redirect_uri=https://www.baidu.com&scope=all

请求头
Authoriztion: bearer Base64(clinet:secret)

```
+ 示例

![img_3.png](../doc/image2/img_3.png)

##  client_credentials 客户端模式
```
请求地址
http://localhost:9401/oauth/token?grant_type=client_credentials&username=showcase&password=123456
```
+ 示例

![img_4.png](../doc/image2/img_4.png)
