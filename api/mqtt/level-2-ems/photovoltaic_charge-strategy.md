# 策略-光伏均衡充放电

## 上报充放电策略

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/list`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/list`</mark>`/post`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_list</td><td>photovoltaic_charge_list</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data/ChargeDetail</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data/ChargeDetail**

    <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="7b18b87853a34308b8576531588a6c12" label="[]emsDevice" color="blue"></option><option value="WJJvuYRv6dm6" label="bool" color="blue"></option><option value="CZ8LBlnYoEPR" label="[]Device" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>ID</td><td>-</td><td>1</td></tr><tr><td>charge_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电类型（后续将支持更多类型）</td><td>1-定时充放电</td><td>1</td></tr><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭,<br>1-开启</td><td>1</td></tr><tr><td>year</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>年</td><td>（若mode=1,则year为必填；)</td><td>2024</td></tr><tr><td>month</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>月份选择（0代表一月）</td><td>[0,11]</td><td>[1,7,8,11]</td></tr><tr><td>week_day</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>false</td><td>星期选择（0代表星期一）</td><td>[0,6]</td><td>[5,6]</td></tr><tr><td>dates</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>false</td><td>日期选择（0代表1日）</td><td>[0, 30]（根据年份大小月份变化）</td><td>[0,1]</td></tr><tr><td>mode</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>模式（根据mode参数取值不同，校验week_day或dates是否必填）</td><td>1-月日模式<br>2- 月周模式<br></td><td>1（若mode=1,则dates为必填；若mode=2，则week_day为必填</td></tr><tr><td>devices</td><td><span data-option="CZ8LBlnYoEPR">[]Device</span></td><td>true</td><td>光伏设备列表</td><td>-</td><td>-</td></tr><tr><td>settings</td><td><span data-option="dc27004c92e443db924ae8f38f2ec7f1">[]chargeTime</span></td><td>true</td><td>充放电时间段</td><td>-</td><td>-</td></tr><tr><td>apply_to_all</td><td><span data-option="WJJvuYRv6dm6">bool</span></td><td>true</td><td>是否包括所有设备</td><td>-</td><td>false</td></tr></tbody></table>
*   **Payload - Device**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="1b28025203f644c291919cb0f1184736" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="127">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td><a href="https://wudun.atlassian.net/browse/DGHDJSJKD-1?atlOrigin=eyJpIjoiYjM0MTA4MzUyYTYxNDVkY2IwMzVjOGQ3ZWQ3NzMwM2QiLCJwIjoianN3LWdpdGxhYlNNLWludCJ9">DGHDJSJKD-1</a></td></tr><tr><td>name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>ems设备</td></tr><tr><td>site_name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>ems站点</td></tr><tr><td>location</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>详细地理位置</td><td>-</td><td>wudun</td></tr><tr><td>longitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>经度</td><td>-</td><td></td></tr><tr><td>latitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>纬度</td><td></td><td></td></tr><tr><td>level</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>EMS等级</td><td>[1, 2]</td><td>1</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备类型</td><td>-</td><td>ems</td></tr><tr><td>running_status</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td><p>运行状态</p><p>1-运行</p><p>2-离线</p><p>3-故障  </p></td><td>[1,2,3]</td><td>1</td></tr><tr><td>host</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>地址</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>端口</td><td>[0,65525]</td><td>2171</td></tr><tr><td>license</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>激活码</td><td>-</td><td>2YIZedmOtl4pcqo1EA4zhM5gofDI</td></tr></tbody></table>
*   **Payload - chargeTime**

    <table><thead><tr><th width="184">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>start_hour</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>开始小时</td><td>[0,23]</td><td>20</td></tr><tr><td>start_minute</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>开始分钟</td><td>[0,59]</td><td>0</td></tr><tr><td>end_hour</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>结束小时</td><td>[0,23]</td><td>0</td></tr><tr><td>end_minute</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>结束分钟</td><td>[0,59]</td><td>0</td></tr><tr><td>cdc_enable_mode</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电设定</td><td>0-待机,<br>1-充电,<br>2-放电</td><td>1</td></tr><tr><td>run_power</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>运行功率(单位：kW)</td><td>[0,65535]</td><td>300</td></tr></tbody></table>

    * **时间说明：**`start_hour`, `start_minute`, `end_hour`, `end_minute`组成左闭右开的时间区间
      * 如`start_hour=14`, `start_minute=15`, `end_hour=15`, `end_minute=00`表示`[14:15, 15:00)`，即14:15开始到15:00前结束。
      * 如`start_hour=20`, `start_minute=00`, `end_hour=00`, `end_minute=00`表示`[20:00, 00:00)`，即20:00开始到后一天的00:00前结束
* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{
</strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "photovoltaic_charge_list",
  "data": [{
    "id": 1
    "charge_type": 1,
    "status": 1,
    "year": 2024,
    "month": [
      1,
      7,
      8,
      11
    ],
    "dates" : [1,2],
    "mode" : 1,
    "ems_devices": [{
      "id": 1
      "name": "右206",
      "site_name": "测试站点",
      "location": "",
      "longitude": 0,
      "latitude": 0,
      "statistics_port": 1504,
      "level": 1,
      "type": "ems",
      "running_status": 1,
      "host": "192.168.77.206",
      "port": 1502,
      "license": "xxxxx"
    }],
    "apply_to_all": false,
    "settings": [
      {
        "start_hour": 20,
        "start_minute": 0,
        "end_hour": 0,
        "end_minute": 0,
        "cdc_enable_mode": 2,
        "run_power": 300
      },
      {
        "start_hour": 0,
        "start_minute": 0,
        "end_hour": 0,
        "end_minute": 0,
        "cdc_enable_mode": 21,
        "run_power": 0
      }
    ]
  },
  "device_uid": "iYRkfVpi77",
  "timestamp": 1695265371000
}
</code></pre>

## 平台请求同步光伏充放电策略

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/sync`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/sync`</mark>`/command`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_sync</td><td>photovoltaic_charge_sync</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "photovoltaic_charge_sync",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

### 同步充放电策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/sync`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/sync`</mark>`/result`
* **权限：**发布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_sync</td><td>photovoltaic_charge_sync</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data/ChargeDetail</strong></td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{
</strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "photovoltaic_charge_sync",
  "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "code": 200,
  "msg": "",
  "data": [{
    "id": 1,
    "charge_type": 1,
    "status": 1,
    "year": 2024,
    "month": [
      1,
      7,
      8,
      11
    ],
    "week_day": [
      5,
      6
    ],
    "mode":2,
    "devices": [{
      "uid": "QmqEiSCEuFNXCozS66W9y8-5",
      "name": "右206",
      "site_name": "测试站点",
      "location": "",
      "longitude": 0,
      "latitude": 0,
      "statistics_port": 1504,
      "level": 1,
      "type": "ems",
      "running_status": 1,
      "host": "192.168.77.206",
      "port": 1502,
      "license": "2YIZedmOtl4pcqo1EA4zhM5gofDI"
    }],
    "apply_to_all": false,
    "settings": [
      {
        "start_hour": 20,
        "start_minute": 0,
        "end_hour": 23,
        "end_minute": 0,
        "cdc_enable_mode": 2,
        "run_power": 300
      },
      {
        "start_hour": 0,
        "start_minute": 0,
        "end_hour": 0,
        "end_minute": 0,
        "cdc_enable_mode": 21,
        "run_power": 0
      }
    ]
  }],
  "device_uid": "iYRkfVpi77",
  "timestamp": 1695265371000
}
</code></pre>

## 下发创建充放电策略指令

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/create`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/create`</mark>`/command`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_list</td><td>photovoltaic_charge_list</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data/ChargeCreate</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data/ChargeCreate**

    <table><thead><tr><th width="158">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="7b18b87853a34308b8576531588a6c12" label="[]string" color="blue"></option><option value="BkP3aIYpA60Z" label="bool" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>charge_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电类型（后续将支持更多类型）</td><td>1-定时充放电</td><td>1</td></tr><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭,<br>1-开启</td><td>1</td></tr><tr><td>year</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>年</td><td>（若mode=1,则year为必填；)</td><td>2024</td></tr><tr><td>month</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>月份选择（0代表一月）</td><td>[0,11]</td><td>[1,7,8,11]</td></tr><tr><td>week_day</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>false</td><td>星期选择（0代表星期一）</td><td>[0,6]</td><td>[5,6]</td></tr><tr><td>dates</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>false</td><td>日期选择（0代表1日）</td><td>【0,30】</td><td>【0,1,2】</td></tr><tr><td>mode</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>模式（根据mode 参数取值不同，校验week_day或dates是否必填）</td><td>1-月日模式<br>2- 月周模式</td><td>1</td></tr><tr><td>device_ids</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>false</td><td>设备列表ID（uids、ids、apply_to_all三选一）</td><td>-</td><td>-</td></tr><tr><td>apply_to_all</td><td><span data-option="BkP3aIYpA60Z">bool</span></td><td>false</td><td>是否包括所有一级设备（uids、ids、apply_to_all三选一）</td><td>-</td><td>true</td></tr><tr><td>settings</td><td><span data-option="dc27004c92e443db924ae8f38f2ec7f1">[]chargeTime</span></td><td>true</td><td>充放电时间段</td><td>-</td><td>-</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "type": "photovoltaic_charge_create",
    "data": {
        "charge_type": 1,
        "status": 1,
        "year": 2024
        "month": [
            1,
            7,
            8,
            11
        ],
        "week_day": [
            5,
            6
        ],
        "mode":2,
        "settings": [
            {
                "start_hour": 1,
                "start_minute": 50,
                "end_hour": 23,
                "end_minute": 0,
                "cdc_enable_mode": 2,
                "run_power": 100
            }
        ],
        "device_ids": [
            1
        ],
//      "apply_to_all": true,
//        "ems_device_ids": [
//            "1"
//        ]    // ems_device_ids、ems_device_uids、apply_to_all 三选一
    },
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265371000
}
```
{% endcode %}

### 创建充放电策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/create`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/create`</mark>`/result`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_create</td><td>photovoltaic_charge_create</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>其他数据</td><td></td><td>见data</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
*   **Data**

    | 参数         | 类型  | 说明      |
    | ---------- | --- | ------- |
    | policy\_id | int | 充放电策略id |
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "photovoltaic_charge_create",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "code": 200,
    "msg": "",
    "data": {
        "policy_id": 1
    },
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

## 下发修改充放电策略指令

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update`</mark>`/command`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_update</td><td>photovoltaic_charge_update</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data/ChargeUpdate</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data/ChargeUpdate**

    <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="7b18b87853a34308b8576531588a6c12" label="[]string" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略ID</td><td>-</td><td>-</td></tr><tr><td>其余字段见<strong>Payload - data/ChargeCreate</strong></td><td></td><td>false</td><td></td><td></td><td></td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "type": "photovoltaic_charge_update",
    "data": {
        "id": 1,
        "charge_type": 1,
        "status": 1,
        "year": 2024,
        "month": [
            1,
            7,
            8,
            11
        ],
        "week_day": [
            5,
            6
        ],
        "mode":2,
        "settings": [
            {
                "start_hour": 1,
                "start_minute": 50,
                "end_hour": 23,
                "end_minute": 0,
                "cdc_enable_mode": 2,
                "run_power": 100
            }
        ],
        "device_ids": [
            1
        ]
//      "apply_to_all": true,
//        "ems_device_ids": [
//            "1"
//        ]    // ems_device_ids、ems_device_uids、apply_to_all 三选一
    },
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265371000
}
```
{% endcode %}

### 下发修改充放电策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update`</mark>`/result`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_update</td><td>photovoltaic_charge_update</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "photovoltaic_charge_update",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "code": 200,
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

