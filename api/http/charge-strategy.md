---
description: 获取、更新、删除设备充放电策略
---

# 充放电策略

## 创建充放电策略

* **Method：**`POST`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/charge-strategy`</mark>
* **接口描述：**为特定ems设备创建充放电策略，每个设备最多四条充放电策略
* **请求**
  *   Body参数

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="5ec013b28547473da58c2c8a9988fd23" label="str" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="5ec013b28547473da58c2c8a9988fd23">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>charge_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电类型（后续将支持更多类型）</td><td>1-定时充放电</td><td>1</td></tr><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭,<br>1-开启</td><td>1</td></tr><tr><td>month</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>月份选择（0代表一月）</td><td>[0,11]</td><td>[1,7,8,11]</td></tr><tr><td>week_day</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>星期选择（0代表星期一）</td><td>[0,6]</td><td>[5,6]</td></tr><tr><td>settings</td><td><span data-option="dc27004c92e443db924ae8f38f2ec7f1">[]chargeTime</span></td><td>true</td><td>充放电时间段，支持1到8个</td><td></td><td>-</td></tr></tbody></table>
  *   chargeTime

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>start_hour</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>开始小时</td><td>[0,23]</td><td>20</td></tr><tr><td>start_minute</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>开始分钟</td><td>[0,59]</td><td>0</td></tr><tr><td>end_hour</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>结束小时</td><td>[0,23]</td><td>23</td></tr><tr><td>end_minute</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>结束分钟</td><td>[0,59]</td><td>0</td></tr><tr><td>cdc_enable_mode</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电设定</td><td>0-待机,<br>1-充电,<br>2-放电</td><td>1</td></tr><tr><td>run_power</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>运行功率(单位：kW)</td><td>[0,65535]</td><td>300</td></tr></tbody></table>
  * 示例

{% tabs %}
{% tab title="cURL" %}

{% endtab %}

{% tab title="Python" %}

{% endtab %}

{% tab title="Java" %}

{% endtab %}
{% endtabs %}

* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略创建成功</td></tr></tbody></table>
*   **错误码**

    | HTTP状态码 | 错误码    | 描述               |
    | ------- | ------ | ---------------- |
    | 400     | 100001 | 参数格式错误           |
    | 400     | 140002 | mqtt超时           |
    | 400     | 140003 | 不是设备的拥有者，操作权限不足  |
    | 400     | 140004 | 规则创建失败           |
    | 400     | 140005 | 规则更新失败           |
    | 400     | 140006 | 规则列表获取失败         |
    | 400     | 140007 | 策略数量超出限制         |
    | 400     | 140008 | 该设备ID对应的ems设备未找到 |

## 获取充放电策略

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/charge-strategy`</mark>
* **接口描述：**获取充放电策略
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th>类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="21f76dd5e4db4a54951b45449203a290" label="str" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>false</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>page-size</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>每页设备数量（默认值为50）</td><td>[0, ∞]</td><td>50</td></tr><tr><td>page</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>页码（默认值 1）</td><td>[0, ∞]</td><td>1</td></tr></tbody></table>
  * 示例
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>错误描述</td><td>-</td><td>-</td></tr><tr><td>data</td><td><span data-option="a1530006d2194402bf5a2360eac38945">listResult</span></td><td>true</td><td>每页设备数量（默认值为50）</td><td>-</td><td>50</td></tr></tbody></table>
  *   listResult

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="4a37161ece0d4d54a10f739af7f3b503" label="[]chargeStrategy" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>total</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>总策略数</td><td>[0, ∞]</td><td>10</td></tr><tr><td>list</td><td><span data-option="4a37161ece0d4d54a10f739af7f3b503">[]chargeStrategy</span></td><td>true</td><td>策略列表</td><td>-</td><td>-</td></tr></tbody></table>
  *   chargeStrategy

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="fa6130284c6e46088d1efb54b0424187" label="str" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>charge_id</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略ID</td><td>[0, ∞]</td><td>1</td></tr><tr><td>device_uid</td><td><span data-option="fa6130284c6e46088d1efb54b0424187">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>index</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略在设侧的索引</td><td>[0,3]</td><td>2</td></tr><tr><td>charge_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电类型（后续将支持更多类型）</td><td>1-定时充放电</td><td>1</td></tr><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭,<br>1-开启</td><td>1</td></tr><tr><td>month</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>月份选择（0代表一月）</td><td>[0,11]</td><td>[1,7,8,11]</td></tr><tr><td>week_day</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>星期选择（0代表星期一）</td><td>[0,6]</td><td>[5,6]</td></tr><tr><td>settings</td><td><span data-option="dc27004c92e443db924ae8f38f2ec7f1">[]chargeTime</span></td><td>true</td><td>充放电时间段</td><td>-</td><td>-</td></tr></tbody></table>
*   错误码

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 根据策略ID修改策略

* **Method：**PATCH
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/charge-strategy/:id`</mark>
* **接口描述：**根据策略ID修改策略
* **请求**
  *   路径参数

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>:id</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>策略ID</td><td>[0, ∞]</td><td>1</td></tr></tbody></table>
  *   Body参数

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="fa6130284c6e46088d1efb54b0424187" label="str" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>charge_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电类型（后续将支持更多类型）</td><td>1-定时充放电</td><td>1</td></tr><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭,<br>1-开启</td><td>1</td></tr><tr><td>month</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>月份选择（0代表一月）</td><td>[0,11]</td><td>[1,7,8,11]</td></tr><tr><td>week_day</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>星期选择（0代表星期一）</td><td>[0,6]</td><td>[5,6]</td></tr><tr><td>settings</td><td><span data-option="dc27004c92e443db924ae8f38f2ec7f1">[]chargeTime</span></td><td>true</td><td>充放电时间段</td><td>-</td><td>-</td></tr></tbody></table>
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略更新成功</td></tr></tbody></table>
*   **错误码**

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 根据设备及索引修改策略

* **Method：**PATCH
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/charge-strategy`</mark>
* **接口描述：**根据设备及索引修改策略
* **请求**
  *   Query参数

      <table><thead><tr><th width="154">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>index</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>策略在设侧的索引</td><td>[0,3]</td><td>2</td></tr></tbody></table>
  *   Body参数

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="fa6130284c6e46088d1efb54b0424187" label="str" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>charge_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电类型（后续将支持更多类型）</td><td>1-定时充放电</td><td>1</td></tr><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭,<br>1-开启</td><td>1</td></tr><tr><td>month</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>月份选择（0代表一月）</td><td>[0,11]</td><td>[1,7,8,11]</td></tr><tr><td>week_day</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>星期选择（0代表星期一）</td><td>[0,6]</td><td>[5,6]</td></tr><tr><td>settings</td><td><span data-option="dc27004c92e443db924ae8f38f2ec7f1">[]chargeTime</span></td><td>true</td><td>充放电时间段</td><td>-</td><td>-</td></tr></tbody></table>
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略更新成功</td></tr></tbody></table>
*   **错误码**

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |



## 同步充放电策略

* **Method：**PUT
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/charge-strategy/sync`</mark>
* **接口描述： 同步充放电策略**
* **请求**
  *   Query参数

      <table><thead><tr><th width="146">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
* **响应**
  *   &#x20;数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略更新成功</td></tr><tr><td>data</td><td><span data-option="a1530006d2194402bf5a2360eac38945">listResult</span></td><td>true</td><td>同步后的充放电策略列表</td><td></td><td></td></tr></tbody></table>
