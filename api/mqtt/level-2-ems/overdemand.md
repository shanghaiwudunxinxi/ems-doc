# 策略-需量管理与防逆流

## 上报防逆流过需策略

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/list`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/list`</mark>`/post`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="66" data-type="checkbox">是否必填</th><th width="148">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_list</td><td>streaming_overdemand_list</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data: StreamingOverDemand**

    <table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="3b8afd5962dd4f8a84d69bb5db1e5b5f" label="eleMeter" color="blue"></option><option value="2e12ee4d54414454be1b21e731c06be5" label="[]emsDevice" color="blue"></option><option value="derQgITNQpbg" label="str" color="blue"></option><option value="LTfGbji72KqQ" label="any" color="blue"></option><option value="QuQFJKgN19ow" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>过需逆流策略ID</td><td></td><td>1</td></tr><tr><td>device_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>设备类型</td><td><p>2-储能设备 </p><p>3-光伏 </p><p>4-充电桩</p></td><td>2</td></tr><tr><td>devices</td><td><span data-option="LTfGbji72KqQ">any</span></td><td>true</td><td>设备列表</td><td>-</td><td>[]emsDevice/[]photovoltaic/[]pail</td></tr><tr><td>elemeter</td><td><span data-option="3b8afd5962dd4f8a84d69bb5db1e5b5f">eleMeter</span></td><td>true</td><td>电表</td><td>-</td><td>eleMeter</td></tr><tr><td>ele_meter_id</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>电表id</td><td></td><td>1</td></tr><tr><td>streaming_status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td><p>防逆流状态</p><p></p></td><td><p>1-启用</p><p>2-禁用</p></td><td>1</td></tr><tr><td>streaming_condition</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>防逆流执行条件（单位：kW）</td><td>-</td><td>5000</td></tr><tr><td>individual_phase_streaming_status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>单相防逆流状态</td><td><p>1-启用</p><p>2-禁用</p></td><td>2</td></tr><tr><td>individual_phase_streaming_condition</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>false</td><td>单相防逆流执行条件（单位：kW）</td><td>-</td><td>100</td></tr><tr><td>over_demand_condition</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>每月防过需执行条件（1-12月）（单位：kW）</td><td>-</td><td>[5000,6000,5000,5000,6000,5000,5000,6000,5000,5000,6000,5000]</td></tr><tr><td>over_demand_status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>防过需状态</td><td><p>1-启用</p><p>2-禁用</p></td><td>1</td></tr><tr><td>dynamic_demand</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>动态需量（单位：kW）</td><td></td><td>6000</td></tr><tr><td>dynamic_demand_percentage</td><td><span data-option="QuQFJKgN19ow">float</span></td><td>true</td><td>动态需量追峰比例</td><td></td><td>90.1</td></tr><tr><td>current_over_demand_condition</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>当前月份的过需条件（单位：kW）</td><td></td><td>2000</td></tr><tr><td>updated_by</td><td><span data-option="derQgITNQpbg">str</span></td><td>true</td><td>更新人</td><td></td><td>user: 1-admin</td></tr><tr><td>created_at</td><td><span data-option="derQgITNQpbg">str</span></td><td>true</td><td>创建时间</td><td></td><td>2024-06-06T08:59:20.21309056Z</td></tr><tr><td>updated_at</td><td><span data-option="derQgITNQpbg">str</span></td><td>true</td><td>更新时间</td><td></td><td>2024-06-06T08:59:20.21309056Z</td></tr></tbody></table>
*   **Payload - emsDevice**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="1b28025203f644c291919cb0f1184736" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="127">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td><a href="https://wudun.atlassian.net/browse/DGHDJSJKD-1?atlOrigin=eyJpIjoiYjM0MTA4MzUyYTYxNDVkY2IwMzVjOGQ3ZWQ3NzMwM2QiLCJwIjoianN3LWdpdGxhYlNNLWludCJ9">DGHDJSJKD-1</a></td></tr><tr><td>name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>ems设备</td></tr><tr><td>site_name</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>ems站点</td></tr><tr><td>location</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>详细地理位置</td><td>-</td><td>wudun</td></tr><tr><td>longitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>经度</td><td>-</td><td>-</td></tr><tr><td>latitude</td><td><span data-option="1b28025203f644c291919cb0f1184736">float</span></td><td>true</td><td>纬度</td><td></td><td>-</td></tr><tr><td>level</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>EMS等级</td><td>[1, 2]</td><td>1</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备类型</td><td>-</td><td>ems</td></tr><tr><td>running_status</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td><p>运行状态</p><p>1-运行</p><p>2-离线</p><p>3-故障</p></td><td>[1,2,3]</td><td>1</td></tr><tr><td>host</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>地址</td><td>-</td><td>192.168.0.1</td></tr><tr><td>port</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>端口</td><td>[0,65525]</td><td>2171</td></tr><tr><td>license</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>激活码</td><td>-</td><td>2YIZedmOtl4pcqo1EA4zhM5gofDI</td></tr></tbody></table>
*   **Payload - eleMeter**

    <table><thead><tr><th>参数</th><th>类型<select><option value="189c0f712e0145f3801c3c40216e2394" label="str" color="blue"></option><option value="71af255091334a68af25411f3ed74398" label="int" color="blue"></option><option value="89e5a91ee2ff4c88baa2bbeee785568c" label="eleDeviceType" color="blue"></option></select></th><th width="90" data-type="checkbox">是否必填</th><th>描述</th><th></th><th>样例</th></tr></thead><tbody><tr><td>uid</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>电表UID</td><td>-</td><td>QmqEhterhgrzS66grew-1</td></tr><tr><td>station_name</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>站点名称</td><td>-</td><td>站点1</td></tr><tr><td>port</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td>端口</td><td>[0,65535]</td><td>1</td></tr><tr><td>name</td><td><span data-option="189c0f712e0145f3801c3c40216e2394">str</span></td><td>true</td><td>设备名称</td><td>-</td><td>东区变压器</td></tr><tr><td>elec_device_type</td><td><span data-option="89e5a91ee2ff4c88baa2bbeee785568c">eleDeviceType</span></td><td>true</td><td>电表类型对象</td><td>-</td><td>-</td></tr><tr><td>rate</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td>倍率</td><td>(0, ∞)</td><td>100</td></tr><tr><td>running_status</td><td><span data-option="71af255091334a68af25411f3ed74398">int</span></td><td>true</td><td><p>运行状态</p><p>1-在线</p><p>2-离线</p></td><td>[1,2]</td><td>1</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_list",
  "data": [{
                "id": 4,
                "device_type": 2,
                "ele_meter_id": 10,
                "ele_meter": {
                    "id": 10,
                    "proto_type": 1,
                    "proto_id": 1,
                    "slave_id": 1,
                    "host": "192.168.77.94",
                    "port": 1,
                    "com_addr": "",
                    "com_no": 0,
                    "baud_rate": 0,
                    "data_bits": 0,
                    "stop_bits": 0,
                    "parity": "",
                    "uid": "",
                    "station_name": "测试站点",
                    "name": "test",
                    "ele_device_type_id": 1,
                    "ele_device_type": {
                        "id": 1,
                        "name": "Acrel-ADW300"
                    },
                    "running_status": 2,
                    "direction": 1,
                    "pt": 1,
                    "ct": 1,
                    "purpose": 1,
                    "meter_ids": null,
                    "associate_meters": null
                },
                "devices": [
                    {
                        "uid": "",
                        "name": "设备208",
                        "site_name": "测试站点",
                        "location": "",
                        "longitude": 0,
                        "latitude": 0,
                        "statistics_port": 1504,
                        "cooling_method": 1,
                        "level": 1,
                        "charges": null,
                        "pcs_reboot": 0,
                        "bms_reboot": 0,
                        "license": "00000011",
                        "type": "Linux",
                        "running_status": 1,
                        "id": 3,
                        "proto_type": 1,
                        "proto_id": 0,
                        "slave_id": 1,
                        "host": "192.168.77.208",
                        "port": 1502,
                        "com_addr": "",
                        "com_no": 0,
                        "baud_rate": 0,
                        "data_bits": 0,
                        "stop_bits": 0,
                        "parity": "",
                        "created_at": "2024-04-24T02:11:01.16135116Z",
                        "updated_at": "2024-06-07T07:32:32.1991944Z"
                    },
                    {
                        "uid": "",
                        "name": "设备210",
                        "site_name": "测试站点",
                        "location": "",
                        "longitude": 0,
                        "latitude": 0,
                        "statistics_port": 1504,
                        "cooling_method": 1,
                        "level": 1,
                        "charges": null,
                        "pcs_reboot": 1,
                        "bms_reboot": 0,
                        "license": "",
                        "type": "",
                        "running_status": 1,
                        "id": 4,
                        "proto_type": 1,
                        "proto_id": 0,
                        "slave_id": 1,
                        "host": "192.168.77.210",
                        "port": 1502,
                        "com_addr": "",
                        "com_no": 0,
                        "baud_rate": 0,
                        "data_bits": 0,
                        "stop_bits": 0,
                        "parity": "",
                        "created_at": "2024-05-08T02:03:48.4397178Z",
                        "updated_at": "2024-06-07T07:32:32.2174462Z"
                    }
                ],
                "over_demand_status": 1,
                "over_demand_condition": [
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000
                ],
                "current_over_demand_condition": 2000,
                "dynamic_demand_status": 1,
                "dynamic_demand": 0,
                "dynamic_demand_percentage": 60,
                "streaming_status": 1,
                "streaming_condition": 2000,
                "individual_phase_streaming_status": 2,
                "individual_phase_streaming_condition": 100,
                "created_at": "2024-06-06T08:59:20.21309056Z",
                "updated_at": "2024-06-06T08:59:20.21309056Z",
                "updated_by": "user: 1-admin"
            }],
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}

