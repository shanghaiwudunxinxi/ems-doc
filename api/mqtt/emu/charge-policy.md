---
description: 一级EMS
---

# 充放电策略

## \[Deprecated] 下发充放电策略

* **Topic：**`v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge/setting`</mark>`/command`
* **权限：**&#x53D1;布
* **Payload主结构**

<table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>charge_setting</td><td>charge_setting</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备ID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **Payload - data**

<table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>charge_type</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电类型（后续将支持更多类型）</td><td>1-定时充放电</td><td>1</td></tr><tr><td>status</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>策略开关</td><td>0-关闭,<br>1-开启</td><td>1</td></tr><tr><td>month</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>月份选择（0代表一月）</td><td>[0,11]</td><td>[1,7,8,11]</td></tr><tr><td>week_day</td><td><span data-option="788ee30047d74e5fadefda8ae2c6b579">[]int</span></td><td>true</td><td>星期选择（0代表星期一）</td><td>[0,6]</td><td>[5,6]</td></tr><tr><td>settings</td><td><span data-option="dc27004c92e443db924ae8f38f2ec7f1">[]chargeTime</span></td><td>true</td><td>充放电时间段</td><td>-</td><td>-</td></tr></tbody></table>

* **Payload - chargeTime**

<table><thead><tr><th width="173">参数</th><th width="122">类型<select><option value="7d4bdb9b9c74432db026fc1a42c657f8" label="int" color="blue"></option><option value="788ee30047d74e5fadefda8ae2c6b579" label="[]int" color="blue"></option><option value="dc27004c92e443db924ae8f38f2ec7f1" label="[]chargeTime" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>start_hour</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>开始小时</td><td>[0,23]</td><td>20</td></tr><tr><td>start_minute</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>开始分钟</td><td>[0,59]</td><td>0</td></tr><tr><td>end_hour</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>结束小时</td><td>[0,23]</td><td>23</td></tr><tr><td>end_minute</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>结束分钟</td><td>[0,59]</td><td>0</td></tr><tr><td>cdc_enable_mode</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>充放电设定</td><td>0-待机,<br>1-充电,<br>2-放电</td><td>1</td></tr><tr><td>run_power</td><td><span data-option="7d4bdb9b9c74432db026fc1a42c657f8">int</span></td><td>true</td><td>运行功率(单位：kW)</td><td>[0,65535]</td><td>300</td></tr></tbody></table>

* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{
</strong>  "mid": "3e681859-6917-4b9a-9afd-3f162cd185bd",
  "type": "charge_setting",
  "data": {
    "charge_type": 1,
    "status": 1,
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
  },
  "device_uid": "iYRkfVpi77",
  "timestamp": 1695265371000
}
</code></pre>

## \[Deprecated] 充放电策略响应

* **Topic：**`v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`charge/setting`</mark>`/result`
* **权限：**&#x8BA2;阅
* **Payload主结构**

<table><thead><tr><th width="173">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>4c5b3c27-cea8-4ea1-a936-41fd3596e0e9</td></tr><tr><td>reply</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>所回复消息的mid</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>charge_setting</td><td>charge_setting</td></tr><tr><td>code</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>响应代码</td><td>-</td><td>见响应代码</td></tr><tr><td>msg</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>失败原因</td><td>-</td><td>参数错误</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备ID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **响应代码**

<table><thead><tr><th>错误码<select><option value="271841fe398248e2ad777dd883d4754c" label="400" color="blue"></option><option value="3c1ae8fc6fe644f78b5f6b6f889f7621" label="200" color="blue"></option></select></th><th>描述</th><th>说明</th></tr></thead><tbody><tr><td><span data-option="3c1ae8fc6fe644f78b5f6b6f889f7621">200</span></td><td>下发成功</td><td></td></tr><tr><td><span data-option="271841fe398248e2ad777dd883d4754c">400</span></td><td>参数有误</td><td></td></tr></tbody></table>

* **Payload示例**

```json
{
    "mid": "4c5b3c27-cea8-4ea1-a936-41fd3596e0e9",
    "reply": "3e681859-6917-4b9a-9afd-3f162cd185bd",
    "type": "charge_setting",
    "code": 200,
    "msg": "",
    "device_uid": "iYRkfVpi77",
    "timestamp": 1695265671000
}
```
