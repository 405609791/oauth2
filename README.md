# oauth2
oauth2协议：允许用户用第三方用户访问资源，（第三方登录，用微信登录其他软件）
通过这个网络标准，一个第三方应用(客户端)可以获取资源所有者(用户)
在服务提供商(为用户提供服务的服务商)保存的特定资源。在这个标准中，
第三方应用不能直接登录服务提供商，资源所有者只负责做是否授权以及授权哪些资源的决策，
根据决策结果，第三方应用可以获得有时效、有授权范围的令牌，并通过令牌从服务供应商那里获得特定的资源。

Oaut2 介绍：https://www.jianshu.com/p/57c16539feb1


postman 测试
post 请求：http://localhost:8080/oauth/token
username:codefarmer
password:123
grant_type:password
client_id:password
scope:all
client_secret:123
请求结果
{
    "access_token": "c0775177-f485-4061-9ece-f260d6f0450e",
    "token_type": "bearer",
    "refresh_token": "f389a89e-5a67-405f-8996-1599436f6852",
    "expires_in": 692,
    "scope": "all"
}


后台请求：
http://localhost:8080/hello?access_token=c0775177-f485-4061-9ece-f260d6f0450e

刷新
post 请求：http://localhost:8080/oauth/token
grant_type:refresh_token
refresh_token:上一个请求里的refresh_token
client_id:password
client_secret:123