## 平台请求同步防逆流过需策略

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/sync`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/sync`</mark>`/command`
* **权限：**&#x53D1;布
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

### 同步防逆流过需电策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/sync`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/sync`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="07hC15jimtTO" label="[]StreamingOverDemand" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_sync</td><td>streaming_overdemand_sync</td></tr><tr><td>data</td><td><span data-option="07hC15jimtTO">[]StreamingOverDemand</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - StreamingOverDemand</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_sync",
  "data": [{
                "id": 4,
                "ele_meter_id": 10,
                "ele_meter": {
                    "id": 10,
                    "proto_type": 1,
                    "proto_id": 1,
                    "slave_id": 1,
                    "host": "192.168.77.94",
                    "port": 1,
                    "com_addr": "",
                    "com_no": 0,
                    "baud_rate": 0,
                    "data_bits": 0,
                    "stop_bits": 0,
                    "parity": "",
                    "uid": "",
                    "station_name": "测试站点",
                    "name": "test",
                    "ele_device_type_id": 1,
                    "ele_device_type": {
                        "id": 1,
                        "name": "Acrel-ADW300"
                    },
                    "running_status": 2,
                    "direction": 1,
                    "pt": 1,
                    "ct": 1,
                    "purpose": 1,
                    "meter_ids": null,
                    "associate_meters": null
                },
                "devices": [
                    {
                        "uid": "",
                        "name": "设备208",
                        "site_name": "测试站点",
                        "location": "",
                        "longitude": 0,
                        "latitude": 0,
                        "statistics_port": 1504,
                        "cooling_method": 1,
                        "level": 1,
                        "charges": null,
                        "pcs_reboot": 0,
                        "bms_reboot": 0,
                        "license": "00000011",
                        "type": "Linux",
                        "running_status": 1,
                        "id": 3,
                        "proto_type": 1,
                        "proto_id": 0,
                        "slave_id": 1,
                        "host": "192.168.77.208",
                        "port": 1502,
                        "com_addr": "",
                        "com_no": 0,
                        "baud_rate": 0,
                        "data_bits": 0,
                        "stop_bits": 0,
                        "parity": "",
                        "created_at": "2024-04-24T02:11:01.16135116Z",
                        "updated_at": "2024-06-07T07:32:32.1991944Z"
                    },
                    {
                        "uid": "",
                        "name": "设备210",
                        "site_name": "测试站点",
                        "location": "",
                        "longitude": 0,
                        "latitude": 0,
                        "statistics_port": 1504,
                        "cooling_method": 1,
                        "level": 1,
                        "charges": null,
                        "pcs_reboot": 1,
                        "bms_reboot": 0,
                        "license": "",
                        "type": "",
                        "running_status": 1,
                        "id": 4,
                        "proto_type": 1,
                        "proto_id": 0,
                        "slave_id": 1,
                        "host": "192.168.77.210",
                        "port": 1502,
                        "com_addr": "",
                        "com_no": 0,
                        "baud_rate": 0,
                        "data_bits": 0,
                        "stop_bits": 0,
                        "parity": "",
                        "created_at": "2024-05-08T02:03:48.4397178Z",
                        "updated_at": "2024-06-07T07:32:32.2174462Z"
                    }
                ],
                "over_demand_status": 1,
                "over_demand_condition": [
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000,
                    2000
                ],
                "current_over_demand_condition": 2000,
                "dynamic_demand_status": 1,
                "dynamic_demand": 0,
                "dynamic_demand_percentage": 60,
                "streaming_status": 1,
                "streaming_condition": 2000,
                "created_at": "2024-06-06T08:59:20.21309056Z",
                "updated_at": "2024-06-06T08:59:20.21309056Z",
                "updated_by": "user: 1-admin"
            }],
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}

