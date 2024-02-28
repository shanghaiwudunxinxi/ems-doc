# 设备事件

## 定时上报信息

* **Topic：**
  * 用户自定义MQTT： `v1/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`report/regular`</mark>`/post`
  * 平台默认MQTT： `待定`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173" align="center">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td align="center">mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td align="center">type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>report_regular</td><td>report_regular</td></tr><tr><td align="center">data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td align="center">sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>子设备UID，仅二级替单个子设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td align="center">sub_device_id</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>false</td><td>子设备ID，仅二级替单个子设备上报时需要该字段</td><td>(0, ∞)</td><td>2</td></tr><tr><td align="center">device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备ID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td align="center">timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>
*   **Payload - data/reportRegular**

    <table><thead><tr><th width="97" align="center">参数</th><th width="195" align="center">类型</th><th width="96" data-type="checkbox">是否必填</th><th>描述</th><th>样例</th></tr></thead><tbody><tr><td align="center">type</td><td align="center">str</td><td>true</td><td>子设备类型<br>sub_ems: 一级EMS数据<br>sub_elemeter: 电表数据<br>sub_elemeters: 电表数据批量<br>ems: 二级ems数据</td><td>"ems"</td></tr><tr><td align="center">data</td><td align="center"><strong>SubEMSData/EMSData/SubEleMeterData/SubEleMetersData</strong></td><td>true</td><td>子设备/二级EMS数据</td><td>-</td></tr></tbody></table>
*   **Payload - SubEMSData**

    <table><thead><tr><th width="97" align="center">参数</th><th width="195" align="center">类型</th><th width="96" data-type="checkbox">是否必填</th><th>描述</th><th>样例</th></tr></thead><tbody><tr><td align="center">uid</td><td align="center">str</td><td>false</td><td>一级设备UID</td><td>"xxxx"</td></tr><tr><td align="center">bms</td><td align="center">RegularReportBMS</td><td>false</td><td>BMS数据</td><td>-</td></tr><tr><td align="center">pcs</td><td align="center">RegularReportPCS</td><td>false</td><td>PCS数据</td><td>-</td></tr><tr><td align="center">ems</td><td align="center">RegularReportEMS</td><td>false</td><td>EMS数据</td><td>-</td></tr><tr><td align="center">cooling</td><td align="center">RegularReportAircon/RegularReportLiquidcon</td><td>false</td><td>空调数据</td><td>-</td></tr><tr><td align="center">cooling_method</td><td align="center">str</td><td>false</td><td>冷却方式<br>air: 风冷<br>liquid: 液冷</td><td>“air“</td></tr><tr><td align="center">fire</td><td align="center">RegularReportFire</td><td>false</td><td>消防数据</td><td></td></tr></tbody></table>
*   **payload - RegularReportBMS**

    <table><thead><tr><th width="172" align="center">参数</th><th align="center">类型</th><th width="95" data-type="checkbox">是否必填</th><th width="169" align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">running_status</td><td align="center">int</td><td>false</td><td align="center">bms运行状态<br>0-未知状态<br>1-停机<br>2-待机<br>3-充电<br>4-放电</td><td align="center">2</td></tr><tr><td align="center">soc</td><td align="center">float</td><td>false</td><td align="center">电池运行状态 SOC</td><td align="center">5</td></tr><tr><td align="center">soh</td><td align="center">float</td><td>false</td><td align="center">电池运行状态 SOH</td><td align="center">4.9</td></tr><tr><td align="center">current_chargeable_energy</td><td align="center">float</td><td>false</td><td align="center">剩余充电电量</td><td align="center"></td></tr><tr><td align="center">current_dischargeable_energy</td><td align="center">float</td><td>false</td><td align="center">剩余放电电量</td><td align="center"></td></tr><tr><td align="center">charge_accumulated_energy</td><td align="center">float</td><td>false</td><td align="center">累计充电电量</td><td align="center"></td></tr><tr><td align="center">discharge_accumulated_energy</td><td align="center">float</td><td>false</td><td align="center">累计放电电量</td><td align="center"></td></tr><tr><td align="center">daily_charge_energy</td><td align="center">float</td><td>false</td><td align="center">日充电电量</td><td align="center"></td></tr><tr><td align="center">daily_discharge_energy</td><td align="center">float</td><td>false</td><td align="center">日放电电量</td><td align="center"></td></tr><tr><td align="center">total_voltage</td><td align="center">float</td><td>false</td><td align="center">总电压</td><td align="center">99</td></tr><tr><td align="center">total_current</td><td align="center">float</td><td>false</td><td align="center">总电流</td><td align="center">400</td></tr><tr><td align="center">power</td><td align="center">float</td><td>false</td><td align="center">功率</td><td align="center"></td></tr><tr><td align="center">max_allowed_charge_current</td><td align="center">float</td><td>false</td><td align="center">电池最大允许充电电流</td><td align="center">123</td></tr><tr><td align="center">max_allowed_discharge_current</td><td align="center">float</td><td>false</td><td align="center">电池最大允许放电电流</td><td align="center">456</td></tr><tr><td align="center">lowest_cell_temp</td><td align="center">float</td><td>false</td><td align="center">单体最低温度</td><td align="center">10</td></tr><tr><td align="center">lowest_temp_id</td><td align="center">int</td><td>false</td><td align="center">单体最低温度位置</td><td align="center"></td></tr><tr><td align="center">highest_cell_temp</td><td align="center">float</td><td>false</td><td align="center">单体最高温度</td><td align="center">50</td></tr><tr><td align="center">highest_temp_id</td><td align="center">int</td><td>false</td><td align="center">单体最高温度位置</td><td align="center"></td></tr><tr><td align="center">lowest_cell_voltage</td><td align="center">float</td><td>false</td><td align="center">单体最低电压</td><td align="center">2.345</td></tr><tr><td align="center">lowest_voltage_id</td><td align="center">int</td><td>false</td><td align="center">单体最低电压位置</td><td align="center"></td></tr><tr><td align="center">highest_cell_voltage</td><td align="center">float</td><td>false</td><td align="center">单体最高电压</td><td align="center">6.789</td></tr><tr><td align="center">highest_voltage_id</td><td align="center">int</td><td>false</td><td align="center">单体最高电压位置</td><td align="center"></td></tr><tr><td align="center">cell_voltage</td><td align="center">[]float</td><td>false</td><td align="center">单体电压</td><td align="center"></td></tr><tr><td align="center">cell_temp</td><td align="center">[]float</td><td>false</td><td align="center">单体温度</td><td align="center"></td></tr></tbody></table>


*   **payload - RegularReportPCS**

    <table><thead><tr><th align="center">参数</th><th width="119" align="center">类型</th><th width="98" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">running_status</td><td align="center">int</td><td>false</td><td align="center">PCS运行状态<br>0-未知状态<br>1-停机<br>2-待机<br>3-充电<br>4-放电</td><td align="center">2</td></tr><tr><td align="center">pcs_total_active_power</td><td align="center">float</td><td>false</td><td align="center">交流_总有功功率</td><td align="center">100</td></tr><tr><td align="center">pcs_active_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相有功功率</td><td align="center">0.16</td></tr><tr><td align="center">pcs_active_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相有功功率</td><td align="center">0.17</td></tr><tr><td align="center">pcs_active_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相有功功率</td><td align="center">0.18</td></tr><tr><td align="center">pcs_total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">交流_总无功功率</td><td align="center">0.26</td></tr><tr><td align="center">pcs_reactive_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相无功功率</td><td align="center">0.19</td></tr><tr><td align="center">pcs_reactive_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相无功功率</td><td align="center">0.2</td></tr><tr><td align="center">pcs_reactive_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相无功功率</td><td align="center">0.21</td></tr><tr><td align="center">pcs_voltage_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相电压</td><td align="center">1.1</td></tr><tr><td align="center">pcs_voltage_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相电压</td><td align="center">2.2</td></tr><tr><td align="center">pcs_voltage_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相电压</td><td align="center">3.3</td></tr><tr><td align="center">pcs_current_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相电流</td><td align="center">0.13</td></tr><tr><td align="center">pcs_current_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相电流</td><td align="center">0.14</td></tr><tr><td align="center">pcs_current_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相电流</td><td align="center">0.15</td></tr><tr><td align="center">pcs_total_power_factor</td><td align="center">float</td><td>false</td><td align="center">交流_总功率因数</td><td align="center">0.28</td></tr><tr><td align="center">pcs_power_factor_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相功率因数</td><td align="center">1.23</td></tr><tr><td align="center">pcs_power_factor_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相功率因数</td><td align="center">4.56</td></tr><tr><td align="center">pcs_power_factor_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相功率因数</td><td align="center">7.89</td></tr><tr><td align="center">pcs_frequency_grid</td><td align="center">float</td><td>false</td><td align="center">交流_电网总频率</td><td align="center"></td></tr><tr><td align="center">pcs_frequency_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相频率</td><td align="center"></td></tr><tr><td align="center">pcs_frequency_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相频率</td><td align="center"></td></tr><tr><td align="center">pcs_frequency_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相频率</td><td align="center"></td></tr><tr><td align="center">pcs_ac_daily_charge_energy</td><td align="center">float</td><td>false</td><td align="center">交流_日充电量</td><td align="center"></td></tr><tr><td align="center">pcs_ac_daily_discharge_energy</td><td align="center">float</td><td>false</td><td align="center">交流_日放电量</td><td align="center"></td></tr><tr><td align="center">pcs_ac_charge_accumulated_energy</td><td align="center">float</td><td>false</td><td align="center">交流_总充电电量</td><td align="center"></td></tr><tr><td align="center">pcs_ac_discharge_accumulated_energy</td><td align="center">float</td><td>false</td><td align="center">交流_总放电电量</td><td align="center"></td></tr><tr><td align="center">pcs_input_power</td><td align="center">float</td><td>false</td><td align="center">直流_功率</td><td align="center">0.33</td></tr><tr><td align="center">pcs_input_voltage</td><td align="center">float</td><td>false</td><td align="center">直流_电压</td><td align="center">3.4</td></tr><tr><td align="center">pcs_input_current</td><td align="center">float</td><td>false</td><td align="center">直流_电流</td><td align="center">0.35</td></tr><tr><td align="center">pcs_alarm_status</td><td align="center">int</td><td>false</td><td align="center">告警状态<br>0-正常<br>1-告警</td><td align="center"></td></tr><tr><td align="center">pcs_fault_status</td><td align="center">int</td><td>false</td><td align="center">故障状态<br>0-正常<br>1-故障</td><td align="center"></td></tr><tr><td align="center">pcs_grid_voltage_ab</td><td align="center">float</td><td>false</td><td align="center">AB相电网线电压</td><td align="center"></td></tr><tr><td align="center">pcs_grid_voltage_bc</td><td align="center">float</td><td>false</td><td align="center">BC相电网线电压</td><td align="center"></td></tr><tr><td align="center">pcs_grid_voltage_ca</td><td align="center">float</td><td>false</td><td align="center">CA相电网线电压</td><td align="center"></td></tr><tr><td align="center">pcs_internal_temp</td><td align="center">float</td><td>false</td><td align="center">设备内部腔体温度</td><td align="center"></td></tr><tr><td align="center">igbt_temp_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相IGBT温度</td><td align="center"></td></tr><tr><td align="center">igbt_temp_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相IGBT温度</td><td align="center"></td></tr><tr><td align="center">igbt_temp_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相IGBT温度</td><td align="center"></td></tr></tbody></table>
*   **payload - RegularReportEMS**

    <table><thead><tr><th width="178" align="center">参数</th><th width="109" align="center">类型</th><th width="98" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">mode</td><td align="center">int</td><td>false</td><td align="center">运行模式<br>0-本地调试模式<br>1-本地自动模式<br>2-远程被动模式</td><td align="center"></td></tr><tr><td align="center">charge_strategy</td><td align="center">待定</td><td>false</td><td align="center">充放电策略<br>（仅mode为远程时有）</td><td align="center"></td></tr><tr><td align="center">protection_strategy</td><td align="center">待定</td><td>false</td><td align="center">安全保护<br>（仅mode为远程时有）</td><td align="center"></td></tr></tbody></table>
*   **payload - RegularReportAircon**

    <table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">machine_status</td><td align="center">int</td><td>false</td><td align="center">整机状态<br>0-停止<br>1-运行</td><td align="center"></td></tr><tr><td align="center">cooling_status</td><td align="center">int</td><td>false</td><td align="center">制冷<br>0-停止<br>1-运行</td><td align="center"></td></tr><tr><td align="center">heating_status</td><td align="center">int</td><td>false</td><td align="center">制热<br>0-停止<br>1-运行</td><td align="center"></td></tr><tr><td align="center">outdoor_temp</td><td align="center">float</td><td>false</td><td align="center">环境温度/室外温度</td><td align="center"></td></tr><tr><td align="center">coil_temp</td><td align="center">float</td><td>false</td><td align="center">盘管温度</td><td align="center"></td></tr><tr><td align="center">indoor_temp</td><td align="center">float</td><td>false</td><td align="center">室内温度</td><td align="center"></td></tr><tr><td align="center">exhaust_temp</td><td align="center">float</td><td>false</td><td align="center">排气温度</td><td align="center"></td></tr><tr><td align="center">cooling_point</td><td align="center">float</td><td>false</td><td align="center">制冷点</td><td align="center"></td></tr><tr><td align="center">heating_poing</td><td align="center">float</td><td>false</td><td align="center">加热点</td><td align="center"></td></tr></tbody></table>
*   **payload - RegularReportLiquidcon**

    <table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">machine_status</td><td align="center">int</td><td>false</td><td align="center">整机状态<br>0-停止<br>1-运行</td><td align="center"></td></tr><tr><td align="center">indoor_temp</td><td align="center">float</td><td>false</td><td align="center">室内温度</td><td align="center"></td></tr><tr><td align="center">inlet_temp</td><td align="center">float</td><td>false</td><td align="center">进水温度</td><td align="center"></td></tr><tr><td align="center">outlet_temp</td><td align="center">float</td><td>false</td><td align="center">出水温度</td><td align="center"></td></tr><tr><td align="center">inlet_pressure</td><td align="center">float</td><td>false</td><td align="center">进水口压力值</td><td align="center"></td></tr><tr><td align="center">outlet_pressure</td><td align="center">float</td><td>false</td><td align="center">出水口压力值</td><td align="center"></td></tr><tr><td align="center">cooling_point</td><td align="center">float</td><td>false</td><td align="center">制冷点</td><td align="center"></td></tr><tr><td align="center">heating_poing</td><td align="center">float</td><td>false</td><td align="center">加热点</td><td align="center"></td></tr></tbody></table>
*   **payload - RegularReportFire**

    <table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">fire_alarm_status</td><td align="center">int</td><td>false</td><td align="center">告警状态</td><td align="center"></td></tr></tbody></table>
*   **payload - EMSData**

    <table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">total</td><td align="center">EMSDataTotal</td><td>false</td><td align="center">二级EMS汇总</td><td align="center"></td></tr></tbody></table>
*   **payload - EMSDataTotal**

    <table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">running_status</td><td align="center">int</td><td>false</td><td align="center">运行状态<br>0-未知状态<br>1-停机<br>2-运行</td><td align="center"></td></tr><tr><td align="center">soc</td><td align="center">float</td><td>false</td><td align="center">平均soc</td><td align="center"></td></tr><tr><td align="center">pcs_total_active_power</td><td align="center">float</td><td>false</td><td align="center">当前总有功功率</td><td align="center"></td></tr><tr><td align="center">pcs_total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">当前总无功功率</td><td align="center"></td></tr><tr><td align="center">current_chargeable_energy</td><td align="center">float</td><td>false</td><td align="center">剩余可充电电量</td><td align="center"></td></tr><tr><td align="center">current_dischargeable_energy</td><td align="center">float</td><td>false</td><td align="center">剩余可放电电量</td><td align="center"></td></tr></tbody></table>
*   **payload - SubEleMeterData**

    <table><thead><tr><th width="180" align="center">参数</th><th width="110" align="center">类型</th><th width="99" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">id</td><td align="center">int</td><td>true</td><td align="center">设备ID</td><td align="center">2</td></tr><tr><td align="center">uid</td><td align="center">string</td><td>false</td><td align="center">设备UID</td><td align="center"></td></tr><tr><td align="center">purpose</td><td align="center">int</td><td>true</td><td align="center"><p>电表用途</p><p>1-关口表</p><p>2-计量表</p></td><td align="center">1</td></tr><tr><td align="center">total_active_power</td><td align="center">float</td><td>false</td><td align="center">总有功功率</td><td align="center">100.5</td></tr><tr><td align="center">active_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相有功功率</td><td align="center">101.5</td></tr><tr><td align="center">active_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相有功功率</td><td align="center">102.5</td></tr><tr><td align="center">active_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相有功功率</td><td align="center">103.5</td></tr><tr><td align="center">total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">总无功功率</td><td align="center">104.5</td></tr><tr><td align="center">reactive_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相无功功率</td><td align="center">105.5</td></tr><tr><td align="center">reactive_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相无功功率</td><td align="center">106.5</td></tr><tr><td align="center">reactive_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相无功功率</td><td align="center">107.5</td></tr><tr><td align="center">total_apparent_power</td><td align="center">float</td><td>false</td><td align="center">总视在功率</td><td align="center">108.5</td></tr><tr><td align="center">apparent_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相视在功率</td><td align="center">109.5</td></tr><tr><td align="center">apparent_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相视在功率</td><td align="center">110.5</td></tr><tr><td align="center">apparent_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相视在功率</td><td align="center">111.5</td></tr><tr><td align="center">total_power_factor</td><td align="center">float</td><td>false</td><td align="center">总功率因数</td><td align="center">112.5</td></tr><tr><td align="center">power_factor_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相功率因数</td><td align="center">113.5</td></tr><tr><td align="center">power_factor_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相功率因数</td><td align="center">114.5</td></tr><tr><td align="center">power_factor_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相功率因数</td><td align="center">115.5</td></tr><tr><td align="center">voltage_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相电压</td><td align="center">116.5</td></tr><tr><td align="center">voltage_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相电压</td><td align="center">117.5</td></tr><tr><td align="center">voltage_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相电压</td><td align="center">118.5</td></tr><tr><td align="center">current_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相电流</td><td align="center">119.5</td></tr><tr><td align="center">current_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相电流</td><td align="center">120.5</td></tr><tr><td align="center">current_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相电流</td><td align="center">121.5</td></tr><tr><td align="center">frequency_grid</td><td align="center">float</td><td>false</td><td align="center">电网总频率</td><td align="center">122.5</td></tr><tr><td align="center">frequency_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相频率</td><td align="center">123.5</td></tr><tr><td align="center">frequency_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相频率</td><td align="center">124.5</td></tr><tr><td align="center">frequency_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相频率</td><td align="center">125.5</td></tr><tr><td align="center">total_forward_active_energy</td><td align="center">float</td><td>false</td><td align="center">正向有功总电能</td><td align="center">126.5</td></tr><tr><td align="center">forward_active_energy_sharp</td><td align="center">float</td><td>false</td><td align="center">正向有功尖电能</td><td align="center">127.5</td></tr><tr><td align="center">forward_active_energy_peak</td><td align="center">float</td><td>false</td><td align="center">正向有功峰电能</td><td align="center">128.5</td></tr><tr><td align="center">forward_active_energy_flat</td><td align="center">float</td><td>false</td><td align="center">正向有功平电能</td><td align="center">129.5</td></tr><tr><td align="center">forward_active_energy_valley</td><td align="center">float</td><td>false</td><td align="center">正向有功谷电能</td><td align="center">130.5</td></tr><tr><td align="center">total_reverse_active_energy</td><td align="center">float</td><td>false</td><td align="center">反向有功总电能</td><td align="center">131.5</td></tr><tr><td align="center">reverse_active_energy_sharp</td><td align="center">float</td><td>false</td><td align="center">反向有功尖电能</td><td align="center">132.5</td></tr><tr><td align="center">reverse_active_energy_peak</td><td align="center">float</td><td>false</td><td align="center">反向有功峰电能</td><td align="center">133.5</td></tr><tr><td align="center">reverse_active_energy_flat</td><td align="center">float</td><td>false</td><td align="center">反向有功平电能</td><td align="center">134.5</td></tr><tr><td align="center">reverse_active_energy_valley</td><td align="center">float</td><td>false</td><td align="center">反向有功谷电能</td><td align="center">135.5</td></tr></tbody></table>
* **payload - SubEleMetersData = \[]SubEleMeterData**
* **Payload示例-sub\_ems**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "085be8f4-2f7b-488d-8a93-d0c7dcd7f033",
    "mid": "044b29cf-565e-434d-82a6-364411af6a71",
    "type": "report_regular",
    "sub_device_uid": "iBbgRK0Lno5yUdF",
    "sub_device_id": 2,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705980251899,
    "data": {
        "type": "sub_ems",
        "data": {
            "uid": "iBbgRK0Lno5yUdF",
            "bms": {
                "running_status": 0,
                "soc": 88,
                "soh": 99,
                "current_chargeable_energy": 4.4,
                "current_dischargeable_energy": 2.2,
                "total_voltage": 6.6,
                "total_current": 161.30000000000018,
                "power": null,
                "charge_accumulated_energy": 0,
                "discharge_accumulated_energy": 0,
                "daily_charge_energy": 0,
                "daily_discharge_energy": 0,
                "max_allowed_charge_current": 20,
                "max_allowed_discharge_current": 10,
                "lowest_cell_temp": 6459.6,
                "lowest_temp_id": 4,
                "highest_cell_temp": 6460.6,
                "highest_temp_id": 3,
                "temp_diff": 1,
                "lowest_cell_voltage": 345,
                "lowest_voltage_id": 2,
                "highest_cell_voltage": 234,
                "highest_voltage_id": 1,
                "voltage_diff": 6225.6,
                "cell_voltage": [10, 10, 10, ...],
                "cell_temp": [25.4, 25.4, 25.4, ...]
            },
            "pcs": {
                "running_status": 2,
                "pcs_total_active_power": 2500,
                "pcs_active_power_phase_a": null,
                "pcs_active_power_phase_b": null,
                "pcs_active_power_phase_c": null,
                "pcs_total_reactive_power": 444.4,
                "pcs_reactive_power_phase_a": null,
                "pcs_reactive_power_phase_b": null,
                "pcs_reactive_power_phase_c": null,
                "pcs_voltage_phase_a": 0,
                "pcs_voltage_phase_b": 0,
                "pcs_voltage_phase_c": 0,
                "pcs_current_phase_a": 1.2,
                "pcs_current_phase_b": 2.3,
                "pcs_current_phase_c": 3.4,
                "pcs_total_power_factor": 8.88,
                "pcs_power_factor_phase_a": null,
                "pcs_power_factor_phase_b": null,
                "pcs_power_factor_phase_c": null,
                "pcs_frequency_grid": null,
                "pcs_frequency_phase_a": null,
                "pcs_frequency_phase_b": null,
                "pcs_frequency_phase_c": null,
                "pcs_ac_daily_charge_energy": 0,
                "pcs_ac_daily_discharge_energy": 0,
                "pcs_ac_charge_accumulated_energy": 0,
                "pcs_ac_discharge_accumulated_energy": 0,
                "pcs_input_power": 4.4,
                "pcs_input_voltage": 3.3,
                "pcs_input_current": 4.4,
                "pcs_alarm_status": 0,
                "pcs_fault_status": 0,
                "pcs_grid_voltage_ab": 0,
                "pcs_grid_voltage_bc": 0,
                "pcs_grid_voltage_ca": 0,
                "pcs_internal_temp": 7.7,
                "igbt_temp_phase_a": 0,
                "igbt_temp_phase_b": 0,
                "igbt_temp_phase_c": 0
            },
            "ems": {
                "mode": 2
            },
            "cooling_method": "air",
            "cooling": {
                "machine_status": null,
                "cooling_status": null,
                "heating_status": null,
                "outdoor_temp": null,
                "coil_temp": null,
                "indoor_temp": null,
                "exhaust_temp": null,
                "cooling_point": null,
                "heating_poing": null
            },
            "fire": {
                "fire_alarm_status": 1
            }
        }
    }
}
```
{% endcode %}

