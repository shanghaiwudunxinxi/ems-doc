---
description: 获取、更新、删除空调联动策略
---

# 空调联动策略

## 创建空调联动策略

* **Method：**`POST`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/air-strategy`</mark>
* **接口描述：**为特定ems设备创建空调联动策略，每个设备最多一条策略
* **请求**
  *   Body参数/airStrategy

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th width="53">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>cooling_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-制冷点（单位：℃）</td><td>-</td><td>1</td></tr><tr><td>cooling_hysteresis</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-制冷回差（单位：℃）</td><td>-</td><td>1</td></tr><tr><td>heating_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-加热点（单位：℃）</td><td>-</td><td>1</td></tr><tr><td>heating_hysteresis</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-加热回差（单位：℃）</td><td>-</td><td>-1</td></tr><tr><td>high_temp_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-高温点（单位：℃）</td><td></td><td>1</td></tr><tr><td>low_temp_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-低温点（单位：℃）</td><td></td><td>1</td></tr><tr><td>high_humidity_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>是 空调设置-高湿点（单位：%）</td><td></td><td>1</td></tr></tbody></table>
  * 示例

{% tabs %}
{% tab title="cURL" %}
```shell
curl --request POST \
  --url https://www.einfra.cn/wad/ems/v1/api/air-strategy \
  --header 'X-API-Key: YH3kPJ5rKVYH3kPJ5rKVYH3kPJ5rKV' \
  --header 'content-type: application/json' \
  --data '{
    "device_uid": "xxxxx",
    "cooling_point": 1,
    "cooling_hysteresis": 2,
    "heating_point": 3,
    "heating_hysteresis": 4,
    "high_temp_point": 5,
    "low_temp_point": 6,
    "high_humidity_point": 7
}'
```
{% endtab %}

{% tab title="Python" %}
```python
import http.client

conn = http.client.HTTPConnection("https://www.einfra.cn")

payload = "{\n    \"cooling_point\": 1,\n    \"cooling_hysteresis\": 2,\n    \"heating_point\": 3,\n    \"heating_hysteresis\": 4,\n    \"high_temp_point\": 5,\n    \"low_temp_point\": 6,\n    \"high_humidity_point\": 7,\n    \"device_uid\": \"xxxxx\"\n}"

headers = {
    'X-API-Key': "YH3kPJ5rKVYH3kPJ5rKVYH3kPJ5rKV",
    'content-type': "application/json"
    }

conn.request("POST", "/wad/ems/v1/api/air-strategy", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```
{% endtab %}

{% tab title="Go" %}


```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://www.einfra.cn/wad/ems/v1/api/air-strategy"

	payload := strings.NewReader("{\n    \"cooling_point\": 1,\n    \"cooling_hysteresis\": 2,\n    \"heating_point\": 3,\n    \"heating_hysteresis\": 4,\n    \"high_temp_point\": 5,\n    \"low_temp_point\": 6,\n    \"high_humidity_point\": 7,\n    \"device_uid\": \"xxxxx\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("X-API-Key", "YH3kPJ5rKVYH3kPJ5rKVYH3kPJ5rKV")
	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

```
{% endtab %}
{% endtabs %}

* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略创建成功</td></tr><tr><td>data</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>详细信息</td><td></td><td></td></tr></tbody></table>
*   **错误码**

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |
    | 200     |        | 成功     |

## 获取空调联动策略列表

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/air-strategy`</mark>
* **接口描述：**获取空调联动策略列表
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th>类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="21f76dd5e4db4a54951b45449203a290" label="str" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>false</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>page-size</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>每页设备数量（默认值为50）</td><td>[0, ∞]</td><td>50</td></tr><tr><td>page</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>页码（默认值 1）</td><td>[0, ∞]</td><td>1</td></tr></tbody></table>
  * 示例
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>错误描述</td><td>-</td><td>-</td></tr><tr><td>data</td><td><span data-option="a1530006d2194402bf5a2360eac38945">listResult</span></td><td>true</td><td>每页设备数量（默认值为50）</td><td>-</td><td>50</td></tr></tbody></table>
  *   listResult

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="4a37161ece0d4d54a10f739af7f3b503" label="[]protectionStrategy" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>total</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>总策略数</td><td>[0, ∞]</td><td>10</td></tr><tr><td>list</td><td><span data-option="4a37161ece0d4d54a10f739af7f3b503">[]protectionStrategy</span></td><td>true</td><td>策略列表</td><td>-</td><td>-</td></tr></tbody></table>
*   错误码

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 修改空调联动策略

* **Method：**PATCH
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/air-strategy`</mark>
* **接口描述：**根据设备uid修改策略
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th width="99">描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
  * Body参数/airStrategy
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略更新成功</td></tr></tbody></table>
*   **错误码**

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 同步空调联动策略

* **Method：**PUT
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/air-strategy/sync`</mark>
* **接口描述： 同步空调联动策略**
*   **请求**

    * Query参数

    <table><thead><tr><th width="663">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
* 响应
  * &#x20;application

<table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="fb9d3250c2db42ac8efe4d4b9d504377" label="object" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略更新成功</td></tr><tr><td>data</td><td><span data-option="fb9d3250c2db42ac8efe4d4b9d504377">object</span></td><td>true</td><td>同步后的策略</td><td></td><td></td></tr></tbody></table>

*   data：

    <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th width="53">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>cooling_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-制冷点（单位：℃）</td><td>-</td><td>1</td></tr><tr><td>cooling_hysteresis</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-制冷回差（单位：℃）</td><td>-</td><td>1</td></tr><tr><td>heating_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-加热点（单位：℃）</td><td>-</td><td>1</td></tr><tr><td>heating_hysteresis</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-加热回差（单位：℃）</td><td>-</td><td>-1</td></tr><tr><td>high_temp_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-高温点（单位：℃）</td><td></td><td>1</td></tr><tr><td>low_temp_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>空调设置-低温点（单位：℃）</td><td></td><td>1</td></tr><tr><td>high_humidity_point</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>是 空调设置-高湿点（单位：%）</td><td></td><td>1</td></tr></tbody></table>
