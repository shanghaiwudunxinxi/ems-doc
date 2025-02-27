# 信息-电表设备

## 上报电表设备信息

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`elemeter_info/details`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`elemeter_info/details`</mark>`/post`
* **权限：**&#x8BA2;阅
* **Payload主结构**

<table><thead><tr><th width="152">参数</th><th width="95">类型</th><th>是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td>uuid</td><td>是</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td>str</td><td>是</td><td>消息类型</td><td>elemeter_info_details</td><td>elemeter_info_details</td></tr><tr><td>data</td><td>data</td><td>是</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_id</td><td>int</td><td>是</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>1</td></tr><tr><td>device_uid</td><td>str</td><td>是</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td>int</td><td>是</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **Payload - data/eleMeter**

<table><thead><tr><th width="199">参数</th><th>类型</th><th>是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td>uint</td><td>是</td><td>ID</td><td>-</td><td>1</td></tr><tr><td>station_name</td><td>str</td><td>是</td><td>站点名称</td><td>-</td><td>丽宝广场</td></tr><tr><td>virtual_type</td><td>uint</td><td>是</td><td>虚拟类型</td><td>1-虚拟电表<br>2-真实电表</td><td>2</td></tr><tr><td>proto_type</td><td>uint</td><td>是</td><td>协议类型 </td><td><p>1-tcp</p><p>2-rtu</p></td><td>1</td></tr><tr><td>application_proto_type</td><td>uint</td><td>是</td><td>应用层协议类型</td><td>1-dlt645<br>2-modbus</td><td>2</td></tr><tr><td>slave_id</td><td>uint</td><td>否</td><td>设备从站id(应用层协议类型为modbus时必填)</td><td>-</td><td>1</td></tr><tr><td>dlt_addr</td><td>str</td><td>否</td><td>私有地址（应用层协议类型为1时必填）</td><td>-</td><td>AAAAAAAAAAAA</td></tr><tr><td>host</td><td>str</td><td>否</td><td>地址（传输层协议类型为2时必填）</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td>uint</td><td>否</td><td>端口（传输层协议类型为2时必填）</td><td>[0,65535]</td><td>502</td></tr><tr><td>com_addr</td><td>str</td><td>否</td><td>串口地址（传输层协议类型为1时必填</td><td>-</td><td>/dev/ttyS1</td></tr><tr><td>com_no</td><td>uint</td><td>否</td><td>串口号（传输层协议类型为1时必填</td><td>-</td><td>1</td></tr><tr><td>baud_rate</td><td>int</td><td>否</td><td>波特率（传输层协议类型为1时必填）</td><td>-</td><td>9600</td></tr><tr><td>data_bits</td><td>int</td><td>否</td><td>数据位（传输层协议类型为1时必填）</td><td>-</td><td>8</td></tr><tr><td>stop_bits</td><td>int</td><td>否</td><td>停止位（传输层协议类型为1时必填）</td><td>-</td><td>1</td></tr><tr><td>parity</td><td>string</td><td>否</td><td>校验位 （传输层协议类型为1时必填）</td><td>N:无校验<br>E:奇校验<br>O:偶校验</td><td>N</td></tr><tr><td>name</td><td>str</td><td>是</td><td>设备名称</td><td></td><td>东区变压器</td></tr><tr><td>ele_device_type_id</td><td>uint</td><td>是</td><td>电表类型id</td><td></td><td>1</td></tr><tr><td>ele_device_type</td><td>ele_device_type</td><td>是</td><td>电表类型对象</td><td></td><td></td></tr><tr><td>pt</td><td>uint</td><td>是</td><td>电压互感</td><td></td><td>10</td></tr><tr><td>ct</td><td>uint</td><td>是</td><td>电流互感</td><td></td><td>10</td></tr><tr><td>direction</td><td>int</td><td>是</td><td>电表方向</td><td></td><td></td></tr><tr><td>running_status</td><td>uint</td><td>是</td><td>运行状态</td><td></td><td>1</td></tr><tr><td>purpose</td><td>int</td><td>否</td><td>用途 </td><td>1-关口表 2-计量表</td><td>1</td></tr><tr><td>associate_meters</td><td>[]<strong>eleMeter</strong></td><td>否</td><td>关联的电表</td><td></td><td>关联自身</td></tr></tbody></table>

* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "elemeter_info_details",
  "data": {
    "id": 1,
    "proto_id": 1,
    "proto_type": 1,
    "application_proto_type": 2,
    "host": "192.168.1.2",
    "port": 502,
    "com_addr": "",
    "com_no": 0,
    "baud_rate": 9600,
    "data_bits": 8,
    "stop_bits": 1,
    "parity": "N",
    "dlt_addr": "",
    "slave_id": 1,
    "uid": "",
    "station_name": "测试站点",
    "name": "电表208",
    "virtual_type": 2,
    "ele_device_type_id": 1,
    "ele_device_type": {
      "id": 1,
      "device_type": 1,
      "name": "Acrel-ADW300"
    },
    "running_status": 1,
    "direction": 1,
    "pt": 1,
    "ct": 1,
    "purpose": 1,
    "meter_ids": null,
    "associate_meters": []
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "sub_device_id": 2,
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}

