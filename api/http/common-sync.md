# 实时获取

## 同步特定字段

* **Method：**PUT
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/common-sync`</mark>
* **接口描述：**请求同步特定字段
*   **请求**

    * Query参数

    <table><thead><tr><th width="149">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>

    * Body参数

    <table><thead><tr><th width="149">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="str" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="[]str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>fields</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">[]str</span></td><td>true</td><td>同步字段</td><td>pcs_total_active_power（更多字段需求请联系物盾）</td><td>["pcs_total_active_power"]</td></tr></tbody></table>

    * 示例

{% tabs %}
{% tab title="cURL" %}
```powershell
curl --location 
--request PUT 'https://www.einfra.cn/wad/ems/v1/api/common-sync?device_uid=xxxxx' \
--header 'X-API-Key: xxxxx' \
--header 'Content-Type: application/json' \
--data '{
    "fields": ["pcs_total_active_power"]
}'
```
{% endtab %}
{% endtabs %}

* 响应
  *   application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="fb9d3250c2db42ac8efe4d4b9d504377" label="object" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>获取实时数据成功</td></tr><tr><td>data</td><td><span data-option="fb9d3250c2db42ac8efe4d4b9d504377">object</span></td><td>true</td><td></td><td></td><td></td></tr></tbody></table>
  *   data

      <table><thead><tr><th width="177">参数</th><th width="90">类型<select><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option><option value="9a1bae556a2448e5b9e72eafa777b893" label="float" color="blue"></option></select></th><th width="73" data-type="checkbox">是否必填</th><th width="129">描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>pcs_total_active_power</td><td><span data-option="9a1bae556a2448e5b9e72eafa777b893">float</span></td><td>false</td><td>PCS 总输出有功功率（单位：kW）</td><td>-</td><td>300.0</td></tr></tbody></table>
*   错误码

    | HTTP状态码 | 错误码    | 描述               |
    | ------- | ------ | ---------------- |
    | 400     | 100001 | 参数格式错误           |
    | 400     | 140008 | 该设备ID对应的ems设备未找到 |
    | 400     | 140003 | 不是设备的拥有者，操作权限不足  |
    | 400     | 140002 | mqtt超时           |
    | 400     | 140001 | mqtt处理失败         |