* **Payload示例-ems**

```json
{
    "trace_id": "a73f409b-69db-469d-ab46-5913e3cbb73a",
    "mid": "33c71134-f57f-42d5-a76a-bd225ba09faf",
    "type": "report_regular",
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705980251904,
    "data": {
        "type": "ems",
        "data": {
            "total": {
                "running_status": 2,
                "soc": 95.33333333333333,
                "pcs_total_active_power": 2500,
                "pcs_total_reactive_power": 444.4,
                "current_chargeable_energy": 4.4,
                "current_dischargeable_energy": 2.2
            }
        }
    }
}
```

* **Payload示例-sub\_elemeter**

```json
{
    "trace_id": "2f492a12-5408-40b3-b347-ed64a3723050",
    "mid": "d39835f5-2087-4601-8a12-85bb2bceb690",
    "type": "report_regular",
    "sub_device_uid": "a8TJthsYq3J4hjz",
    "sub_device_id": 2,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705563840345,
    "data": {
        "type": "sub_elemeter",
        "data": {
            "id": 2,
            "uid": "",
            "purpose": 1,
            "total_active_power": 100.5,
            "active_power_phase_a": 101.5,
            "active_power_phase_b": 102.5,
            "active_power_phase_c": 103.5,
            "total_reactive_power": 104.5,
            "reactive_power_phase_a": 105.5,
            "reactive_power_phase_b": 106.5,
            "reactive_power_phase_c": 107.5,
            "total_apparent_power": 108.5,
            "apparent_power_phase_a": 109.5,
            "apparent_power_phase_b": 110.5,
            "apparent_power_phase_c": 111.5,
            "total_power_factor": 112.5,
            "power_factor_phase_a": 113.5,
            "power_factor_phase_b": 114.5,
            "power_factor_phase_c": 115.5,
            "voltage_phase_a": 116.5,
            "voltage_phase_b": 117.5,
            "voltage_phase_c": 118.5,
            "current_phase_a": 119.5,
            "current_phase_b": 120.5,
            "current_phase_c": 121.5,
            "frequency_grid": 122.5,
            "frequency_phase_a": 123.5,
            "frequency_phase_b": 124.5,
            "frequency_phase_c": 125.5,
            "total_forward_active_energy": 126.5,
            "forward_active_energy_sharp": 127.5,
            "forward_active_energy_peak": 128.5,
            "forward_active_energy_flat": 129.5,
            "forward_active_energy_valley": 130.5,
            "total_reverse_active_energy": 131.5,
            "reverse_active_energy_sharp": 132.5,
            "reverse_active_energy_peak": 133.5,
            "reverse_active_energy_flat": 134.5,
            "reverse_active_energy_valley": 135.5
        }
    }
}
```

