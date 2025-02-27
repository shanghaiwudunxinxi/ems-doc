# BMS控制

## 下发BMS控制

* **Method：**`POST`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/bms-control`</mark>
* **接口描述：**&#x4E3A;特定ems设备下发BMS控制指令
*   **请求**

    * Body参数/bmsControl



    <table><thead><tr><th width="146">参数</th><th width="85">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option></select></th><th width="67" data-type="checkbox">是否必填</th><th width="138">描述</th><th width="225">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>command</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>命令</td><td><p>1-故障复位 </p><p>2-接触器闭合 </p><p>3-接触器断开</p></td><td>1</td></tr></tbody></table>



    * **响应**
      *   数据类型：application/json

          <table><thead><tr><th width="128">参数</th><th width="86">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th width="81" data-type="checkbox">是否必填</th><th width="101">描述</th><th width="133">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>PCS控制下发成功</td></tr><tr><td>data</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>详细信息</td><td></td><td></td></tr></tbody></table>
    *   **错误码**

        | HTTP状态码 | 错误码    | 描述     |
        | ------- | ------ | ------ |
        | 200     | 0      | 成功     |
        | 400     | 100001 | 参数格式错误 |

## 获取BMS状态

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/bms-control`</mark>
* **接口描述：**&#x83B7;取BMS状态
*   **请求**

    * Query参数



    <table><thead><tr><th width="163">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
*   响应

    * &#x20;application

    <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="fb9d3250c2db42ac8efe4d4b9d504377" label="object" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td></td></tr><tr><td>data</td><td><span data-option="fb9d3250c2db42ac8efe4d4b9d504377">object</span></td><td>true</td><td>同步后的策略</td><td></td><td></td></tr></tbody></table>

    * data：



    <table><thead><tr><th width="181">参数</th><th width="73">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option></select></th><th width="78" data-type="checkbox">是否必填</th><th width="134">描述</th><th width="187">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>alarm_status</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>报警状态（单位：个）</td><td>[0, ∞]</td><td>0</td></tr><tr><td>operating_status</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>电池运行状态</td><td><p>1-下电(接触器断开) </p><p>2-静置(接触器闭合) </p><p>3-充电 </p><p>4-放电</p></td><td>1</td></tr></tbody></table>

## 同步BMS状态

* **Method：**&#x50;UT
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/bms-control/sync`</mark>
* **接口描述： 同步BMS状态**
*   **请求**

    * Query参数

    <table><thead><tr><th width="149">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
* 响应
  * &#x20;application

<table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="fb9d3250c2db42ac8efe4d4b9d504377" label="object" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>PCS状态同步成功</td></tr><tr><td>data</td><td><span data-option="fb9d3250c2db42ac8efe4d4b9d504377">object</span></td><td>true</td><td>同步后的策略</td><td></td><td></td></tr></tbody></table>

* data：

<table><thead><tr><th width="177">参数</th><th width="90">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option></select></th><th width="73" data-type="checkbox">是否必填</th><th width="129">描述</th><th width="174">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>alarm_status</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>报警状态（单位：个）</td><td>[0, ∞]</td><td>0</td></tr><tr><td>operating_status</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>电池运行状态</td><td><p>1-下电(接触器断开) </p><p>2-静置(接触器闭合) </p><p>3-充电 </p><p>4-放电</p></td><td>1</td></tr></tbody></table>

