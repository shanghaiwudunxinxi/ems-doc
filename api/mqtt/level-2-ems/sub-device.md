# 信息-EMU设备

## 上报设备信息

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`device_info/details`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`device_info/details`</mark>`/post`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>device_info_details</td><td>device_info_details</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>sub_device_id</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>(0, ∞)</td><td>2</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="1b28025203f644c291919cb0f1184736" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="127">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td><a href="https://wudun.atlassian.net/browse/DGHDJSJKD-1?atlOrigin=eyJpIjoiYjM0MTA4MzUyYTYxNDVkY2IwMzVjOGQ3ZWQ3NzMwM2QiLCJwIjoianN3LWdpdGxhYlNNLWludCJ9">DGHDJSJKD-1</a></td></tr><tr><td>name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>ems设备</td></tr><tr><td>site_name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>ems站点</td></tr><tr><td>location</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>详细地理位置</td><td>-</td><td>wudun</td></tr><tr><td>longitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>经度</td><td>-</td><td></td></tr><tr><td>latitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>纬度</td><td></td><td></td></tr><tr><td>level</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>EMS等级</td><td>[1, 2]</td><td>1</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备类型</td><td>-</td><td>ems</td></tr><tr><td>running_status</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td><p>运行状态</p><p>1-运行</p><p>2-离线</p><p>3-故障  </p></td><td>[1,2,3]</td><td>1</td></tr><tr><td>host</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>地址</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>端口</td><td>[0,65525]</td><td>2171</td></tr><tr><td>license</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>激活码</td><td>-</td><td>2YIZedmOtl4pcqo1EA4zhM5gofDI</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{  
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "device_info_details",
  "data": {
      "uid": "${DEVICE_UID}",
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
      "license": "2YIZedmOtl4pcqo1EA4zhM5gofDI",
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "sub_device_id": 2,
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>

## 平台请求同步设备信息

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`device_info/sync`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`device_info/sync`</mark>`/command`
* **权限：**发布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>device_info_sync</td><td>device_info_sync</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "device_info_sync",
    "sub_device_uid": "${SUB_DEVICE_UID}",
    "device_uid": "${DEVICE_UID}",
    "timestamp": 1695265671000
}
```

### 同步设备信息响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`device_info/sync`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`device_info/sync`</mark>`/result`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>device_info_sync</td><td>device_info_sync</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="1b28025203f644c291919cb0f1184736" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="127">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td><a href="https://wudun.atlassian.net/browse/DGHDJSJKD-1?atlOrigin=eyJpIjoiYjM0MTA4MzUyYTYxNDVkY2IwMzVjOGQ3ZWQ3NzMwM2QiLCJwIjoianN3LWdpdGxhYlNNLWludCJ9">DGHDJSJKD-1</a></td></tr><tr><td>name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>ems设备</td></tr><tr><td>site_name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>ems站点</td></tr><tr><td>location</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>详细地理位置</td><td>-</td><td>wudun</td></tr><tr><td>longitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>经度</td><td>-</td><td></td></tr><tr><td>latitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>纬度</td><td>-</td><td></td></tr><tr><td>level</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>EMS等级</td><td>[1, 2]</td><td>1</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备类型</td><td>-</td><td>ems</td></tr><tr><td>running_status</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td><p>运行状态</p><p>1-运行</p><p>2-离线</p><p>3-故障  </p></td><td>[1,2,3]</td><td>1</td></tr><tr><td>host</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>地址</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>端口</td><td>[0,65525]</td><td>2171</td></tr><tr><td>license</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>激活码</td><td>-</td><td>2YIZedmOtl4pcqo1EA4zhM5gofDI</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json"><code class="lang-json"><strong>{  
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "device_info_sync",
  "data": {
      "uid": "${DEVICE_UID}",
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
      "license": "2YIZedmOtl4pcqo1EA4zhM5gofDI",
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>

## 平台请求同步设备信息列表

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`device_info/list`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`device_info/list`</mark>`/command`
* **权限：**发布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>device_info_list</td><td>device_info_list</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "device_info_list",
    "code": 200,
    "msg": "",
    "sub_device_uid": "${SUB_DEVICE_UID}",
    "device_uid": "${DEVICE_UID}",
    "timestamp": 1695265671000
}
```

### 同步设备信息响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`device_info/list`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`device_info/list`</mark>`/result`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>device_info_list</td><td>device_info_list</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="1b28025203f644c291919cb0f1184736" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="127">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td><a href="https://wudun.atlassian.net/browse/DGHDJSJKD-1?atlOrigin=eyJpIjoiYjM0MTA4MzUyYTYxNDVkY2IwMzVjOGQ3ZWQ3NzMwM2QiLCJwIjoianN3LWdpdGxhYlNNLWludCJ9">DGHDJSJKD-1</a></td></tr><tr><td>name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>ems设备</td></tr><tr><td>site_name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>ems站点</td></tr><tr><td>location</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>详细地理位置</td><td>-</td><td>wudun</td></tr><tr><td>longitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>经度</td><td>-</td><td></td></tr><tr><td>latitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>纬度</td><td>-</td><td></td></tr><tr><td>level</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>EMS等级</td><td>[1, 2]</td><td>1</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备类型</td><td>-</td><td>ems</td></tr><tr><td>running_status</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td><p>运行状态</p><p>1-运行</p><p>2-离线</p><p>3-故障  </p></td><td>[1,2,3]</td><td>1</td></tr><tr><td>host</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>地址</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>端口</td><td>[0,65525]</td><td>2171</td></tr><tr><td>license</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>激活码</td><td>-</td><td>2YIZedmOtl4pcqo1EA4zhM5gofDI</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json"><code class="lang-json"><strong>{  
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "device_info_list",
  "data": [{
      "uid": "${DEVICE_UID}",
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
      "license": "2YIZedmOtl4pcqo1EA4zhM5gofDI",
  }],
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>
