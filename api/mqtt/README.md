# MQTT

## 变量说明

* `TENANT`：租户/企业唯一标识
* `DEVICE`：设备唯一标识

## 接口认证

接口认证采用用户名/密码的形式，调用接口前请先申请。

### 使用流程

1. 注册租户
2. 创建 / 获取MQTT-broker地址、用户名、密码
3. 连接MQTT，订阅相关Topic

## 接口清单

### 设备事件

<table data-view="cards"><thead><tr><th>分类</th><th>接口名称</th><th>接口</th></tr></thead><tbody><tr><td><a href="broken-reference">设备事件</a></td><td><a href="broken-reference">定时信息上报</a></td><td><mark style="background-color:green;">SUB</mark> <code>v1/user/$(TENANT}/$(DEVICE}/</code><mark style="color:red;"><code>report/regular</code></mark><code>/post</code></td></tr></tbody></table>
