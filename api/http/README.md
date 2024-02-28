# HTTP

## 接口认证

接口认证采用API Key的形式，调用接口前请先申请API Key。

### 使用流程

1. 注册租户
2. 创建API-Key / 获取API-Key
3. 调用接口时将API-Key放在请求头部`X-API-Key`，无特殊说明接口前缀均为`https://www.einfra.cn/wad/ems/v1/api`，详见示例（假设API-Key为`YH3kPJ5rKVYH3kPJ5rKVYH3kPJ5rKV`）

{% tabs %}
{% tab title="cURL" %}
```sh
curl --location --request GET 'https://www.einfra.cn/wad/ems/v1/api/test-apikey' \
--header 'X-API-Key: YH3kPJ5rKVYH3kPJ5rKVYH3kPJ5rKV'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://www.einfra.cn/wad/ems/v1/api/test-apikey"

headers = {
  'X-API-Key': 'YH3kPJ5rKVYH3kPJ5rKVYH3kPJ5rKV',
}

response = requests.request("GET", url, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://www.einfra.cn/wad/ems/v1/api/test-apikey")
  .method("GET", body)
  .addHeader("X-API-Key", "YH3kPJ5rKVYH3kPJ5rKVYH3kPJ5rKV")
  .build();
Response response = client.newCall(request).execute();
```
{% endtab %}
{% endtabs %}

4. 若API-Key正确 ，返回如下
   1. HTTP状态码：200
   2. 响应

```json
{
    "message": "ok"
}
```

### 相关报错

* **请求未携带API Key**
  * HTTP状态码：401
  * 响应

```json
{
    "code": 0,
    "message": "API Key未提供"
}
```

* **请求所携带API Key无效**
  * HTTP状态码：401
  * 响应

```json
{
    "code": 0,
    "message": "API Key无效"
}
```