## 平台请求同步设备信息

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`elemeter_info/sync`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`elemeter_info/sync`</mark>`/command`
* **权限：**&#x53D1;布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>elemeter_info_sync</td><td>elemeter_info_sync</td></tr><tr><td>sub_device_id</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "elemeter_info_sync",
    "sub_device_id": "${SUB_DEVICE_ID}",
    "device_uid": "${DEVICE_UID}",
    "timestamp": 1695265671000
}
```

### 同步设备信息响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`elemeter_info/sync`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`elemeter_info/sync`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="152">参数</th><th width="95">类型</th><th>是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td>uuid</td><td>是</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>reply</td><td>uuid</td><td>是</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td>str</td><td>是</td><td>消息类型</td><td>elemeter_info_sync</td><td>elemeter_info_sync</td></tr><tr><td>data</td><td>data</td><td>是</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>code</td><td>int</td><td>是</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td>str</td><td>是</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>sub_device_id</td><td>int</td><td>是</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>1</td></tr><tr><td>device_uid</td><td>str</td><td>是</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td>int</td><td>是</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data/eleMeter**
* **Payload示例**

<pre class="language-json"><code class="lang-json"><strong>{  
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "elemeter_info_sync",
  "data": {
    "id": 1,
    "proto_id": 1,
    "proto_type": 1,
    "application_proto_type": 2,
    "host": "192.168.1.2",
    "port": 502,
    "com_addr": "",
    "com_no": 0,
    "baud_rate": 9600,
    "data_bits": 8,
    "stop_bits": 1,
    "parity": "N",
    "dlt_addr": "",
    "slave_id": 1,
    "uid": "",
    "station_name": "测试站点",
    "name": "电表208",
    "virtual_type": 2,
    "ele_device_type_id": 1,
    "ele_device_type": {
      "id": 1,
      "device_type": 1,
      "name": "Acrel-ADW300"
    },
    "running_status": 1,
    "direction": 1,
    "pt": 1,
    "ct": 1,
    "purpose": 1,
    "meter_ids": null,
    "associate_meters": []
  },
  "sub_device_id": "${SUB_DEVICE_ID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>

## 平台请求同步设备信息列表

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`elemeter_info/list`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`elemeter_info/list`</mark>`/command`
* **权限：**&#x53D1;布
*   **Payload主结构**

    <table><thead><tr><th width="152">参数</th><th width="95">类型</th><th>是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td>uuid</td><td>是</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td>str</td><td>是</td><td>消息类型</td><td>elemeter_info_list</td><td>elemeter_info_list</td></tr><tr><td>device_uid</td><td>str</td><td>是</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td>int</td><td>是</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "elemeter_info_list",
    "device_uid": "${DEVICE_UID}",
    "timestamp": 1695265671000
}
```

### 同步设备信息响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`elemeter_info/list`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`elemeter_info/list`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="152">参数</th><th width="95">类型</th><th>是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td>uuid</td><td>是</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>reply</td><td>uuid</td><td>是</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td>str</td><td>是</td><td>消息类型</td><td>elemeter_info_list</td><td>elemeter_info_list</td></tr><tr><td>data</td><td>data</td><td>是</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>code</td><td>int</td><td>是</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td>str</td><td>是</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>sub_device_id</td><td>int</td><td>是</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>1</td></tr><tr><td>device_uid</td><td>str</td><td>是</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td>int</td><td>是</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data/\[]eleMeter**
* **Payload示例**

<pre class="language-json"><code class="lang-json"><strong>{  
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "elemeter_info_list",
  "data": [ 
    {
      "id": 1,
      "proto_id": 1,
      "proto_type": 1,
      "application_proto_type": 2,
      "host": "192.168.1.2",
      "port": 502,
      "com_addr": "",
      "com_no": 0,
      "baud_rate": 9600,
      "data_bits": 8,
      "stop_bits": 1,
      "parity": "N",
      "dlt_addr": "",
      "slave_id": 1,
      "uid": "",
      "station_name": "测试站点",
      "name": "电表208",
      "virtual_type": 2,
      "ele_device_type_id": 1,
      "ele_device_type": {
        "id": 1,
        "device_type": 1,
        "name": "Acrel-ADW300"
      },
      "running_status": 1,
      "direction": 1,
      "pt": 1,
      "ct": 1,
      "purpose": 1,
      "meter_ids": null,
      "associate_meters": []
    },
],
  "sub_device_id": "${SUB_DEVICE_ID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>