* **Payload示例-sub\_elemeters**

```json
{
    "trace_id": "2f492a12-5408-40b3-b347-ed64a3723050",
    "mid": "d39835f5-2087-4601-8a12-85bb2bceb690",
    "type": "report_regular",
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705563840345,
    "data": {
        "type": "sub_elemeters",
        "data": [
            {
                "id": 1,
                "uid": "",
                "purpose": 2,
                "total_active_power": 100.5,
                "active_power_phase_a": 101.5,
                "active_power_phase_b": 102.5,
                "active_power_phase_c": 103.5,
                "total_reactive_power": 104.5,
                "reactive_power_phase_a": 105.5,
                "reactive_power_phase_b": 106.5,
                "reactive_power_phase_c": 107.5,
                "total_apparent_power": 108.5,
                "apparent_power_phase_a": 109.5,
                "apparent_power_phase_b": 110.5,
                "apparent_power_phase_c": 111.5,
                "total_power_factor": 112.5,
                "power_factor_phase_a": 113.5,
                "power_factor_phase_b": 114.5,
                "power_factor_phase_c": 115.5,
                "voltage_phase_a": 116.5,
                "voltage_phase_b": 117.5,
                "voltage_phase_c": 118.5,
                "current_phase_a": 119.5,
                "current_phase_b": 120.5,
                "current_phase_c": 121.5,
                "frequency_grid": 122.5,
                "frequency_phase_a": 123.5,
                "frequency_phase_b": 124.5,
                "frequency_phase_c": 125.5,
                "total_forward_active_energy": 126.5,
                "forward_active_energy_sharp": 127.5,
                "forward_active_energy_peak": 128.5,
                "forward_active_energy_flat": 129.5,
                "forward_active_energy_valley": 130.5,
                "total_reverse_active_energy": 131.5,
                "reverse_active_energy_sharp": 132.5,
                "reverse_active_energy_peak": 133.5,
                "reverse_active_energy_flat": 134.5,
                "reverse_active_energy_valley": 135.5
            },
            {
                "id": 2,
                "uid": "",
                "purpose": 1,
                "total_active_power": 100.5,
                "active_power_phase_a": 101.5,
                "active_power_phase_b": 102.5,
                "active_power_phase_c": 103.5,
                "total_reactive_power": 104.5,
                "reactive_power_phase_a": 105.5,
                "reactive_power_phase_b": 106.5,
                "reactive_power_phase_c": 107.5,
                "total_apparent_power": 108.5,
                "apparent_power_phase_a": 109.5,
                "apparent_power_phase_b": 110.5,
                "apparent_power_phase_c": 111.5,
                "total_power_factor": 112.5,
                "power_factor_phase_a": 113.5,
                "power_factor_phase_b": 114.5,
                "power_factor_phase_c": 115.5,
                "voltage_phase_a": 116.5,
                "voltage_phase_b": 117.5,
                "voltage_phase_c": 118.5,
                "current_phase_a": 119.5,
                "current_phase_b": 120.5,
                "current_phase_c": 121.5,
                "frequency_grid": 122.5,
                "frequency_phase_a": 123.5,
                "frequency_phase_b": 124.5,
                "frequency_phase_c": 125.5,
                "total_forward_active_energy": 126.5,
                "forward_active_energy_sharp": 127.5,
                "forward_active_energy_peak": 128.5,
                "forward_active_energy_flat": 129.5,
                "forward_active_energy_valley": 130.5,
                "total_reverse_active_energy": 131.5,
                "reverse_active_energy_sharp": 132.5,
                "reverse_active_energy_peak": 133.5,
                "reverse_active_energy_flat": 134.5,
                "reverse_active_energy_valley": 135.5
            },
        ]
    }
}
```
