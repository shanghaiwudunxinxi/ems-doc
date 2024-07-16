---
description: 绑定、解绑设备。
---

# 设备管理

## 绑定设备

* **Method：**`POST`
* **URL：**`https://www.einfra.cn/wad/`<mark style="color:red;">`emm`</mark>`/v1/api`<mark style="color:red;">`/device/bind-owner`</mark>
* **接口描述：**绑定设备
* **请求**
  *   Body参数

      <table><thead><tr><th>参数</th><th>类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="21f76dd5e4db4a54951b45449203a290" label="str" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>license_code</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>true</td><td>设备激活码</td><td>-</td><td>6rDMfM0MVoB8jQHkDrPFey</td></tr><tr><td>name</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>true</td><td>设备名称（唯一）</td><td>长度小于48，无空格</td><td>ems设备</td></tr><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>设备代码</td><td>[0, ∞]</td><td>10312</td></tr><tr><td>location</td><td><span data-option="21f76dd5e4db4a54951b45449203a290">str</span></td><td>false</td><td>设备位置</td><td>长度小于256</td><td>上海</td></tr></tbody></table>
* **响应**
  *   数据类型：application/json

      <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>绑定成功</td></tr></tbody></table>
*   **错误码**

    | HTTP状态码 | 错误码    | 描述     |
    | ------- | ------ | ------ |
    | 400     | 100001 | 参数格式错误 |
    | 400     | 100007 | 该记录未找到 |
    | 400     | 100010 | 名称重复   |
