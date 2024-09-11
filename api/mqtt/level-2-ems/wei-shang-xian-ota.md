---
description: OTA
---

# \[未上线]OTA

## 下发OTA命令

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/upgrade`</mark>`/command`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/upgrade`</mark>`/command`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>ota_upgrade</td><td>ota_upgrade</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
* **Payload - data**

| 参数            | 类型     | 是否必填 | 描述   | 样例                                                       |
| ------------- | ------ | ---- | ---- | -------------------------------------------------------- |
| source        | string | 是    | 更新目标 | ems\_II                                                  |
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
    "source": "ems_II",
    "download_url": "http://example.com/ems_II",
    "md5_code": "50a2811e047dd49ace3801685eedb732",
  }
}
```
{% endcode %}

### 同步OTA结果响应

* **Topic：**

这里结果会有两阶段，发送两次响应，不同阶段对应的状态不同

* 第一阶段

第一阶段是准备阶段，在下载好确认文件无误后状态是 **2-文件已准备**。

状态有：**1-禁止更新 2-更新已准备3-更新准备失败**

* 第二阶段

第二阶段是最后结果，如果更新成功后状态是  **4-更新成功**。

状态有：**4-更新成功 5-回滚成功 6-回滚失败**

* **Topic：**
  * 用户自定义MQTT：`v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`ota/upgrade`</mark>`/result`
  * 平台默认MQTT： `v1/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`ota/upgrade`</mark>`/result`
* **权限：**订阅
* **Payload主结构**

<table><thead><tr><th width="173">参数</th><th width="81">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td>mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td>type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>ota_upgrade</td><td>ota_upgrade</td></tr><tr><td>data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td>sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>一级设备UID，仅二级替一级设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td>device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备UID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td>timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

* **Payload - data**

| 参数                  | 类型     | 是否必填 | 描述                                                                                           | 样例           |
| ------------------- | ------ | ---- | -------------------------------------------------------------------------------------------- | ------------ |
| source              | string | 否    | 来源                                                                                           | ems\_II      |
| version             | string | 否    | 当前版本                                                                                         | v1.0.0       |
| target\_commit\_sha | string | 否    | 目标提交SHA                                                                                      | 6f7g8h9i0j1k |
| target\_version     | string | 否    | 目标版本                                                                                         | v1.1.0       |
| final\_commit\_sha  | string | 否    | 最终提交SHA                                                                                      | 6f7g8h9i0j1k |
| final\_version      | string | 否    | 最终版本                                                                                         | v1.1.0       |
| status              | int    | 否    | <p>更新状态</p><p>1-禁止更新</p><p>2-更新已准备</p><p>3-更新准备失败</p><p>4-更新成功</p><p>5-回滚成功</p><p>6-回滚失败</p> | 4            |

* **Payload示例**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "577f5df0-65d6-432d-8aac-011789wfg2",
    "mid": "389d9ac9-c660-4459-b9d5-f43160183552",
    "type": "ota_upgrade",
    "device_uid": "test",
    "timestamp": 1725615497191,
    "data": {
        "source": "ems_II",
        "target_commit_sha": "6a2bbabde8d42abc6f8fef7b31f60c5e69045245",
        "target_version": "0.9.1",
        "final_commit_sha": "6a2bbabde8d42abc6f8fef7b31f60c5e69045245",
        "final_version": "0.9.1",
        "status": 4
    }
}
```
{% endcode %}

