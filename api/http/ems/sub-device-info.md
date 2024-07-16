---
description: 查看、更新设备信息。
---

# 【未上线】二级子设备信息

## 获取子设备列表

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/sub-device`</mark>
* **接口描述：**获取设备列表
* **请求**
  *   Query参数

      <table><thead><tr><th>参数</th><th>类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="e03078992bf54b5988ed9ffe0c160e15" label="str" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="e03078992bf54b5988ed9ffe0c160e15">str</span></td><td>true</td><td>二级EMS设备唯一ID</td><td></td><td>xxxxxxxxx</td></tr><tr><td>subdevice_type</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>子设备类型（1-储能设备；2-电表设备）</td><td></td><td></td></tr><tr><td>page-size</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>每页设备数量（默认值为50）</td><td>[0, ∞]</td><td>50</td></tr><tr><td>page</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>页码（默认值 1）</td><td>[0, ∞]</td><td>1</td></tr></tbody></table>
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>false</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>错误描述</td><td>-</td><td>-</td></tr><tr><td>data</td><td><span data-option="a1530006d2194402bf5a2360eac38945">listResult</span></td><td>true</td><td>每页设备数量（默认值为50）</td><td>-</td><td>50</td></tr></tbody></table>
  *   listResult

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="4a37161ece0d4d54a10f739af7f3b503" label="[]emsDevice或[]elecMeter" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>total</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>总设备数</td><td>[0, ∞]</td><td>10</td></tr><tr><td>list</td><td><span data-option="4a37161ece0d4d54a10f739af7f3b503">[]emsDevice或[]elecMeter</span></td><td>true</td><td>设备列表</td><td>-</td><td>-</td></tr></tbody></table>
  *   emsDevice

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="4a37161ece0d4d54a10f739af7f3b503" label="[]emsDevice" color="blue"></option><option value="3300c89a832442589eed260b55df3d10" label="time" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>设备ID</td><td>-</td><td>1</td></tr><tr><td>uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>设备UID</td><td>-</td><td>xxxx</td></tr><tr><td>name</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>设备名称</td><td>-</td><td>EMS设备</td></tr><tr><td>device_type</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>设备类型</td><td>-</td><td></td></tr><tr><td>running_status</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>运行状态（1-运行、2-离线、3-故障）</td><td>-</td><td>2</td></tr></tbody></table>
  *   elecMeter

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="4a37161ece0d4d54a10f739af7f3b503" label="[]emsDevice" color="blue"></option><option value="3300c89a832442589eed260b55df3d10" label="time" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>设备ID</td><td>-</td><td>1</td></tr><tr><td>uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>设备UID</td><td>-</td><td>xxxx</td></tr><tr><td>device_type</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>false</td><td>设备类型</td><td>-</td><td></td></tr><tr><td>factor</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>倍率</td><td>-</td><td>10</td></tr><tr><td>running_status</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>运行状态（1-运行、2-离线）</td><td>-</td><td>1</td></tr></tbody></table>
*   错误码

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |

