# 策略-安全保护

## 上报安全保护策略

* **Topic：** `${自定义前缀v1}/${DEVICE}/`<mark style="color:red;">`safety/details`</mark>`/post`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>safety_details</td><td>safety_details</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data**

    <table><thead><tr><th width="209">参数</th><th width="81">类型<select><option value="7a689ae99ed145e183989371bbcf21ce" label="int" color="blue"></option></select></th><th width="85" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>bms_3</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>BMS三级报警停机状态 0-关 1-开</td><td>[0,1]</td><td>1</td></tr><tr><td>fire_control</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>消防报警停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>0</td></tr><tr><td>flooding</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>水浸停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>aircon</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>空调掉线停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>0</td></tr><tr><td>aircon_mins</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>空调掉线停机时间</td><td>[0, ∞)</td><td>10</td></tr><tr><td>temp</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>室内温度过高停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>temp_celsius</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>室内温度过高停机温度</td><td>[0, ∞)</td><td>35</td></tr><tr><td>grounded</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>接地离线停机状态 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>grounded_mins</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>接地离线停机时间</td><td>[0, ∞)</td><td>5</td></tr><tr><td>bms_2</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>BMS二级报警降功率停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>bms_2_kw</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>BMS二级报警降功率至停机功率</td><td>[0, ∞)</td><td>100</td></tr><tr><td>meter_offline_power0</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>电表离线停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>meter_offline_mins</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>电表离线停机时间</td><td>[0, ∞)</td><td>100</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "safety_details",
  "data": {
    "bms_3": 0,
    "fire_control": 0,
    "flooding": 0,
    "aircon": 0,
    "aircon_mins": 0,
    "temp": 0,
    "temp_celsius": 0,
    "grounded": 0,
    "grounded_mins": 0,
    "bms_2": 0,
    "bms_2_kw": 0,
    "meter_offline_power0": 0,
    "meter_offline_mins": 0
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>

## 平台请求同步安全保护策略

* **Topic：** `${自定义前缀v1}/${DEVICE}/`<mark style="color:red;">`safety/sync`</mark>`/command`
* **权限：**&#x53D1;布
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>safety_sync</td><td>safety_sync</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **响应代码**

    <table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>
* **Payload示例**

```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "type": "safety_sync",
    "code": 200,
    "msg": "",
    "sub_device_uid": "${SUB_DEVICE_UID}",
    "device_uid": "${DEVICE_UID}",
    "timestamp": 1695265671000
}
```



### 同步安全保护策略响应

* **Topic：** `${自定义前缀v1}/${DEVICE}/`<mark style="color:red;">`safety/sync`</mark>`/result`
* **权限：**&#x8BA2;阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>safety_sync</td><td>safety_sync</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data**

    <table><thead><tr><th width="209">参数</th><th width="81">类型<select><option value="7a689ae99ed145e183989371bbcf21ce" label="int" color="blue"></option></select></th><th width="85" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>bms_3</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>BMS三级报警停机状态 0-关 1-开</td><td>[0,1]</td><td>1</td></tr><tr><td>fire_control</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>消防报警停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>0</td></tr><tr><td>flooding</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>水浸停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>aircon</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>空调掉线停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>0</td></tr><tr><td>aircon_mins</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>空调掉线停机时间</td><td>[0, ∞)</td><td>10</td></tr><tr><td>temp</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>室内温度过高停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>temp_celsius</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>室内温度过高停机温度</td><td>[0, ∞)</td><td>35</td></tr><tr><td>grounded</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>接地离线停机状态 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>grounded_mins</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>接地离线停机时间</td><td>[0, ∞)</td><td>5</td></tr><tr><td>bms_2</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>BMS二级报警降功率停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>bms_2_kw</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>BMS二级报警降功率至停机功率</td><td>[0, ∞)</td><td>100</td></tr><tr><td>meter_offline_power0</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td><p>电表离线停机 </p><p>0-关 </p><p>1-开</p></td><td>[0,1]</td><td>1</td></tr><tr><td>meter_offline_mins</td><td><span data-option="7a689ae99ed145e183989371bbcf21ce">int</span></td><td>true</td><td>电表离线停机时间</td><td>[0, ∞)</td><td>100</td></tr></tbody></table>
* **Payload示例**

<pre class="language-json"><code class="lang-json"><strong>{  
</strong><strong>  "trace_id": "577f5df0-65d6-432d-8aac-0116e9530152",
</strong>  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "safety_sync",
  "data": {
    "bms_3": 0,
    "fire_control": 0,
    "flooding": 0,
    "aircon": 0,
    "aircon_mins": 0,
    "temp": 0,
    "temp_celsius": 0,
    "grounded": 0,
    "grounded_mins": 0,
    "bms_2": 0,
    "bms_2_kw": 0,
    "meter_offline_power0": 0,
    "meter_offline_mins": 0
  },
  "sub_device_uid": "${SUB_DEVICE_UID}",
  "device_uid": "${DEVICE_UID}",
  "timestamp": 1695265371000
}
</code></pre>
