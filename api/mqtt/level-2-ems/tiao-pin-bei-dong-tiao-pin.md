# 调频-被动调频

## 上报被动调频信息

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`grid_fm/receive`</mark>`/post`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`grid_fm/receive`</mark>`/post`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173" align="center">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="98">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td align="center">mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td align="center">type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>grid_fm_receive</td><td>grid_fm_receive</td></tr><tr><td align="center">data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td align="center">sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>子设备UID，仅二级替单个子设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td align="center">sub_device_id</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>false</td><td>子设备ID，仅二级替单个子设备上报时需要该字段</td><td>(0, ∞)</td><td>2</td></tr><tr><td align="center">device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备ID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td align="center">timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

### **Payload - data**

<table><thead><tr><th width="173" align="center">参数</th><th width="80">类型<select><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="cgvge610ZB6t" label="float" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th width="98">描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td align="center">type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>指令类型</td><td>status-启停状态<br>power-功率</td><td>power</td></tr><tr><td align="center">value</td><td><span data-option="cgvge610ZB6t">float</span></td><td>true</td><td>指令内容</td><td><ul><li><p>对于status</p><ul><li>0-停机</li><li>1-启动</li></ul></li><li><p>对于power</p><ul><li>单位：kw</li><li>正充负放</li></ul></li></ul></td><td>100.5</td></tr><tr><td align="center">receive_time</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>接收到调频指令的时间（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **Payload示例**

```json
{
  "mid": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "grid_fm_receive",
  "data": {
    "type": "power",
    "value": 100.5,
    "receive_time": 1696837112000
  },
  "sub_device_id": 2,
  "device_uid": "iYRkfVpi77",
  "timestamp": 1696837112000
}
```