## 下发删除充放电策略指令

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/delete`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/delete`</mark>`/command`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_delete</td><td>photovoltaic_charge_delete</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data**

    <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option><option value="7b18b87853a34308b8576531588a6c12" label="[]string" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电策略ID</td><td>-</td><td>1</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{
</strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "charge_delete",
  "data": {
    "id": 1,
  },
  "device_uid": "iYRkfVpi77",
  "timestamp": 1695265371000
}
</code></pre>

### 下发删除充放电策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/delete`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/delete`</mark>`/result`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_delete</td><td>photovoltaic_charge_delete</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "photovoltaic_charge_delete",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "code": 200,
    "msg": "",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

## 批量下发充放电策略指令

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update_all`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update_all`</mark>`/command`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_update_all</td><td>photovoltaic_charge_update_all</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - Data: \[]ChargeCreate**
* **Payload示例**

```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "photovoltaic_charge_update_all",
  "data": [
    {
      "charge_type": 1,
      "status": 1,
      "year": 2024,
      "month": [
        8
      ],
      "week_day": [
        6
      ],
      "mode":2,
      "apply_to_all": true,
      "settings": [
        {
          "start_hour": 1,
          "start_minute": 50,
          "end_hour": 23,
          "end_minute": 0,
          "cdc_enable_mode": 2,
          "run_power": 100
        }
      ]
    }
  ],
  "device_uid": "iYRkfVpi77",
  "timestamp": 1695265371000
}
```

### 批量下发充放电策略响应

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update_all`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_photovoltaic/update_all`</mark>`/result`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>photovoltaic_charge_update_all</td><td>photovoltaic_charge_update_all</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "d90e64f6-6c71-43e1-a755-d034bb307ee2",
    "type": "photovoltaic_charge_update_all",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1706521447074,
    "reply": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
    "code": 200,
}
```
