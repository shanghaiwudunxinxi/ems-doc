# 支路设计

## 上报支路设计

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`power_node/list`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`power_node/list`</mark>`/post`
* **权限：**上报
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="66" data-type="checkbox">是否必填</th><th width="148">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_list</td><td>streaming_overdemand_list</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data**

<table><thead><tr><th width="162">参数</th><th width="170">类型<select><option value="57a23d84e69e4a169a3e7ad9429a889e" label="str" color="blue"></option><option value="ee99c4f6e6af4d28857280add3137f3b" label="int" color="blue"></option><option value="9f304e2bd34c4d9680fe5edbc719d1ad" label="eleMeter/emsDevice" color="blue"></option><option value="9e6b65df2ed64abdb9721cf1f5b18101" label="[]powerNode" color="blue"></option></select></th><th width="109" data-type="checkbox">是否必填</th><th>描述</th><th></th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>ID</td><td>-</td><td>1</td></tr><tr><td>name</td><td><span data-option="57a23d84e69e4a169a3e7ad9429a889e">str</span></td><td>true</td><td>支路名称</td><td>-</td><td>电表1</td></tr><tr><td>type</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>设备类型 1-电表设备 2-EMS设备</td><td>[1,2]</td><td>1</td></tr><tr><td>device</td><td><span data-option="9f304e2bd34c4d9680fe5edbc719d1ad">eleMeter/emsDevice</span></td><td>true</td><td>设备详情</td><td>-</td><td>-</td></tr><tr><td>parent_id</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>父节点ID</td><td>-</td><td>0</td></tr><tr><td>path</td><td><span data-option="57a23d84e69e4a169a3e7ad9429a889e">str</span></td><td>true</td><td>路径</td><td>-</td><td>-0-</td></tr><tr><td>running_status</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>运行状态 1-运行 2-离线 3-故障</td><td>[1,2,3]</td><td>1</td></tr><tr><td>children</td><td><span data-option="9e6b65df2ed64abdb9721cf1f5b18101">[]powerNode</span></td><td>true</td><td>子节点</td><td>-</td><td>-</td></tr></tbody></table>

*   **Payload - emsDevice**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="1b28025203f644c291919cb0f1184736" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="127">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td><a href="https://wudun.atlassian.net/browse/DGHDJSJKD-1?atlOrigin=eyJpIjoiYjM0MTA4MzUyYTYxNDVkY2IwMzVjOGQ3ZWQ3NzMwM2QiLCJwIjoianN3LWdpdGxhYlNNLWludCJ9">DGHDJSJKD-1</a></td></tr><tr><td>name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>ems设备</td></tr><tr><td>site_name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>ems站点</td></tr><tr><td>location</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>详细地理位置</td><td>-</td><td>wudun</td></tr><tr><td>longitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>经度</td><td>-</td><td>-</td></tr><tr><td>latitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>纬度</td><td></td><td>-</td></tr><tr><td>level</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>EMS等级</td><td>[1, 2]</td><td>1</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备类型</td><td>-</td><td>ems</td></tr><tr><td>running_status</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td><p>运行状态</p><p>1-运行</p><p>2-离线</p><p>3-故障  </p></td><td>[1,2,3]</td><td>1</td></tr><tr><td>host</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>地址</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>端口</td><td>[0,65525]</td><td>2171</td></tr><tr><td>license</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>激活码</td><td>-</td><td>2YIZedmOtl4pcqo1EA4zhM5gofDI</td></tr></tbody></table>
*   **Payload - eleMeter**

    <table><thead><tr><th>参数</th><th>类型<select><option value="189c0f712e0145f3801c3c40216e2394" label="str" color="blue"></option><option value="71af255091334a68af25411f3ed74398" label="int" color="blue"></option><option value="89e5a91ee2ff4c88baa2bbeee785568c" label="eleDeviceType" color="blue"></option></select></th><th width="90" data-type="checkbox">是否必填</th><th>描述</th><th></th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>电表UID</td><td>-</td><td>QmqEhterhgrzS66grew-1</td></tr><tr><td>station_name</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>站点1</td></tr><tr><td>port</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td>端口</td><td>[0,65535]</td><td>1</td></tr><tr><td>name</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>东区变压器</td></tr><tr><td>rate</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td>倍率</td><td>(0, ∞)</td><td>100</td></tr><tr><td>running_status</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td><p>运行状态</p><p>1-在线 </p><p>2-离线 </p></td><td>[1,2] </td><td>1</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_list",
  "data": [{
    "id": 1,          
    "name": "总电表",
    "type": 1,
    "device": {
      "uid": "QmqEhterhgrzS66grew-1",
      "station_name": "",
      "port": 1,
      "com_addr": "/dev/ttyS9",
      "slave_id": 1,
      "name": "总电表",
      "running_status": 2,
      "direction": -1,
      "rate": 100
    },
    "parent_id": 0,
    "path": "-0-",
    "running_status": 0,
    "children": null
  },{
    "id": 2,
    "name": "左电表",
    "type": 1,
    "device": {
      "uid": "QmqEhterhgrzS66grew-2",
      "station_name": "",
      "port": 2,
      "com_addr": "/dev/ttyS5",
      "slave_id": 1,
      "name": "左电表",
      "running_status": 2,
      "direction": 1,
      "rate": 20
    },
    "parent_id": 1,
    "path": "-0-1-",
    "running_status": 0,
    "children": null
  },{
    "id": 3,
    "name": "设备204",
    "type": 2,
    "device": {
      "uid": "QmqEiSCEuFNXCozS66W9y8-5",
      "name": "设备204",
      "site_name": "测试站点",
      "location": "",
      "longitude": 0,
      "latitude": 0,
      "level": 1,
      "charges": null,
      "license": "",
      "type": "",
      "running_status": 2,
      "host": "192.168.77.204",
      "port": 1502
    },
    "parent_id": 2,
    "path": "-0-1-2-",
    "running_status": 0,
    "children": null
  }],
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}

