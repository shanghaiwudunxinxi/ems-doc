---
description: EMUOTA
---

# \[未上线]OTA-EMU

## 请求EMU版本信息

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/emu_version`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/emu_version`</mark>`/command`
* **权限：发布**
*   **Payload主结构**

    <table><thead><tr><th width="154">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th width="131">范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>emu_version</td><td>emu_version</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data 无**
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-06hjkgfg2",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "emu_version",
  "device_uid": "test",
  "sub_device_id": 2,
  "timestamp": 1697789021000
}
```
{% endcode %}



### EMU版本信息响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/emu_version`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/emu_version`</mark>`/result`
* **权限：**订阅
* **Payload主结构**

<table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>emu_version</td><td>emu_version</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_id</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>2</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **Payload - data \[]**EMUVersion
* EMUVersion

<table><thead><tr><th width="159">参数</th><th width="93">类型</th><th width="99">是否必填</th><th width="255">描述</th><th>样例</th></tr></thead><tbody><tr><td>device_id</td><td>int</td><td>是</td><td>升级设备ID</td><td>2</td></tr><tr><td>status</td><td>int</td><td>是</td><td><p>设备状态</p><p>1-运行</p><p>2-离线</p><p>3-故障</p></td><td>1</td></tr><tr><td>emu_upgrade_success</td><td>int</td><td>否</td><td><p>EMU升级成功</p><p>0-有错误 </p><p>1-全部升级成功</p></td><td>1</td></tr><tr><td>emu_upgrade_device</td><td>int</td><td>否</td><td><p>EMU升级设备</p><p>3:EMU </p><p>21:通讯板卡1 </p><p>22:通讯板2 </p><p>23:通讯板3 </p><p>24:通讯板4 </p><p>25:通讯板5 </p><p>26:通讯板6</p></td><td>3</td></tr><tr><td>emu_upgrade_status</td><td>int</td><td>否</td><td><p>EMU升级状态 </p><p>1:升级准备 </p><p>2:传输准备 </p><p>3:传输状态 </p><p>4:校验状态 </p><p>5:完成状态</p></td><td>5</td></tr><tr><td>emu_upgrade_content</td><td>int</td><td>否</td><td>升级内容 传输状态:对应文件传输进度</td><td>100</td></tr><tr><td>emu_product_sn</td><td>string</td><td>否</td><td>EMU产品SN码</td><td>emu-v1.0.0</td></tr></tbody></table>

* **Payload示例**

<pre class="language-json" data-line-numbers><code class="lang-json"><strong>{
</strong>    "trace_id": "577f5df0-65d6-432d-8aac-011789wfg2",
    "mid": "389d9ac9-c660-4459-b9d5-f43160183552",
    "type": "emu_version",
    "device_uid": "test",
    "sub_device_id": 2,
    "timestamp": 1725615497191,
    "data": [{
        "device_id": 2,
        "status": 1,
        "emu_upgrade_success": 1,
        "emu_upgrade_device": 3,
        "emu_upgrade_status": 5,
        "emu_upgrade_content": 100,
        "emu_product_sn": "emu-v1.0.0"   
    },
    {
        "device_id": 3,
        "status": 1,
        "emu_upgrade_success": 1,
        "emu_upgrade_device": 3,
        "emu_upgrade_status": 5,
        "emu_upgrade_content": 100,
        "emu_product_sn": "emu-v1.0.0"
    },
    {
        "device_id": 4,
        "status": 2,
        "emu_upgrade_success": null,
        "emu_upgrade_device": null,
        "emu_upgrade_status": null,
        "emu_upgrade_content": null,
        "emu_product_sn": ""
    }]
}
</code></pre>

## 下发OTA-EMU升级命令

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade`</mark>`/command`
* **权限：发布**
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>ota_upgrade</td><td>ota_upgrade</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data**

| 参数            | 类型     | 是否必填 | 描述   | 样例                                                       |
| ------------- | ------ | ---- | ---- | -------------------------------------------------------- |
| download\_url | string | 是    | 下载链接 | [http://example.com/ems\_II](http://example.com/ems\_II) |
| md5\_code     | string | 是    | MD5码 | <p>50a2811e047dd49ace3801685eedb732</p><p></p>           |

* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-06hjkgfg2",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "ota_upgrade",
  "device_uid": "test",
  "timestamp": 1697789021000,
  "data":{
    "download_url": "http://example.com/ems_II",
    "md5_code": "50a2811e047dd49ace3801685eedb732",
  }
}
```
{% endcode %}



### OTA-EMU升级命令响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade`</mark>`/result`
* **权限：**订阅
* **Payload主结构**

<table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>ota_upgrade</td><td>ota_upgrade</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_id</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>2</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **Payload - data**

<table><thead><tr><th width="183">参数</th><th width="93">类型</th><th width="99">是否必填</th><th width="255">描述</th><th>样例</th></tr></thead><tbody><tr><td>device_id</td><td>int</td><td>是</td><td>升级设备ID</td><td>2</td></tr><tr><td>download_status</td><td>int</td><td>是</td><td><p>下载状态</p><p>1-下发EMU升级成功</p><p>2-下发EMU升级失败</p><p>3-下载失败</p></td><td>1</td></tr></tbody></table>

* **Payload示例**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-011789wfg2",
    "mid": "389d9ac9-c660-4459-b9d5-f43160183552",
    "type": "emu_upgrade",
    "device_uid": "test",
    "sub_device_id": 2,
    "timestamp": 1725615497191,
    "data": {
        "device_id": 2,
        "download_status": 1,
    },
}
```
{% endcode %}



## 请求OTA-EMU升级结果

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade_result`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade_result`</mark>`/command`
* **权限：发布**
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>emu_upgrade_result</td><td>emu_upgrade_result</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_id</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>2</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data 无**
* **Payload示例**

{% code lineNumbers="true" %}
```json
{
  "trace_id": "577f5df0-65d6-432d-8aac-06hjkgfg2",
  "mid": "ee2e8f09-b280-4e4d-bcb9-1529b703cfed",
  "type": "emu_upgrade_result",
  "device_uid": "test",
  "sub_device_id": 2,
  "timestamp": 1697789021000,
}
```
{% endcode %}

### OTA-EMU升级结果响应

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade_result`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/emu_upgrade_result`</mark>`/result`
* **权限：订阅**
* **Payload主结构**

<table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>emu_upgrade_result</td><td>emu_upgrade_result</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_id</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备ID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>2</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **Payload - data**

<table><thead><tr><th width="159">参数</th><th width="93">类型</th><th width="99">是否必填</th><th width="255">描述</th><th>样例</th></tr></thead><tbody><tr><td>device_id</td><td>int</td><td>是</td><td>升级设备ID</td><td>2</td></tr><tr><td>status</td><td>int</td><td>是</td><td><p>设备状态</p><p>1-运行</p><p>2-离线</p><p>3-故障</p></td><td>1</td></tr><tr><td>emu_upgrade_success</td><td>int</td><td>否</td><td><p>EMU升级成功</p><p>0-有错误 </p><p>1-全部升级成功</p></td><td>1</td></tr><tr><td>emu_upgrade_device</td><td>int</td><td>否</td><td><p>EMU升级设备</p><p>3:EMU </p><p>21:通讯板卡1 </p><p>22:通讯板2 </p><p>23:通讯板3 </p><p>24:通讯板4 </p><p>25:通讯板5 </p><p>26:通讯板6</p></td><td>3</td></tr><tr><td>emu_upgrade_status</td><td>int</td><td>否</td><td><p>EMU升级状态 </p><p>1:升级准备 </p><p>2:传输准备 </p><p>3:传输状态 </p><p>4:校验状态 </p><p>5:完成状态</p></td><td>5</td></tr><tr><td>emu_upgrade_content</td><td>int</td><td>否</td><td>升级内容 传输状态:对应文件传输进度</td><td>100</td></tr><tr><td>emu_product_sn</td><td>string</td><td>否</td><td>EMU产品SN码</td><td>emu-v1.0.0</td></tr></tbody></table>

* **Payload示例**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-011789wfg2",
    "mid": "389d9ac9-c660-4459-b9d5-f43160183552",
    "type": "emu_upgrade_result",
    "device_uid": "test",
    "sub_device_id": 2,
    "timestamp": 1725615497191,
    "data": {
        "device_id": 2,
        "status": 1,
        "emu_upgrade_success": 1,
        "emu_upgrade_device": 3,
        "emu_upgrade_status": 5,
        "emu_upgrade_content": 100,
        "emu_product_sn": "emu-v1.0.0"
    },
}
```
{% endcode %}

