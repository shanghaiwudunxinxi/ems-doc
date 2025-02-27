---
description: 查看、更新设备信息。
---

# EMU设备信息

## 根据更新时间范围获取设备列表

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/device/by-time`</mark>
* **接口描述：**&#x6839;据更新时间获取设备列表
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th>类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>start_time</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>开始时间戳（单位：秒）</td><td>[0, ∞]</td><td>1696089600</td></tr><tr><td>end_time</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>结束时间戳（单位：秒）</td><td>[0, ∞]</td><td>1697179204</td></tr><tr><td>page-size</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>每页设备数量（默认值为50）</td><td>[0, ∞]</td><td>50</td></tr><tr><td>page</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>页码（默认值 1）</td><td>[0, ∞]</td><td>1</td></tr></tbody></table>
  * 示例

{% tabs %}
{% tab title="cURL" %}

{% endtab %}

{% tab title="Python" %}

{% endtab %}

{% tab title="Untitled" %}

{% endtab %}
{% endtabs %}

* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>错误描述</td><td>-</td><td>-</td></tr><tr><td>data</td><td><span data-option="a1530006d2194402bf5a2360eac38945">listResult</span></td><td>true</td><td>每页设备数量（默认值为50）</td><td>-</td><td>50</td></tr></tbody></table>
  *   listResult

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="4a37161ece0d4d54a10f739af7f3b503" label="[]emsDevice" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>total</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>总设备数</td><td>[0, ∞]</td><td>10</td></tr><tr><td>list</td><td><span data-option="4a37161ece0d4d54a10f739af7f3b503">[]emsDevice</span></td><td>true</td><td>设备列表</td><td>-</td><td>-</td></tr></tbody></table>
  *   emsDevice

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="4a37161ece0d4d54a10f739af7f3b503" label="[]emsDevice" color="blue"></option><option value="3300c89a832442589eed260b55df3d10" label="time" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>license_code</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>激活码</td><td>-</td><td>DNAFPQFRTWXXUKRJ</td></tr><tr><td>name</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备名</td><td>-</td><td>EMS设备</td></tr><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>代码</td><td></td><td>1</td></tr><tr><td>location</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>所在位置</td><td></td><td>上海</td></tr><tr><td>affiliation</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>拥有权限</td><td>1-管理<br>2-查看</td><td>1</td></tr><tr><td>heartbeat_time</td><td><span data-option="3300c89a832442589eed260b55df3d10">time</span></td><td>false</td><td>最后心跳时间</td><td>-</td><td>2023-10-01T00:00:00Z</td></tr></tbody></table>
*   错误码

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 获取设备列表

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/device`</mark>
* **接口描述：**&#x83B7;取设备列表
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th>类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>page-size</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>每页设备数量（默认值为50）</td><td>[0, ∞]</td><td>50</td></tr><tr><td>page</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>页码（默认值 1）</td><td>[0, ∞]</td><td>1</td></tr></tbody></table>
  * 示例

{% tabs %}
{% tab title="cURL" %}
```sh
curl --location 'https://www.einfra.cn/wad/ems/v1/api/device?page-size=10&page=1' \
--header 'X-API-Key: YH3kPJ5rKV'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://www.einfra.cn/wad/ems/v1/api/device?page-size=10&page=1"

headers = {
  'X-API-Key': 'YH3kPJ5rKV'
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
  .url("https://www.einfra.cn/wad/ems/v1/api/device?page-size=10&page=1")
  .method("GET", body)
  .addHeader("X-API-Key", "YH3kPJ5rKVP")
  .build();
Response response = client.newCall(request).execute();java
```
{% endtab %}
{% endtabs %}

* **响应**
  * 数据类型：application/json
  * 同<mark style="color:red;">`/device/by-time`</mark>
*   错误码

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 更新设备信息

* **Method：**`PATCH`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/device`</mark>
* **接口描述：**&#x66F4;新设备信息
* **请求**
  *   Body参数

      <table><thead><tr><th>参数</th><th>类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="21f76dd5e4db4a54951b45449203a290" label="str" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>name</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>true</td><td>设备名称（唯一）</td><td>长度小于48，无空格</td><td>ems设备</td></tr><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>设备代码</td><td>[0, ∞]</td><td>10312</td></tr><tr><td>location</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>false</td><td>设备位置</td><td>长度小于256</td><td>上海</td></tr></tbody></table>


* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>设备修改成功</td></tr></tbody></table>
*   错误码

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |
    | 400     | 100007 | 该记录未找到 |
    | 400     | 100010 | 名称重复   |