## 平台请求同步支路设计

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`power_node/sync`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`power_node/sync`</mark>`/command`
* **权限：**发布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_sync</td><td>streaming_overdemand_sync</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "streaming_overdemand_sync",
    "code": 200,
    "msg": "",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

## 同步支路设计响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`power_node/sync`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`power_node/sync`</mark>`/result`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_sync</td><td>streaming_overdemand_sync</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data**

<table><thead><tr><th width="162">参数</th><th width="170">类型<select><option value="57a23d84e69e4a169a3e7ad9429a889e" label="str" color="blue"></option><option value="ee99c4f6e6af4d28857280add3137f3b" label="int" color="blue"></option><option value="9f304e2bd34c4d9680fe5edbc719d1ad" label="emsMeter/emsDevice" color="blue"></option><option value="9e6b65df2ed64abdb9721cf1f5b18101" label="[]powerNode" color="blue"></option></select></th><th width="109" data-type="checkbox">是否必填</th><th>描述</th><th></th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>ID</td><td>-</td><td>1</td></tr><tr><td>name</td><td><span data-option="57a23d84e69e4a169a3e7ad9429a889e">str</span></td><td>true</td><td>支路名称</td><td>-</td><td>电表1</td></tr><tr><td>type</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>设备类型 1-电表设备 2-EMS设备</td><td>[1,2]</td><td>1</td></tr><tr><td>device</td><td><span data-option="9f304e2bd34c4d9680fe5edbc719d1ad">emsMeter/emsDevice</span></td><td>true</td><td>设备详情</td><td>-</td><td>-</td></tr><tr><td>parent_id</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>父节点ID</td><td>-</td><td>0</td></tr><tr><td>path</td><td><span data-option="57a23d84e69e4a169a3e7ad9429a889e">str</span></td><td>true</td><td>路径</td><td>-</td><td>-0-</td></tr><tr><td>running_status</td><td><span data-option="ee99c4f6e6af4d28857280add3137f3b">int</span></td><td>true</td><td>运行状态 1-运行 2-离线 3-故障</td><td>[1,3]</td><td>1</td></tr><tr><td>children</td><td><span data-option="9e6b65df2ed64abdb9721cf1f5b18101">[]powerNode</span></td><td>true</td><td>子节点</td><td>-</td><td>-</td></tr></tbody></table>

