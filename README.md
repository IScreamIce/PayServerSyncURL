# PayServerSyncURL

完成支付后，阿里微信将异步告知指定外网服务器，捕获阿里微信等访问者的请求参数


当支付完成后，支付提供商会向我们指定的外网服务器发送信息，表示有人成功支付了。这个需要是外网可访问服务器。

我叫这个为回调地址。还有一个是站内的回跳地址。在支付成功后，站内可指定跳哪里，测试时就可以是本地的IP+服务而回调地址，是支付提供商向我们发送，需要外网IP

回跳我们指定跳服务(可站内)，回调支付成功调用我们指定的URL服务告知(外网可访问)



这个工程，不仅是拦截支付宝，还可以拦截微信等其他第三方任何发起的请求，拦截请求者的所有请求参数并存储在servletcontext中。


本工程有以下注意：
1：访问notify_url.jsp，将拦截所有参数并存储在全局唯一对象中，存储格式json。作用、存储
2：访问clear，将情况所有拦截并存储在全局对象中的对象，作用、清空存储
