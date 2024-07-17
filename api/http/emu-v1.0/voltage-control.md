# 【未上线】电压治理

## 下发电压治理控制

* **Method：**`POST`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/voltage-control`</mark>
* **接口描述：**为特定ems设备下发电压治理控制指令
*   **请求**

    * Body参数/voltageControl



    <table><thead><tr><th width="223">参数</th><th width="79">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option><option value="f3ccac124c5143dbbf3d2987cfd716fc" label="float" color="blue"></option></select></th><th width="50" data-type="checkbox">是否必填</th><th width="183">描述</th><th width="78">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>phase_rated_voltage_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>A相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_rated_voltage_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_rated_voltage_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_voltage_upper_limit_threshold_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压上限阈值,A相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_upper_limit_threshold_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压上限阈值,B相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_upper_limit_threshold_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压上限阈值,C相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_lower_limit_threshold_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压上限阈值,A相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_lower_limit_threshold_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压上限阈值,B相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_lower_limit_threshold_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压上限阈值,C相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_hysteresis_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压回差,触发调节后,A相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>phase_voltage_hysteresis_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压回差,触发调节后,B相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>phase_voltage_hysteresis_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压回差,触发调节后,C相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>period</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>调节周期,单位毫秒</td><td>-</td><td>500</td></tr><tr><td>step</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>步长,每次调节的步长</td><td>-</td><td>5</td></tr></tbody></table>



    * **响应**
      *   数据类型：application/json

          <table><thead><tr><th width="128">参数</th><th width="86">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th width="81" data-type="checkbox">是否必填</th><th width="101">描述</th><th width="133">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>PCS控制下发成功</td></tr><tr><td>data</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>详细信息</td><td></td><td></td></tr></tbody></table>
    *   **错误码**

        | HTTP状态码 | 错误码    | 描述     |
        | ------- | ------ | ------ |
        | 200     | 0      | 成功     |
        | 400     | 100001 | 参数格式错误 |

## 获取电压治理控制

* **Method：**`GET`
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/voltage-control`</mark>
* **接口描述：**获取电压治理控制
*   **请求**

    * Query参数



    <table><thead><tr><th width="163">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
*   响应

    * &#x20;application

    <table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="fb9d3250c2db42ac8efe4d4b9d504377" label="object" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td></td></tr><tr><td>data</td><td><span data-option="fb9d3250c2db42ac8efe4d4b9d504377">object</span></td><td>true</td><td>同步后的控制</td><td></td><td></td></tr></tbody></table>

    * data：

    <table><thead><tr><th width="223">参数</th><th width="79">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option><option value="f3ccac124c5143dbbf3d2987cfd716fc" label="float" color="blue"></option></select></th><th width="50" data-type="checkbox">是否必填</th><th width="183">描述</th><th width="78">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>phase_rated_voltage_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>A相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_rated_voltage_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_rated_voltage_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_voltage_upper_limit_threshold_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压上限阈值,A相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_upper_limit_threshold_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压上限阈值,B相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_upper_limit_threshold_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压上限阈值,C相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_lower_limit_threshold_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压上限阈值,A相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_lower_limit_threshold_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压上限阈值,B相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_lower_limit_threshold_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压上限阈值,C相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_hysteresis_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压回差,触发调节后,A相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>phase_voltage_hysteresis_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压回差,触发调节后,B相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>phase_voltage_hysteresis_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压回差,触发调节后,C相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>period</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>调节周期,单位毫秒</td><td>-</td><td>500</td></tr><tr><td>step</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>步长,每次调节的步长</td><td>-</td><td>5</td></tr></tbody></table>

## 同步电压治理控制

* **Method：**PUT
* **URL：**`https://www.einfra.cn/wad/ems/v1/api`<mark style="color:red;">`/voltage-control/sync`</mark>
* **接口描述： 同步电压治理控制**
*   **请求**

    * Query参数

    <table><thead><tr><th width="149">参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr></tbody></table>
* 响应
  * &#x20;application

<table><thead><tr><th>参数</th><th width="113">类型<select><option value="47624d5c9393461e9a8ecece42e932a4" label="int" color="blue"></option><option value="86eb210b3c8c4e78b798bd84c85688fe" label="str" color="blue"></option><option value="a1530006d2194402bf5a2360eac38945" label="listResult" color="blue"></option><option value="fb9d3250c2db42ac8efe4d4b9d504377" label="object" color="blue"></option></select></th><th width="107" data-type="checkbox">是否必填</th><th>描述</th><th width="123">范围</th><th>样例</th></tr></thead><tbody><tr><td>code</td><td><span data-option="47624d5c9393461e9a8ecece42e932a4">int</span></td><td>true</td><td>错误码</td><td>见下文错误码</td><td>0</td></tr><tr><td>message</td><td><span data-option="86eb210b3c8c4e78b798bd84c85688fe">str</span></td><td>true</td><td>描述</td><td>-</td><td>电压治理同步成功</td></tr><tr><td>data</td><td><span data-option="fb9d3250c2db42ac8efe4d4b9d504377">object</span></td><td>true</td><td>同步后的控制</td><td></td><td></td></tr></tbody></table>

* data：

<table><thead><tr><th width="223">参数</th><th width="79">类型<select><option value="13f5f7e233844eca8e11ff995c863432" label="streaming" color="blue"></option><option value="578d846029d045879f81a03e30ac19ff" label="overdemand" color="blue"></option><option value="5620061ebf2d47e18a839b283a24cc45" label="chargeDepth" color="blue"></option><option value="bf6b0330299043f49d8c6246b932a936" label="safety" color="blue"></option><option value="193cc2f0dc5b4a6197c8a4e8c79dfee4" label="int" color="blue"></option><option value="18d18a729bf94885843098182240bff3" label="string" color="blue"></option><option value="f3ccac124c5143dbbf3d2987cfd716fc" label="float" color="blue"></option></select></th><th width="50" data-type="checkbox">是否必填</th><th width="183">描述</th><th width="78">范围</th><th>样例</th></tr></thead><tbody><tr><td>device_uid</td><td><span data-option="18d18a729bf94885843098182240bff3">string</span></td><td>true</td><td>设备唯一ID</td><td>-</td><td>xxxxx</td></tr><tr><td>phase_rated_voltage_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>true</td><td>A相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_rated_voltage_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_rated_voltage_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相额定电压,希望A相保持的电压（单位：V）</td><td>-</td><td>220</td></tr><tr><td>phase_voltage_upper_limit_threshold_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压上限阈值,A相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_upper_limit_threshold_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压上限阈值,B相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_upper_limit_threshold_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压上限阈值,C相平均电压高于该阈值则触发调节策略（单位：V）</td><td>-</td><td>240</td></tr><tr><td>phase_voltage_lower_limit_threshold_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压上限阈值,A相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_lower_limit_threshold_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压上限阈值,B相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_lower_limit_threshold_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压上限阈值,C相平均电压低于该阈值则触发调节策略（单位：V）</td><td>-</td><td>200</td></tr><tr><td>phase_voltage_hysteresis_a</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>A相电压回差,触发调节后,A相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>phase_voltage_hysteresis_b</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>B相电压回差,触发调节后,B相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>phase_voltage_hysteresis_c</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>C相电压回差,触发调节后,C相平均电压达到回差值时,停止调节</td><td></td><td>5</td></tr><tr><td>period</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>调节周期,单位毫秒</td><td>-</td><td>500</td></tr><tr><td>step</td><td><span data-option="193cc2f0dc5b4a6197c8a4e8c79dfee4">int</span></td><td>false</td><td>步长,每次调节的步长</td><td>-</td><td>5</td></tr></tbody></table>