*   **Payload - emsDevice**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="1b28025203f644c291919cb0f1184736" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="127">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td><a href="https://wudun.atlassian.net/browse/DGHDJSJKD-1?atlOrigin=eyJpIjoiYjM0MTA4MzUyYTYxNDVkY2IwMzVjOGQ3ZWQ3NzMwM2QiLCJwIjoianN3LWdpdGxhYlNNLWludCJ9">DGHDJSJKD-1</a></td></tr><tr><td>name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>ems设备</td></tr><tr><td>site_name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>ems站点</td></tr><tr><td>location</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>详细地理位置</td><td>-</td><td>wudun</td></tr><tr><td>longitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>经度</td><td>-</td><td></td></tr><tr><td>latitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>纬度</td><td></td><td></td></tr><tr><td>level</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>EMS等级</td><td>[1, 2]</td><td>1</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备类型</td><td>-</td><td>ems</td></tr><tr><td>running_status</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td><p>运行状态</p><p>1-运行</p><p>2-离线</p><p>3-故障  </p></td><td>[1,2,3]</td><td>1</td></tr><tr><td>host</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>地址</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>端口</td><td>[0,65525]</td><td>2171</td></tr><tr><td>license</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>激活码</td><td>-</td><td>2YIZedmOtl4pcqo1EA4zhM5gofDI</td></tr></tbody></table>
*   **Payload - eleMeter**

    <table><thead><tr><th>参数</th><th>类型<select><option value="189c0f712e0145f3801c3c40216e2394" label="str" color="blue"></option><option value="71af255091334a68af25411f3ed74398" label="int" color="blue"></option><option value="89e5a91ee2ff4c88baa2bbeee785568c" label="eleDeviceType" color="blue"></option></select></th><th width="90" data-type="checkbox">是否必填</th><th>描述</th><th></th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>电表UID</td><td>-</td><td>QmqEhterhgrzS66grew-1</td></tr><tr><td>station_name</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>站点1</td></tr><tr><td>port</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td>端口</td><td>[0,65535]</td><td>1</td></tr><tr><td>name</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>东区变压器</td></tr><tr><td>rate</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td>倍率</td><td>(0, ∞)</td><td>100</td></tr><tr><td>running_status</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td><p>运行状态</p><p>1-在线 </p><p>2-离线 </p></td><td>[1,2] </td><td>1</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_list",
  "data": [{
    "id": 1,          
    "name": "总电表",
    "type": 1,
    "device": {
      "uid": "QmqEhterhgrzS66grew-1",
      "station_name": "",
      "port": 1,
      "com_addr": "/dev/ttyS9",
      "slave_id": 1,
      "name": "总电表",
      "running_status": 2,
      "direction": -1,
      "rate": 100
    },
    "parent_id": 0,
    "path": "-0-",
    "running_status": 0,
    "children": null
  },{
    "id": 2,
    "name": "左电表",
    "type": 1,
    "device": {
      "uid": "QmqEhterhgrzS66grew-2",
      "station_name": "",
      "port": 2,
      "com_addr": "/dev/ttyS5",
      "slave_id": 1,
      "name": "左电表",
      "running_status": 2,
      "direction": 1,
      "rate": 20
    },
    "parent_id": 1,
    "path": "-0-1-",
    "running_status": 0,
    "children": null
  },{
    "id": 3,
    "name": "设备204",
    "type": 2,
    "device": {
      "uid": "QmqEiSCEuFNXCozS66W9y8-5",
      "name": "设备204",
      "site_name": "测试站点",
      "location": "",
      "longitude": 0,
      "latitude": 0,
      "level": 1,
      "charges": null,
      "license": "",
      "type": "",
      "running_status": 2,
      "host": "192.168.77.204",
      "port": 1502
    },
    "parent_id": 2,
    "path": "-0-1-2-",
    "running_status": 0,
    "children": null
  }],
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}
