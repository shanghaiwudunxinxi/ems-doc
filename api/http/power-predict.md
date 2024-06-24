---
description: 查看、更新设备信息。
---

# 用电负荷功率预测

## 用电负荷功率预测

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/power/load-forecast`</mark>
* **接口描述：**获取24小时或者7天用电负荷功率预测
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th>类型<select></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>period</td><td></td><td>true</td><td>预测周期</td><td>24h, 7d</td><td>24h</td></tr></tbody></table>
  * 示例

{% tabs %}
{% tab title="cURL" %}
```
curl --location 'https://www.einfra.cn/wad/ems/v1/api/power/load-forecast?period=24h' \
--header 'X-API-Key: YH3kPJ5rKV'
```
{% endtab %}

{% tab title="Python" %}

{% endtab %}

{% tab title="Untitled" %}

{% endtab %}
{% endtabs %}

* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>错误描述</td><td>-</td><td>-</td></tr><tr><td>data</td><td><span data-option="a1530006d2194402bf5a2360eac38945">listResult</span></td><td>true</td><td>每15分钟用电负荷预测数据</td><td>-</td><td><p></p><pre class="language-json"><code class="lang-json">{"00:00":227.67,"00:01":263.67,"00:02":262.63,...}
      </code></pre></td></tr></tbody></table>
*   错误码

    <table><thead><tr><th>HTTP状态码</th><th width="500">错误码</th><th>描述</th></tr></thead><tbody><tr><td>400</td><td>100001</td><td>参数格式错误</td></tr></tbody></table>
