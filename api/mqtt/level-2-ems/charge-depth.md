# 放电深度保策略

## 上报放电深度保护策略

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_percentage/details`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_percentage/details`</mark>`/post`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>charge_percentage_details</td><td>charge_percentage_details</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data**

    <table><thead><tr><th>参数</th><th width="130">类型<select><option value="bb43c884142f4569b3ec2e9619564912" label="int" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th>样例</th></tr></thead><tbody><tr><td>charge_depth</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>充电保护深度SOC 0-100</td><td>80</td></tr><tr><td>charge_slow</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓充电SOC 0-100</td><td>30</td></tr><tr><td>charge_pcs</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓充电PCS输出 0-100</td><td>40</td></tr><tr><td>discharge_depth</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>放电保护深度SOC 0-100</td><td>20</td></tr><tr><td>discharge_slow</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓放电SOC 0-100</td><td>10</td></tr><tr><td>discharge_pcs</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓放电PCS输出 0-100</td><td>15</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "charge_percentage_details",
  "data": {
    "charge_depth": 0,
    "charge_slow": 0,
    "charge_pcs": 0,
    "discharge_depth": 0,
    "discharge_slow": 0,
    "discharge_pcs": 0
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>

## 平台请求同步放电深度保护策略

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`charge_percentage/sync`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge_percentage/sync`</mark>`/command`
* **权限：**发布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>charge_percentage_sync</td><td>charge_percentage_sync</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备ID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "charge_percentage_sync",
    "code": 200,
    "msg": "",
    "sub_device_uid": "${SUB_DEVICE_UID}",
    "device_uid": "${DEVICE_UID}",
    "timestamp": 1695265671000
}
```



## 同步放电深度保护策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`device_info/sync`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`device_info/sync`</mark>`/result`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>charge_percentage_sync</td><td>charge_percentage_sync</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

**Payload - data**

<table><thead><tr><th>参数</th><th width="130">类型<select><option value="bb43c884142f4569b3ec2e9619564912" label="int" color="blue"></option></select></th><th data-type="checkbox">是否必填</th><th>描述</th><th>样例</th></tr></thead><tbody><tr><td>charge_depth</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>充电保护深度SOC 0-100</td><td>80</td></tr><tr><td>charge_slow</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓充电SOC 0-100</td><td>30</td></tr><tr><td>charge_pcs</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓充电PCS输出 0-100</td><td>40</td></tr><tr><td>discharge_depth</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>放电保护深度SOC 0-100</td><td>20</td></tr><tr><td>discharge_slow</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓放电SOC 0-100</td><td>10</td></tr><tr><td>discharge_pcs</td><td><span data-option="bb43c884142f4569b3ec2e9619564912">int</span></td><td>true</td><td>开始减缓放电PCS输出 0-100</td><td>15</td></tr></tbody></table>

**Payload示例**

<pre class="language-json"><code class="lang-json"><strong>{  
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "charge_percentage_sync",
  "data": {
    "charge_depth": 0,
    "charge_slow": 0,
    "charge_pcs": 0,
    "discharge_depth": 0,
    "discharge_slow": 0,
    "discharge_pcs": 0
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>
