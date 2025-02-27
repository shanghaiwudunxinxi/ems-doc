---
description: 获取、更新、删除设备保护策略
---

# 保护策略

## 创建保护策略

* **Method：**`POST`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/protection-strategy`</mark>
* **接口描述：**&#x4E3A;特定ems设备创建保护策略，每个设备最多一条策略
* **请求**
  *   Body参数/protectionStrategy

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="bf06562ca6414412b921d032747c0cb4" label="str" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="bf06562ca6414412b921d032747c0cb4">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>streaming</td><td><span data-option="13f5f7e233844eca8e11ff995c863432">streaming</span></td><td>true</td><td>防逆流</td><td>-</td><td>-</td></tr><tr><td>overdemand</td><td><span data-option="578d846029d045879f81a03e30ac19ff">overdemand</span></td><td>true</td><td>防过需</td><td>-</td><td>-</td></tr><tr><td>charge_depth</td><td><span data-option="5620061ebf2d47e18a839b283a24cc45">chargeDepth</span></td><td>true</td><td>放电深度保护</td><td>-</td><td>-</td></tr><tr><td>safety</td><td><span data-option="bf6b0330299043f49d8c6246b932a936">safety</span></td><td>true</td><td>安全保护</td><td>-</td><td>-</td></tr></tbody></table>
  *   streaming

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>total_margin</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>总安全余量（单位：kW）</td><td> [0,65535]</td><td>1000</td></tr><tr><td>margin_a</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>A相独立安全余量（单位：kW）</td><td>[0,65535]</td><td>400</td></tr><tr><td>margin_b</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>B相独立安全余量（单位：kW）</td><td>[0,65535]</td><td>400</td></tr><tr><td>margin_b</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>C相独立安全余量（单位：kW）</td><td>[0,65535]</td><td>400</td></tr></tbody></table>
  *   overdemand

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭1-开启</td><td>1</td></tr><tr><td>total_demand</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>总最大需量（单位：kW）</td><td> [0,65535]</td><td>1000</td></tr><tr><td>demand_a</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>A相独立最大需量（单位：kW）</td><td>[0,65535]</td><td>400</td></tr><tr><td>demand_b</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>B相独立最大需量（单位：kW）</td><td>[0,65535]</td><td>400</td></tr><tr><td>demand_c</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>C相独立最大需量（单位：kW）</td><td>[0,65535]</td><td>400</td></tr></tbody></table>
  *   chargeDepth

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="c131da9d8eee454eb2c708057b010579" label="int" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>charge_depth</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>充电保护深度SOC（单位：%）</td><td>[0,100]</td><td>70</td></tr><tr><td>charge_slow</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>开始减缓充电SOC（单位：%）</td><td>[0,100]</td><td>80</td></tr><tr><td>charge_max_vol</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>单体最高电压末端控制（单位：V）</td><td>[0,65535]</td><td>300</td></tr><tr><td>charge_pcs</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>开始减缓充电PCS输出（单位：%）</td><td>[0,100]</td><td>50</td></tr><tr><td>discharge_depth</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>放电保护深度SOC（单位：%）</td><td>[0,100]</td><td>100</td></tr><tr><td>discharge_slow</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>开始减缓放电SOC（单位：%）</td><td>[0,100]</td><td>80</td></tr><tr><td>discharge_min_vol</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>单体最低电压末端控制（单位：V）</td><td>[0,65535]</td><td>200</td></tr><tr><td>discharge_pcs</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>开始减缓放电PCS输出（单位：%）</td><td>[0,100]</td><td>50</td></tr></tbody></table>


  *   safety

      <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="c131da9d8eee454eb2c708057b010579" label="int" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>bms_3</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>BMS三级报警停机开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>bms_2</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>BMS二级报警降功率开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>bms_2_kw</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>false</td><td>BMS二级报警降功率开关（单位：kW）</td><td>[0,65535]</td><td>400</td></tr><tr><td>aircon</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>空调掉线停机开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>aircon_mins</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>false</td><td>空调掉线持续时间（单位：min）</td><td>[0,65535]</td><td>5</td></tr><tr><td>temp</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>室内温度过高停机开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>temp_celsius</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>false</td><td>室内温度过高值（单位：℃）</td><td>[0,65535]</td><td>50</td></tr><tr><td>grounded</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>接地离线停机开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>grounded_mins</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>false</td><td>接地离线持续时间（单位：min）</td><td>[0,65535]</td><td>5</td></tr><tr><td>fire_control</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>消防报警停机开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>flooding</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>true</td><td>水浸报警停机开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>meter_offline_power0</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>false</td><td>负荷电表离线功率为0开关</td><td>0-关闭<br>1-开启</td><td>1</td></tr><tr><td>meter_offline_mins</td><td><span data-option="c131da9d8eee454eb2c708057b010579">int</span></td><td>false</td><td>负荷电表离线持续时间（单位：min）</td><td>[0,65535]</td><td>5</td></tr></tbody></table>
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

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 获取保护策略

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/protection-strategy`</mark>
* **接口描述：**&#x83B7;取充放电策略
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

## 修改策略

* **Method：**&#x50;ATCH
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/protection-strategy`</mark>
* **接口描述：**&#x6839;据设备及索引修改策略
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
  * Body参数/protectionStrategy
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略更新成功</td></tr></tbody></table>
*   **错误码**

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

## 同步保护策略

* **Method：**&#x50;UT
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/protection-strategy/sync`</mark>
* **接口描述：**&#x540C;步保护策略
* **请求**
  *   Query参数

      <table><thead><tr><th width="146">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
* **响应**
  *   &#x20;数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>策略更新成功</td></tr><tr><td>data</td><td><span data-option="a1530006d2194402bf5a2360eac38945">listResult</span></td><td>true</td><td>同步后的保护策略列表</td><td></td><td></td></tr></tbody></table>
