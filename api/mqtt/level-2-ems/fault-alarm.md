# 故障告警

## 上报故障告警

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`alarm/details`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`alarm/details`</mark>`/post`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>alarm_details</td><td>alarm_details</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>sub_device_id</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>(0, ∞)</td><td>1</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data/AlarmData**

    <table><thead><tr><th width="209">参数</th><th width="81">类型</th><th width="85" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>id</td><td>int</td><td>true</td><td>告警id</td><td>(0, ∞)</td><td>10</td></tr><tr><td>content</td><td>str</td><td>true</td><td>故障/告警内容</td><td></td><td>不控整流告警</td></tr><tr><td>device_type</td><td>str</td><td>true</td><td>发生设备设备类型</td><td>PCS、BMS</td><td>PCS</td></tr><tr><td>alarm_type</td><td>str</td><td>true</td><td>上报设备类型</td><td>ems</td><td>ems</td></tr><tr><td>level</td><td>int</td><td>true</td><td>告警等级</td><td>[1,3]</td><td>1</td></tr><tr><td>handle_status</td><td>int</td><td>true</td><td>状态</td><td>1-新增，2-已处理</td><td>2</td></tr><tr><td>handle_type</td><td>int</td><td>false</td><td>处理方式</td><td>1-系统自动处理，2-用户手动处理</td><td>2</td></tr><tr><td>user_id</td><td>int</td><td>false</td><td>处理的用户ID</td><td></td><td>1</td></tr><tr><td>occur_time</td><td>str</td><td>true</td><td>告警发生时间</td><td></td><td>2024-01-24 18:15:25.317133+08:00</td></tr><tr><td>handle_time</td><td>str</td><td>false</td><td>告警处理时间</td><td></td><td>2024-01-24 18:15:25.317133+08:00</td></tr></tbody></table>
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "safety_details",
  "data": {
    "content": "不控整流告警",
    "device_type": "PCS",
    "alarm_type": "ems",
    "level": 1,
    "handle_status": 2,
    "handle_type": 2,
    "user_id": 1,
    "occur_time": "2024-01-24 18:15:25.317133+08:00",
    "handle_time": "2024-01-24 18:15:25.317133+08:00"
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "sub_device_id": "${SUB_DEVICE_ID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
```
{% endcode %}