## 下发创建防逆流过需电策略指令

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/create`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/create`</mark>`/command`
* **权限：**&#x53D1;布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="gezpP3Z54Brz" label="StreamingOverDemand" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_create</td><td>streaming_overdemand_create</td></tr><tr><td>data</td><td><span data-option="gezpP3Z54Brz">StreamingOverDemand</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - StreamingOverDemand</strong> </td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_create",
  "data": {
        "over_demand_status": 1,
        "streaming_status": 1,
        "dynamic_demand_status": 1,
        "over_demand_condition": [
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000
        ],
        "ele_meter_id": 9,
        "dynamic_demand_percentage": 80,
        "streaming_condition": 1000,
        "individual_phase_streaming_status": 2,
        "individual_phase_streaming_condition": 100,
  },
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}

### 创建防过需防逆流策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/create`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/create`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_create</td><td>streaming_overdemand_create</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>Data</td><td></td><td>见Data</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Data**

    | 参数 | 类型  | 说明        |
    | -- | --- | --------- |
    | id | int | 防过需逆流策略id |
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功 </td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "streaming_overdemand_create",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "code": 200,
    "data": {
        "id": 1
    },
    "msg": "",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

## 下发更新防逆流过需电策略指令

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update`</mark>`/command`
* **权限：**&#x53D1;布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="eQREWS2HafA7" label="StreamingOverDemand" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_update</td><td>streaming_overdemand_update</td></tr><tr><td>data</td><td><span data-option="eQREWS2HafA7">StreamingOverDemand</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload -</strong> StreamingOverDemand</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_update",
  "data": {
        "id": 1,
        "over_demand_status": 1,
        "streaming_status": 1,
        "dynamic_demand_status": 1,
        "over_demand_condition": [
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000
        ],
        "ele_meter_id": 9,
        "dynamic_demand_percentage": 80,
        "streaming_condition": 1000,
        "individual_phase_streaming_status": 2,
        "individual_phase_streaming_condition": 100,
  },
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}

### 更新防过需防逆流策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_update</td><td>streaming_overdemand_update</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "streaming_overdemand_update",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "code": 200,
    "msg": "",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

## 下发删除防逆流过需电策略指令

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/delete`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/delete`</mark>`/command`
* **权限：**&#x53D1;布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_delete</td><td>streaming_overdemand_delete</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - Data**



    | 参数 | 类型  | 是否必填 | 描述         | 样例 |
    | -- | --- | ---- | ---------- | -- |
    | id | int | 是    | 防过需防逆流策略ID | 1  |
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_delete",
  "data": {
    "id": 1,                   
  },
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}

### 删除防过需防逆流策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/delete`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/delete`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_delete</td><td>streaming_overdemand_delete</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "streaming_overdemand_delete",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "code": 200,
    "msg": "",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```

## 批量下发创建防逆流过需电策略指令

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update_all`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update_all`</mark>`/command`
* **权限：**&#x53D1;布
*   **Payload主结构**



    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option><option value="gezpP3Z54Brz" label="[]StreamingOverDemand" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_update_all</td><td>streaming_overdemand_update_all</td></tr><tr><td>data</td><td><span data-option="gezpP3Z54Brz">[]StreamingOverDemand</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - StreamingOverDemand</strong> </td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload示例**

```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "streaming_overdemand_update_all",
  "data": [
     {
        "device_type": 2,
        "over_demand_status": 1,
        "streaming_status": 1,
        "dynamic_demand_status": 1,
        "over_demand_condition": [
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000,
          2000
        ],
        "ele_meter_id": 9,
        "dynamic_demand_percentage": 80,
        "streaming_condition": 1000,
        "individual_phase_streaming_status": 2,
        "individual_phase_streaming_condition": 100,
    }
  ],
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```

### 批量创建防过需防逆流策略响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update_all`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`streaming_overdemand/update_all`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**



    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>streaming_overdemand_update_all</td><td>streaming_overdemand_update_all</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>（二级）设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功 </td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "streaming_overdemand_update_all",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "code": 200,
    "msg": "",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```
