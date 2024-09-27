---
description: V2
---

# 设备事件V2

## 定时上报信息

* **Topic：**
  * 用户自定义MQTT： `v2/wudun/${PRODUCT_KEY}/${DEVICE}/`<mark style="color:red;">`report/regular`</mark>`/post`
  * 平台默认MQTT： `v2/user/${TENANT}/${DEVICE}/`<mark style="color:red;">`report/regular`</mark>`/post`
* **权限：**订阅
*   **Payload主结构**

    <table><thead><tr><th width="173" align="center">参数</th><th width="80">类型<select><option value="36cc16022bbb4c7b93fe3a347e4eee85" label="UUID" color="blue"></option><option value="826385f71ccd46638f3a63c8d6abef21" label="str" color="blue"></option><option value="bb5bb2c3a10846bf881acb0506b5951f" label="int" color="blue"></option><option value="f53674f5f7b044bab9768d2995855ea2" label="[]str" color="blue"></option><option value="005ee50172ec4f44a83308b0bfb12d48" label="[]data" color="blue"></option></select></th><th width="100" data-type="checkbox">是否必填</th><th>描述</th><th>范围</th><th>样例</th></tr></thead><tbody><tr><td align="center">mid</td><td><span data-option="36cc16022bbb4c7b93fe3a347e4eee85">UUID</span></td><td>true</td><td>消息ID</td><td>-</td><td>3e681859-6917-4b9a-9afd-3f162cd185bd</td></tr><tr><td align="center">type</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>消息类型</td><td>report_regular</td><td>report_regular</td></tr><tr><td align="center">data</td><td><span data-option="005ee50172ec4f44a83308b0bfb12d48">[]data</span></td><td>true</td><td>消息内容</td><td>-</td><td>见<strong>Payload - data</strong></td></tr><tr><td align="center">sub_device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>false</td><td>子设备UID，仅二级替单个子设备上报时需要该字段</td><td>-</td><td>jHODSda39</td></tr><tr><td align="center">sub_device_id</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>false</td><td>子设备ID，仅二级替单个子设备上报时需要该字段</td><td>(0, ∞)</td><td>2</td></tr><tr><td align="center">device_uid</td><td><span data-option="826385f71ccd46638f3a63c8d6abef21">str</span></td><td>true</td><td>设备ID</td><td>-</td><td>iYRkfVpi77</td></tr><tr><td align="center">timestamp</td><td><span data-option="bb5bb2c3a10846bf881acb0506b5951f">int</span></td><td>true</td><td>消息时间戳（单位：毫秒）</td><td>(0, ∞)</td><td>1696837112000</td></tr></tbody></table>

### **Payload - data/ReportRegular**

<table><thead><tr><th width="97" align="center">参数</th><th width="253" align="center">类型</th><th width="89" data-type="checkbox">是否必填</th><th width="277">描述</th><th>样例</th></tr></thead><tbody><tr><td align="center">type</td><td align="center">str</td><td>true</td><td><p>sub_ems_fire: 一级EMS设备火警数据</p><p>sub_ems_aircon:一级EMS设备风冷数据</p><p>sub_ems_liquidcon:一级EMS设备液冷数据</p><p>sub_ems_bms: 一级EMS设备BMS数据</p><p>sub_ems_pcs: 一级EMS设备PCS数据<br>sub_elemeter: 电表数据<br>ems: 二级ems数据<br>photovoltaic_elemeter: 光伏（电表）数据<br>photovoltaic_inverter: 光伏（逆变器）数据<br>alternating_pail: 充电桩（交流充电桩）数据<br>direct_pail: 充电桩（直流充电桩）<br>pail_meter: 充电桩（电表）数据</p></td><td>"ems"</td></tr><tr><td align="center">index</td><td align="center">int</td><td>true</td><td>编号</td><td>0</td></tr><tr><td align="center">data</td><td align="center"><p>(<strong>SubEMSFire/SubEMSAircon/SubEMSLiquid)/</strong></p><p><strong>SubEMSBMS/SubEMSPCS/</strong></p><p><strong>EMSData/</strong></p><p><strong>SubEleMeterData/</strong></p><p><strong>PhotovoltaicMeterData/</strong></p><p><strong>PhotovoltaicInverterData/</strong><br><strong>DirectChargePailData/</strong><br><strong>AlternatingChargePailData/</strong><br><strong>ChargePailMeterData</strong></p></td><td>true</td><td><p>一级EMS火警/风冷/液冷数据组合</p><p>一级EMS设备BMS数据</p><p>一级EMS设备PCS数据</p><p>二级EMS数据</p><p>电表数据</p><p>光伏电表类型</p><p>光伏逆变器类型<br>直流充电桩<br>交流充电桩<br>充电桩电表</p></td><td>-</td></tr></tbody></table>

### **payload - RegularReportSubEMSFire**

<table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">fire_smoke_alarm_status</td><td align="center">int</td><td>false</td><td align="center">烟雾传感器报警状态: 0-无烟雾告警，1-有烟感告警</td><td align="center">1</td></tr><tr><td align="center">fire_flammable_gas_alarm_status</td><td align="center">int</td><td>false</td><td align="center">可燃气体传感器报警状态: 0-无可燃气体告警，1-有可燃气体告警</td><td align="center">1</td></tr><tr><td align="center">fire_safety_equipments_status</td><td align="center">int</td><td>false</td><td align="center">消防装置状态: 0-正常（无动作）；1、被启动（火警</td><td align="center">1</td></tr><tr><td align="center">fire_safety_system</td><td align="center">int</td><td>false</td><td align="center">0-正常;1-故障</td><td align="center">1</td></tr><tr><td align="center">fire_temperature_sensor</td><td align="center">float</td><td>false</td><td align="center">温度传感器</td><td align="center"></td></tr><tr><td align="center">fire_humidity_sensor</td><td align="center">float</td><td>false</td><td align="center">湿度传感器</td><td align="center"></td></tr></tbody></table>

### **payload - RegularReportSubEMSAircon**

<table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">machine_status</td><td align="center">int</td><td>false</td><td align="center"><p>整机状态<br>0-未知<br>1-关机</p><p>2-制冷</p><p>3-制热</p><p>4-自循环</p><p>5-自动</p><p>6-待机</p></td><td align="center"></td></tr><tr><td align="center">cooling_status</td><td align="center">int</td><td>false</td><td align="center">制冷<br>0-停止<br>1-运行</td><td align="center"></td></tr><tr><td align="center">heating_status</td><td align="center">int</td><td>false</td><td align="center">制热<br>0-停止<br>1-运行</td><td align="center"></td></tr><tr><td align="center">outdoor_temp</td><td align="center">float</td><td>false</td><td align="center">环境温度/室外温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">coil_temp</td><td align="center">float</td><td>false</td><td align="center">盘管温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">indoor_temp</td><td align="center">float</td><td>false</td><td align="center">室内温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">exhaust_temp</td><td align="center">float</td><td>false</td><td align="center">排气温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">cooling_point</td><td align="center">float</td><td>false</td><td align="center">制冷点（单位：℃）</td><td align="center"></td></tr><tr><td align="center">heating_point</td><td align="center">float</td><td>false</td><td align="center">加热点（单位：℃）</td><td align="center"></td></tr></tbody></table>

### **payload - RegularReportSubEMSLiquidcon**

<table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">machine_status</td><td align="center">int</td><td>false</td><td align="center"><p>整机状态<br>0-未知<br>1-关机</p><p>2-制冷</p><p>3-制热</p><p>4-自循环</p><p>5-自动</p><p>6-待机</p></td><td align="center"></td></tr><tr><td align="center">indoor_temp</td><td align="center">float</td><td>false</td><td align="center">室内温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">inlet_temp</td><td align="center">float</td><td>false</td><td align="center">进水温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">outlet_temp</td><td align="center">float</td><td>false</td><td align="center">出水温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">inlet_pressure</td><td align="center">float</td><td>false</td><td align="center">进水口压力值（单位：bar）</td><td align="center"></td></tr><tr><td align="center">outlet_pressure</td><td align="center">float</td><td>false</td><td align="center">出水口压力值（单位：bar）</td><td align="center"></td></tr><tr><td align="center">ambient_temperature</td><td align="center">float</td><td>false</td><td align="center">环境温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">compressor_power</td><td align="center">float</td><td>false</td><td align="center">压缩机功率（单位：kW）</td><td align="center"></td></tr><tr><td align="center">cooling_point</td><td align="center">float</td><td>false</td><td align="center">制冷点（单位：℃）</td><td align="center"></td></tr><tr><td align="center">heating_point</td><td align="center">float</td><td>false</td><td align="center">加热点（单位：℃）</td><td align="center"></td></tr></tbody></table>

### **payload - RegularReportSubEMSBMS**

<table><thead><tr><th width="208">参数</th><th width="112">类型</th><th width="99" data-type="checkbox">是否必填</th><th width="201">描述</th><th>样例</th></tr></thead><tbody><tr><td>running_status</td><td>int</td><td>false</td><td><p>bms运行状态</p><p>0-未知状态</p><p>1-停机</p><p>2-待机</p><p>3-充电</p><p>4-放电</p></td><td>1</td></tr><tr><td>total_alarm_status</td><td>int</td><td>false</td><td><p>总告警</p><p>0-正常</p><p>1-告警</p></td><td>0</td></tr><tr><td>total_fault_status</td><td>int</td><td>false</td><td><p>总故障</p><p>0-正常</p><p>1-故障</p></td><td>0</td></tr><tr><td>high_voltage_closed_status</td><td>int</td><td>false</td><td><p>高压状态</p><p>0-断开</p><p>1-闭合</p></td><td>1</td></tr><tr><td>soc</td><td>float</td><td>false</td><td>SOC</td><td>80.1</td></tr><tr><td>soh</td><td>float</td><td>false</td><td>SOH</td><td>90.2</td></tr><tr><td>current_chargeable_energy</td><td>float</td><td>false</td><td>剩余充电电量</td><td>1000</td></tr><tr><td>current_dis_chargeable_energy</td><td>float</td><td>false</td><td>剩余放电电量</td><td>2000</td></tr><tr><td>total_voltage</td><td>float</td><td>false</td><td>组电压</td><td>400</td></tr><tr><td>total_current</td><td>float</td><td>false</td><td>组电流</td><td>-10</td></tr><tr><td>power</td><td>float</td><td>false</td><td>组功率</td><td>4000</td></tr><tr><td>charge_accumulated_energy</td><td>float</td><td>false</td><td>累计充电电量</td><td>100000</td></tr><tr><td>discharge_accumulated_energy</td><td>float</td><td>false</td><td>累计放电电量</td><td>50000</td></tr><tr><td>daily_charge_energy</td><td>float</td><td>false</td><td>日充电电量（单位：kWh）</td><td>100</td></tr><tr><td>daily_discharge_energy</td><td>float</td><td>false</td><td>日放电电量（单位：kWh）</td><td>50</td></tr><tr><td>max_allowed_charge_power</td><td>float</td><td>false</td><td>允许充电最大功率</td><td>5000</td></tr><tr><td>max_allowed_discharge_power</td><td>float</td><td>false</td><td>允许放电最大功率</td><td>3000</td></tr><tr><td>max_allowed_charge_current</td><td>float</td><td>false</td><td>允许充电最大电流</td><td>200</td></tr><tr><td>max_allowed_dis_charge_current</td><td>float</td><td>false</td><td>允许放电最大电流</td><td>100</td></tr><tr><td>highest_cell_voltage</td><td>float</td><td>false</td><td>最高单体电压</td><td>4200</td></tr><tr><td>highest_voltage_id_cell</td><td>int</td><td>false</td><td>最高单体电压对应编号</td><td>3</td></tr><tr><td>lowest_cell_voltage</td><td>float</td><td>false</td><td>最低单体电压</td><td>4100</td></tr><tr><td>lowest_voltage_id_cell</td><td>int</td><td>false</td><td>最低单体电压对应编号</td><td>5</td></tr><tr><td>average_cell_voltage</td><td>float</td><td>false</td><td>平均单体电压</td><td>4150</td></tr><tr><td>highest_cell_temp</td><td>float</td><td>false</td><td>最高单体温度</td><td>40</td></tr><tr><td>highest_temp_id</td><td>int</td><td>false</td><td>最高单体温度对应编号</td><td>4</td></tr><tr><td>lowest_cell_temp</td><td>float</td><td>false</td><td>最低单体温度</td><td>-5</td></tr><tr><td>lowest_temp_id</td><td>int</td><td>false</td><td>最低单体温度对应编号</td><td>6</td></tr><tr><td>average_cell_temperature</td><td>float</td><td>false</td><td>平均单体温度</td><td>20</td></tr><tr><td>voltage_diff</td><td>float</td><td>false</td><td>单体电压极差值</td><td>100</td></tr><tr><td>temp_diff</td><td>loat</td><td>false</td><td>单体温度极差值</td><td>45</td></tr><tr><td>cell_voltage</td><td>[]float</td><td>false</td><td>单体电压(数组长度固定为700)</td><td>[4150,4130,4110]</td></tr><tr><td>cell_temp</td><td>[]float</td><td>false</td><td>单体温度(数组长度固定为700)</td><td>[20,23,21]</td></tr></tbody></table>

### **payload - RegularReportSubEMSPCS**

<table><thead><tr><th align="center">参数</th><th width="119" align="center">类型</th><th width="98" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">running_status</td><td align="center">int</td><td>false</td><td align="center">PCS运行状态<br>0-未知状态<br>1-停机<br>2-待机<br>3-充电<br>4-放电</td><td align="center">2</td></tr><tr><td align="center">pcs_total_active_power</td><td align="center">float</td><td>false</td><td align="center">交流_总有功功率（单位：kW）</td><td align="center">100</td></tr><tr><td align="center">pcs_active_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相有功功率（单位：kW）</td><td align="center">0.16</td></tr><tr><td align="center">pcs_active_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相有功功率（单位：kW）</td><td align="center">0.17</td></tr><tr><td align="center">pcs_active_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相有功功率（单位：kW）</td><td align="center">0.18</td></tr><tr><td align="center">pcs_total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">交流_总无功功率（单位：kVar）</td><td align="center">0.26</td></tr><tr><td align="center">pcs_reactive_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相无功功率（单位：kVar）</td><td align="center">0.19</td></tr><tr><td align="center">pcs_reactive_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相无功功率（单位：kVar）</td><td align="center">0.2</td></tr><tr><td align="center">pcs_reactive_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相无功功率（单位：kVar）</td><td align="center">0.21</td></tr><tr><td align="center">pcs_voltage_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相电压（单位：V）</td><td align="center">1.1</td></tr><tr><td align="center">pcs_voltage_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相电压（单位：V）</td><td align="center">2.2</td></tr><tr><td align="center">pcs_voltage_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相电压（单位：V）</td><td align="center">3.3</td></tr><tr><td align="center">pcs_current_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相电流（单位：A）</td><td align="center">0.13</td></tr><tr><td align="center">pcs_current_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相电流（单位：A）</td><td align="center">0.14</td></tr><tr><td align="center">pcs_current_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相电流（单位：A）</td><td align="center">0.15</td></tr><tr><td align="center">pcs_total_power_factor</td><td align="center">float</td><td>false</td><td align="center">交流_总功率因数</td><td align="center">0.28</td></tr><tr><td align="center">pcs_power_factor_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相功率因数</td><td align="center">1.23</td></tr><tr><td align="center">pcs_power_factor_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相功率因数</td><td align="center">4.56</td></tr><tr><td align="center">pcs_power_factor_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相功率因数</td><td align="center">7.89</td></tr><tr><td align="center">pcs_frequency_grid</td><td align="center">float</td><td>false</td><td align="center">交流_电网总频率（单位：Hz）</td><td align="center"></td></tr><tr><td align="center">pcs_frequency_phase_a</td><td align="center">float</td><td>false</td><td align="center">交流_A相频率（单位：Hz）</td><td align="center"></td></tr><tr><td align="center">pcs_frequency_phase_b</td><td align="center">float</td><td>false</td><td align="center">交流_B相频率（单位：Hz）</td><td align="center"></td></tr><tr><td align="center">pcs_frequency_phase_c</td><td align="center">float</td><td>false</td><td align="center">交流_C相频率（单位：Hz）</td><td align="center"></td></tr><tr><td align="center">pcs_ac_daily_charge_energy</td><td align="center">float</td><td>false</td><td align="center">交流_日充电量（单位：kWh）</td><td align="center"></td></tr><tr><td align="center">pcs_ac_daily_discharge_energy</td><td align="center">float</td><td>false</td><td align="center">交流_日放电量（单位：kWh）</td><td align="center"></td></tr><tr><td align="center">pcs_ac_charge_accumulated_energy</td><td align="center">float</td><td>false</td><td align="center">交流_总充电电量（单位：kWh）</td><td align="center"></td></tr><tr><td align="center">pcs_ac_discharge_accumulated_energy</td><td align="center">float</td><td>false</td><td align="center">交流_总放电电量（单位：kWh）</td><td align="center"></td></tr><tr><td align="center">pcs_input_power</td><td align="center">float</td><td>false</td><td align="center">直流_功率（单位：kW）</td><td align="center">0.33</td></tr><tr><td align="center">pcs_input_voltage</td><td align="center">float</td><td>false</td><td align="center">直流_电压（单位：V）</td><td align="center">3.4</td></tr><tr><td align="center">pcs_input_current</td><td align="center">float</td><td>false</td><td align="center">直流_电流（单位：A）</td><td align="center">0.35</td></tr><tr><td align="center">pcs_alarm_status</td><td align="center">int</td><td>false</td><td align="center">告警状态<br>0-正常<br>1-告警</td><td align="center"></td></tr><tr><td align="center">pcs_fault_status</td><td align="center">int</td><td>false</td><td align="center">故障状态<br>0-正常<br>1-故障</td><td align="center"></td></tr><tr><td align="center">pcs_grid_voltage_ab</td><td align="center">float</td><td>false</td><td align="center">AB相电网线电压（单位：V）</td><td align="center"></td></tr><tr><td align="center">pcs_grid_voltage_bc</td><td align="center">float</td><td>false</td><td align="center">BC相电网线电压（单位：V）</td><td align="center"></td></tr><tr><td align="center">pcs_grid_voltage_ca</td><td align="center">float</td><td>false</td><td align="center">CA相电网线电压（单位：V）</td><td align="center"></td></tr><tr><td align="center">pcs_internal_temp</td><td align="center">float</td><td>false</td><td align="center">设备内部腔体温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">igbt_temp_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相IGBT温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">igbt_temp_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相IGBT温度（单位：℃）</td><td align="center"></td></tr><tr><td align="center">igbt_temp_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相IGBT温度（单位：℃）</td><td align="center"></td></tr></tbody></table>

### **payload - RegularReportEMS**

<table><thead><tr><th width="178" align="center">参数</th><th width="109" align="center">类型</th><th width="98" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">mode</td><td align="center">int</td><td>false</td><td align="center">运行模式<br>0-本地调试模式<br>1-本地自动模式<br>2-远程被动模式</td><td align="center"></td></tr><tr><td align="center">charge_strategy</td><td align="center">待定</td><td>false</td><td align="center">充放电策略<br>（仅mode为远程时有）</td><td align="center"></td></tr><tr><td align="center">protection_strategy</td><td align="center">待定</td><td>false</td><td align="center">安全保护<br>（仅mode为远程时有）</td><td align="center"></td></tr></tbody></table>

### **payload - EMSData**

<table><thead><tr><th width="178" align="center">参数</th><th width="112" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">total</td><td align="center">EMSDataTotal</td><td>false</td><td align="center">二级EMS汇总</td><td align="center"></td></tr><tr><td align="center">statistics</td><td align="center">[]EMSDataStatistics</td><td>false</td><td align="center">支路下属储能设备运行统计</td><td align="center"></td></tr></tbody></table>

### **payload - EMSDataTotal**

<table><thead><tr><th width="178" align="center">参数</th><th width="224" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">running_status</td><td align="center">int</td><td>false</td><td align="center">运行状态<br>0-未知状态<br>1-停机<br>2-运行</td><td align="center"></td></tr><tr><td align="center">soc</td><td align="center">float</td><td>false</td><td align="center">平均soc</td><td align="center"></td></tr><tr><td align="center">pcs_total_active_power</td><td align="center">float</td><td>false</td><td align="center">当前总有功功率（单位：kW）</td><td align="center"></td></tr><tr><td align="center">pcs_total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">当前总无功功率（单位：kVar）</td><td align="center"></td></tr><tr><td align="center">current_chargeable_energy</td><td align="center">float</td><td>false</td><td align="center">剩余可充电电量（单位：kWh）</td><td align="center"></td></tr><tr><td align="center">current_dischargeable_energy</td><td align="center">float</td><td>false</td><td align="center">剩余可放电电量（单位：kWh）</td><td align="center"></td></tr><tr><td align="center">max_charge_power</td><td align="center">float</td><td>false</td><td align="center">最大可充电功率（单位：kW）</td><td align="center"></td></tr><tr><td align="center">max_discharge_power</td><td align="center">float</td><td>false</td><td align="center">最大可放电功率（单位：kW）</td><td align="center"></td></tr></tbody></table>

### **payload - EMSDataStatistics**

<table><thead><tr><th width="178" align="center">参数</th><th width="133" align="center">类型</th><th width="97" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">ele_meter_id</td><td align="center">int</td><td>false</td><td align="center">电表编号</td><td align="center"></td></tr><tr><td align="center">running_status</td><td align="center">int</td><td>false</td><td align="center">运行状态<br>0-未知状态<br>1-停机<br>2-运行</td><td align="center"></td></tr><tr><td align="center">pcs_total_active_power</td><td align="center">float</td><td>false</td><td align="center">当前总有功功率（单位：kW）</td><td align="center"></td></tr><tr><td align="center">soc</td><td align="center">float</td><td>false</td><td align="center">平均soc</td><td align="center"></td></tr></tbody></table>

### **payload - SubEleMeterData**

<table><thead><tr><th width="180" align="center">参数</th><th width="110" align="center">类型</th><th width="99" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">device_id</td><td align="center">int</td><td>true</td><td align="center">设备ID</td><td align="center">2</td></tr><tr><td align="center">uid</td><td align="center">string</td><td>false</td><td align="center">设备UID</td><td align="center"></td></tr><tr><td align="center">purpose</td><td align="center">int</td><td>true</td><td align="center"><p>电表用途</p><p>1-关口表</p><p>2-计量表</p></td><td align="center">1</td></tr><tr><td align="center">scenario</td><td align="center">int</td><td>false</td><td align="center"><p>适用场景</p><p>1-储能</p><p>2-光伏</p><p>3-充电桩</p></td><td align="center">1</td></tr><tr><td align="center">total_active_power</td><td align="center">float</td><td>false</td><td align="center">总有功功率（单位：kW）</td><td align="center">100.5</td></tr><tr><td align="center">active_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相有功功率（单位：kW）</td><td align="center">101.5</td></tr><tr><td align="center">active_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相有功功率（单位：kW）</td><td align="center">102.5</td></tr><tr><td align="center">active_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相有功功率（单位：kW）</td><td align="center">103.5</td></tr><tr><td align="center">total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">总无功功率（单位：kVar）</td><td align="center">104.5</td></tr><tr><td align="center">reactive_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相无功功率（单位：kVar）</td><td align="center">105.5</td></tr><tr><td align="center">reactive_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相无功功率（单位：kVar）</td><td align="center">106.5</td></tr><tr><td align="center">reactive_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相无功功率（单位：kVar）</td><td align="center">107.5</td></tr><tr><td align="center">total_apparent_power</td><td align="center">float</td><td>false</td><td align="center">总视在功率（单位：kVar）</td><td align="center">108.5</td></tr><tr><td align="center">apparent_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相视在功率（单位：kVA）</td><td align="center">109.5</td></tr><tr><td align="center">apparent_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相视在功率（单位：kVA）</td><td align="center">110.5</td></tr><tr><td align="center">apparent_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相视在功率（单位：kVA）</td><td align="center">111.5</td></tr><tr><td align="center">total_power_factor</td><td align="center">float</td><td>false</td><td align="center">总功率因数</td><td align="center">112.5</td></tr><tr><td align="center">power_factor_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相功率因数</td><td align="center">113.5</td></tr><tr><td align="center">power_factor_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相功率因数</td><td align="center">114.5</td></tr><tr><td align="center">power_factor_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相功率因数</td><td align="center">115.5</td></tr><tr><td align="center">voltage_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相电压（单位：V）</td><td align="center">116.5</td></tr><tr><td align="center">voltage_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相电压（单位：V）</td><td align="center">117.5</td></tr><tr><td align="center">voltage_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相电压（单位：V）</td><td align="center">118.5</td></tr><tr><td align="center">current_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相电流（单位：A）</td><td align="center">119.5</td></tr><tr><td align="center">current_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相电流（单位：A）</td><td align="center">120.5</td></tr><tr><td align="center">current_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相电流（单位：A）</td><td align="center">121.5</td></tr><tr><td align="center">frequency_grid</td><td align="center">float</td><td>false</td><td align="center">电网总频率（单位：Hz）</td><td align="center">122.5</td></tr><tr><td align="center">frequency_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相频率（单位：Hz）</td><td align="center">123.5</td></tr><tr><td align="center">frequency_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相频率（单位：Hz）</td><td align="center">124.5</td></tr><tr><td align="center">frequency_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相频率（单位：Hz）</td><td align="center">125.5</td></tr><tr><td align="center">total_active_energy</td><td align="center">float</td><td>false</td><td align="center">组合有功总电能（单位：kWh）</td><td align="center">125.5</td></tr><tr><td align="center">total_active_energy_1</td><td align="center">float</td><td>false</td><td align="center">组合功费率1电能（单位：kWh）</td><td align="center">125.5</td></tr><tr><td align="center">total_active_energy_2</td><td align="center">float</td><td>false</td><td align="center">组合功费率2电能（单位：kWh）</td><td align="center">125.5</td></tr><tr><td align="center">total_active_energy_3</td><td align="center">float</td><td>false</td><td align="center">组合功费率3电能（单位：kWh）</td><td align="center">125.5</td></tr><tr><td align="center">total_active_energy_4</td><td align="center">float</td><td>false</td><td align="center">组合功费率4电能（单位：kWh）</td><td align="center">125.5</td></tr><tr><td align="center">total_forward_active_energy</td><td align="center">float</td><td>false</td><td align="center">正向有功总电能（单位：kWh）</td><td align="center">126.5</td></tr><tr><td align="center">forward_active_energy_sharp</td><td align="center">float</td><td>false</td><td align="center">正向有功尖电能（单位：kWh）</td><td align="center">127.5</td></tr><tr><td align="center">forward_active_energy_peak</td><td align="center">float</td><td>false</td><td align="center">正向有功峰电能（单位：kWh）</td><td align="center">128.5</td></tr><tr><td align="center">forward_active_energy_flat</td><td align="center">float</td><td>false</td><td align="center">正向有功平电能（单位：kWh）</td><td align="center">129.5</td></tr><tr><td align="center">forward_active_energy_valley</td><td align="center">float</td><td>false</td><td align="center">正向有功谷电能（单位：kWh）</td><td align="center">130.5</td></tr><tr><td align="center">forward_active_energy_1</td><td align="center">float</td><td>false</td><td align="center">正向有功费率1电能（单位：kWh）</td><td align="center">127.5</td></tr><tr><td align="center">forward_active_energy_2</td><td align="center">float</td><td>false</td><td align="center">正向有功费率2电能（单位：kWh）</td><td align="center">128.5</td></tr><tr><td align="center">forward_active_energy_3</td><td align="center">float</td><td>false</td><td align="center">正向有功费率3电能（单位：kWh）</td><td align="center">129.5</td></tr><tr><td align="center">forward_active_energy_4</td><td align="center">float</td><td>false</td><td align="center">正向有功费率4电能（单位：kWh）</td><td align="center">130.5</td></tr><tr><td align="center">total_reverse_active_energy</td><td align="center">float</td><td>false</td><td align="center">反向有功总电能（单位：kWh）</td><td align="center">131.5</td></tr><tr><td align="center">reverse_active_energy_sharp</td><td align="center">float</td><td>false</td><td align="center">反向有功尖电能（单位：kWh）</td><td align="center">132.5</td></tr><tr><td align="center">reverse_active_energy_peak</td><td align="center">float</td><td>false</td><td align="center">反向有功峰电能（单位：kWh）</td><td align="center">133.5</td></tr><tr><td align="center">reverse_active_energy_flat</td><td align="center">float</td><td>false</td><td align="center">反向有功平电能（单位：kWh）</td><td align="center">134.5</td></tr><tr><td align="center">reverse_active_energy_valley</td><td align="center">float</td><td>false</td><td align="center">反向有功谷电能（单位：kWh）</td><td align="center">135.5</td></tr><tr><td align="center">reverse_active_energy_1</td><td align="center">float</td><td>false</td><td align="center">反向有功费率1电能（单位：kWh）</td><td align="center">132.5</td></tr><tr><td align="center">reverse_active_energy_2</td><td align="center">float</td><td>false</td><td align="center">反向有功费率2电能（单位：kWh）</td><td align="center">133.5</td></tr><tr><td align="center">reverse_active_energy_3</td><td align="center">float</td><td>false</td><td align="center">反向有功费率3电能（单位：kWh）</td><td align="center">134.5</td></tr><tr><td align="center">reverse_active_energy_4</td><td align="center">float</td><td>false</td><td align="center">反向有功费率4电能（单位：kWh）</td><td align="center">135.5</td></tr><tr><td align="center">max_demand_forward_active_power</td><td align="center">float</td><td>false</td><td align="center">正向有功最大需量（单位：kVar）</td><td align="center">657</td></tr><tr><td align="center">occurred_time_forward_active</td><td align="center">int</td><td>false</td><td align="center">正向有功最大需量发生时间戳（单位：秒）</td><td align="center">1719398925</td></tr><tr><td align="center">max_demand_reverse_active_power</td><td align="center">float</td><td>false</td><td align="center">反向有功最大需量（单位：kVar）</td><td align="center">342</td></tr><tr><td align="center">occurred_time_reverse_active</td><td align="center">​int</td><td>false</td><td align="center">反向有功最大需量发生时间戳（单位：秒）</td><td align="center">1719398925</td></tr><tr><td align="center">max_demand_forward_reactive_power</td><td align="center">float</td><td>false</td><td align="center">正向无功最大需量（单位：kVar）</td><td align="center">357</td></tr><tr><td align="center">occurred_time_forward_reactive</td><td align="center">int</td><td>false</td><td align="center">正向无功最大需量发生时间戳（单位：秒）</td><td align="center">1719398925</td></tr><tr><td align="center">max_demand_reverse_reactive_power</td><td align="center">float</td><td>false</td><td align="center">反向无功最大需量（单位：kVar）</td><td align="center">342</td></tr><tr><td align="center">occurred_time_reverse_reactive</td><td align="center">int</td><td>false</td><td align="center">反向无功最大需量发生时间戳（单位：秒）</td><td align="center">1719398925</td></tr><tr><td align="center">instantaneous_apparent_power</td><td align="center">float</td><td>false</td><td align="center">实时视在需量（单位：KVA）</td><td align="center">123</td></tr></tbody></table>

### **payload - PhotovoltaicMeterData**&#x20;

_与SubEleMeterData一致_

### **payload - PhotovoltaicInverterData**

| 参数                                          | 类型      | 是否必填 | 描述                                                            | 样例   |
| ------------------------------------------- | ------- | ---- | ------------------------------------------------------------- | ---- |
| direct\_current\_voltage                    | float64 | 否    | 直流侧（DC）电压（V）                                                  | 500  |
| direct\_current\_current                    | float64 | 否    | 直流侧（DC）电流（A）                                                  | 100  |
| alternating\_current\_voltage\_a            | float64 | 否    | 交流侧（AC）A相电压（V）                                                | 230  |
| alternating\_current\_voltage\_b            | float64 | 否    | 交流侧（AC）B相电压（V）                                                | 230  |
| alternating\_current\_voltage\_c            | float64 | 否    | 交流侧（AC）C相电压（V）                                                | 230  |
| alternating\_current\_current\_a            | float64 | 否    | 交流侧（AC）A相电流（A）                                                | 50   |
| alternating\_current\_current\_b            | float64 | 否    | 交流侧（AC）B相电流（A）                                                | 50   |
| alternating\_current\_current\_c            | float64 | 否    | 交流侧（AC）C相电流（A）                                                | 50   |
| direct\_current\_input\_power               | float64 | 否    | 直流输入功率（kW）                                                    | 50   |
| alternating\_current\_output\_power         | float64 | 否    | 交流输出功率（kW）                                                    | 45   |
| total\_active\_power                        | float64 | 否    | 有功功率（kW）                                                      | 40   |
| total\_reactive\_power                      | float64 | 否    | 无功功率（kVar）                                                    | 10   |
| alternating\_current\_output\_frequency     | float64 | 否    | 交流输出频率（Hz）                                                    | 50   |
| inverter\_efficiency                        | float64 | 否    | 逆变器效率                                                         | 98.5 |
| inverter\_internal\_temp                    | float64 | 否    | 逆变器内部温度（℃）                                                    | 45   |
| inverter\_heatsink\_temp                    | float64 | 否    | 散热器温度（℃）                                                      | 50   |
| running\_status                             | int     | 否    | <p>当前运行状态 </p><p>1-停机 </p><p>2-待机 </p><p>5-运行 </p><p>7-故障</p> | 1    |
| fault\_status                               | int     | 否    | 故障代码                                                          | 0    |
| alternating\_current\_output\_power\_factor | float64 | 否    | 交流输出功率因数                                                      | 0.95 |
| ambient\_temp                               | float64 | 否    | 环境温度（℃）                                                       | 30   |
| irradiance                                  | float64 | 否    | 辐射强度（W/m²）                                                    | 800  |

### **payload - AlternatingChargePailData**

<table><thead><tr><th width="180" align="center">参数</th><th width="110" align="center">类型</th><th width="99" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">total_active</td><td align="center">float</td><td>false</td><td align="center">总有功功率（单位：kW）</td><td align="center">100.5</td></tr><tr><td align="center">active_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相有功功率（单位：kW）</td><td align="center">101.5</td></tr><tr><td align="center">active_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相有功功率（单位：kW）</td><td align="center">102.5</td></tr><tr><td align="center">active_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相有功功率（单位：kW）</td><td align="center">103.5</td></tr><tr><td align="center">total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">总无功功率（单位：kVar）</td><td align="center">104.5</td></tr><tr><td align="center">reactive_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相无功功率（单位：kVar）</td><td align="center">105.5</td></tr><tr><td align="center">reactive_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相无功功率（单位：kVar）</td><td align="center">106.5</td></tr><tr><td align="center">reactive_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相无功功率（单位：kVar）</td><td align="center">107.5</td></tr><tr><td align="center">total_apparent_power</td><td align="center">float</td><td>false</td><td align="center">总视在功率（单位：kVar）</td><td align="center">108.5</td></tr><tr><td align="center">apparent_power_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相视在功率（单位：kVA）</td><td align="center">109.5</td></tr><tr><td align="center">apparent_power_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相视在功率（单位：kVA）</td><td align="center">110.5</td></tr><tr><td align="center">apparent_power_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相视在功率（单位：kVA）</td><td align="center">111.5</td></tr><tr><td align="center">total_power_factor</td><td align="center">float</td><td>false</td><td align="center">总功率因数</td><td align="center">112.5</td></tr><tr><td align="center">power_factor_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相功率因数</td><td align="center">113.5</td></tr><tr><td align="center">power_factor_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相功率因数</td><td align="center">114.5</td></tr><tr><td align="center">power_factor_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相功率因数</td><td align="center">115.5</td></tr><tr><td align="center">a_phase_voltage</td><td align="center">float</td><td>false</td><td align="center">A相电压（单位：V）</td><td align="center">116.5</td></tr><tr><td align="center">b_phase_voltage</td><td align="center">float</td><td>false</td><td align="center">B相电压（单位：V）</td><td align="center">117.5</td></tr><tr><td align="center">c_phase_voltage</td><td align="center">float</td><td>false</td><td align="center">C相电压（单位：V）</td><td align="center">118.5</td></tr><tr><td align="center">a_phase_current</td><td align="center">float</td><td>false</td><td align="center">A相电流（单位：A）</td><td align="center">119.5</td></tr><tr><td align="center">b_phase_current</td><td align="center">float</td><td>false</td><td align="center">B相电流（单位：A）</td><td align="center">120.5</td></tr><tr><td align="center">c_phase_current</td><td align="center">float</td><td>false</td><td align="center">C相电流（单位：A）</td><td align="center">121.5</td></tr><tr><td align="center">frequency_grid</td><td align="center">float</td><td>false</td><td align="center">电网总频率（单位：Hz）</td><td align="center">122.5</td></tr><tr><td align="center">frequency_phase_a</td><td align="center">float</td><td>false</td><td align="center">A相频率（单位：Hz）</td><td align="center">123.5</td></tr><tr><td align="center">frequency_phase_b</td><td align="center">float</td><td>false</td><td align="center">B相频率（单位：Hz）</td><td align="center">124.5</td></tr><tr><td align="center">frequency_phase_c</td><td align="center">float</td><td>false</td><td align="center">C相频率（单位：Hz）</td><td align="center">125.5</td></tr><tr><td align="center">total_electric_energy</td><td align="center">float</td><td>false</td><td align="center">累计并入电网总电能）</td><td align="center">123.5</td></tr><tr><td align="center">current_electric_energy</td><td align="center">float</td><td>false</td><td align="center">当前并入电网电能</td><td align="center">123.5</td></tr></tbody></table>

### **payload - DirectChargePailData**

<table><thead><tr><th width="180" align="center">参数</th><th width="110" align="center">类型</th><th width="99" data-type="checkbox">是否必填</th><th align="center">描述</th><th align="center">样例</th></tr></thead><tbody><tr><td align="center">input_power</td><td align="center">float</td><td>false</td><td align="center">输入功率</td><td align="center">100.5</td></tr><tr><td align="center">output_power</td><td align="center">float</td><td>false</td><td align="center">输出功率</td><td align="center">101.5</td></tr><tr><td align="center">input_voltage</td><td align="center">float</td><td>false</td><td align="center">输入电压</td><td align="center">102.5</td></tr><tr><td align="center">output_voltage</td><td align="center">float</td><td>false</td><td align="center">输出电压</td><td align="center">103.5</td></tr><tr><td align="center">input_current</td><td align="center">float</td><td>false</td><td align="center">输入电流</td><td align="center">104.5</td></tr><tr><td align="center">output_current</td><td align="center">float</td><td>false</td><td align="center">输出电流</td><td align="center">105.5</td></tr><tr><td align="center">total_apparent_power</td><td align="center">float</td><td>false</td><td align="center">总视在功率（单位：kVar）</td><td align="center">108.5</td></tr><tr><td align="center">total_power_factor</td><td align="center">float</td><td>false</td><td align="center">总功率因数</td><td align="center">112.5</td></tr><tr><td align="center">total_electric_energy</td><td align="center">float</td><td>false</td><td align="center">累计充电电量</td><td align="center">113.5</td></tr><tr><td align="center">current_electric_energy</td><td align="center">float</td><td>false</td><td align="center">当前充电电量</td><td align="center">114.5</td></tr><tr><td align="center">total_active</td><td align="center">float</td><td>false</td><td align="center">总有功功率</td><td align="center">114.5</td></tr><tr><td align="center">total_reactive_power</td><td align="center">float</td><td>false</td><td align="center">总无功功率</td><td align="center">115.5</td></tr><tr><td align="center">a_phase_voltage</td><td align="center">float</td><td>false</td><td align="center">A相电压（单位：V）</td><td align="center">116.5</td></tr><tr><td align="center">b_phase_voltage</td><td align="center">float</td><td>false</td><td align="center">B相电压（单位：V）</td><td align="center">117.5</td></tr><tr><td align="center">c_phase_voltage</td><td align="center">float</td><td>false</td><td align="center">C相电压（单位：V）</td><td align="center">118.5</td></tr><tr><td align="center">frequency_grid</td><td align="center">float</td><td>false</td><td align="center">电网总频率（单位：Hz）</td><td align="center">122.5</td></tr></tbody></table>

### **payload - PailEleMeterData**

_**SubEleMeterData一致**_

### **Payload示例 - sub\_ems\_fire和sub\_ems\_aircon/sub\_ems\_liquidcon组合数据**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "085be8f4-2f7b-488d-8a93-d0c7dcd7f033",
    "mid": "044b29cf-565e-434d-82a6-364411af6a71",
    "type": "report_regular",
    "sub_device_id": 2,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705980251899,
    "data": [{
        "type": "sub_ems_fire",
        "index": 0,
        "data": {
            "fire_status": 1,
        }
    },{
        "type": "sub_ems_aircon", // "sub_ems_aircon" / "sub_ems_liquidcon"
        "index": 0,
        "data": {
            "machine_status": 1,
            "cooling_status": 1,
            "heating_status": 1,
            "outdoor_temp": 20.7,
            "coil_temp": 26.9,
            "indoor_temp": 28.4,
            "exhaust_temp": 22.1,
            "cooling_point": 16.2,
            "heating_point": 28.5
        }        
    }]
}
```
{% endcode %}

### **Payload示例 - sub\_ems\_bms**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "085be8f4-2f7b-488d-8a93-d0c7dcd7f033",
    "mid": "044b29cf-565e-434d-82a6-364411af6a71",
    "type": "report_regular",
    "sub_device_id": 2,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705980251899,
    "data": [{
        "type": "sub_ems_bms",
        "index": 0,
        "data": {
            "running_status": 1,
            "soc": 80,
            "soh": 90,
            "current_chargeable_energy": 1000,
            "current_dis_chargeable_energy": 2000,
            "total_voltage": 400,
            "total_current": -10,
            "power": 4000,
            "charge_accumulated_energy": 100000,
            "discharge_accumulated_energy": 50000,
            "daily_charge_energy": 100,
            "daily_discharge_energy": 50,
            "max_allowed_charge_power": 5000,
            "max_allowed_discharge_power": 3000,
            "max_allowed_charge_current": 200,
            "max_allowed_dis_charge_current": 100,
            "highest_cell_voltage": 4200,
            "highest_voltage_id_cell": 3,
            "lowest_cell_voltage": 4100,
            "lowest_voltage_id_cell": 5,
            "average_cell_voltage": 4150,
            "highest_cell_temp": 40,
            "highest_temp_id": 4,
            "lowest_cell_temp": -5,
            "lowest_temp_id": 6,
            "average_cell_temperature": 20,
            "cell_voltage_range": 100,
            "cell_temperature_range": 45,
            "cell_voltage": [4150,4130,4110...], // 数组长度固定为700
            "cell_temp": [20,23,21...] // 数组长度固定为700
        }
    },{
        "type": "sub_ems_bms",
        "index": 1,
        "data": {
            "running_status": 1,
            "soc": 80,
            "soh": 90,
            "current_chargeable_energy": 1000,
            "current_dis_chargeable_energy": 2000,
            "total_voltage": 400,
            "total_current": -10,
            "power": 4000,
            "charge_accumulated_energy": 100000,
            "discharge_accumulated_energy": 50000,
            "daily_charge_energy": 100,
            "daily_discharge_energy": 50,
            "max_allowed_charge_power": 5000,
            "max_allowed_discharge_power": 3000,
            "max_allowed_charge_current": 200,
            "max_allowed_dis_charge_current": 100,
            "highest_cell_voltage": 4200,
            "highest_voltage_id_cell": 3,
            "lowest_cell_voltage": 4100,
            "lowest_voltage_id_cell": 5,
            "average_cell_voltage": 4150,
            "highest_cell_temp": 40,
            "highest_temp_id": 4,
            "lowest_cell_temp": -5,
            "lowest_temp_id": 6,
            "average_cell_temperature": 20,
            "cell_voltage_range": 100,
            "cell_temperature_range": 45,
            "cell_voltage": [4150,4130,4110...], // 数组长度固定为700
            "cell_temp": [20,23,21...] // 数组长度固定为700
        }
    }]
}
```
{% endcode %}

### **Payload示例 - sub\_ems\_pcs**

{% code lineNumbers="true" %}
```json
{
    "trace_id": "085be8f4-2f7b-488d-8a93-d0c7dcd7f033",
    "mid": "044b29cf-565e-434d-82a6-364411af6a71",
    "type": "report_regular",
    "sub_device_id": 2,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705980251899,
    "data": [{
        "type": "sub_ems_pcs",
        "index": 0,
        "data": {
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
        }
    }]
}
```
{% endcode %}

### **Payload示例 - ems**

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

### **Payload示例 - sub\_elemeter**

```json
{
    "trace_id": "2f492a12-5408-40b3-b347-ed64a3723050",
    "mid": "d39835f5-2087-4601-8a12-85bb2bceb690",
    "type": "report_regular",
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705563840345,
    "data": [
        {
            "type": "sub_elemeter",
            "index": 0,
            "data": {
                "device_id": 1,
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
                "total_active_energy": 234.1,
                "total_active_energy_1": 234.1,
                "total_active_energy_2": 234.1,
                "total_active_energy_3": 234.1,
                "total_active_energy_4": 234.1,
                "total_forward_active_energy": 126.5,
                "forward_active_energy_1": 0,
                "forward_active_energy_2": 123.8,
                "forward_active_energy_3": 424,
                "forward_active_energy_4": 436.4,
                "total_reverse_active_energy": 134.4,
                "reverse_active_energy_1": 0,
                "reverse_active_energy_2": 123.6,
                "reverse_active_energy_3": 235.8,
                "reverse_active_energy_4": 134,
                "max_demand_forward_active_power": 124,
                "occurred_time_forward_active": 1720752678,
                "max_demand_reverse_active_power": 2343,
                "occurred_time_reverse_active": 1720752678,
                "max_demand_forward_reactive_power": 432,
                "occurred_time_forward_reactive": 1720752678,
                "max_demand_reverse_reactive_power": 563,
                "occurred_time_reverse_reactive": 1720752678,
                "instantaneous_apparent_power": 234
            }
        }
    ]
}
```

### **Payload示例 -** photovoltaic\_elemeter

```json
{
    "trace_id": "144d6384-c32a-4221-ad44-5d0063128441",
    "mid": "f76612ce-b8aa-4bab-8138-7e7fc74bcbcf",
    "type": "report_regular",
    "sub_device_id": 1,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1721180810009,
    "data": [
        {
            "type": "photovoltaic_meter",
            "index": 0,
            "data": {
                "total_active_power": 2359.333,
                "active_power_phase_a": 1966.111,
                "active_power_phase_b": 2097.185,
                "active_power_phase_c": 2228.259,
                "total_reactive_power": 2883.629,
                "reactive_power_phase_a": 2490.407,
                "reactive_power_phase_b": 2621.481,
                "reactive_power_phase_c": 2752.555,
                "total_apparent_power": 3407.925,
                "apparent_power_phase_a": 3014.703,
                "apparent_power_phase_b": 3145.777,
                "apparent_power_phase_c": 3276.851,
                "total_power_factor": 0.057,
                "power_factor_phase_a": 0.054,
                "power_factor_phase_b": 0.055,
                "power_factor_phase_c": 0.056,
                "voltage_phase_a": 2,
                "voltage_phase_b": 2.1,
                "voltage_phase_c": 2.2,
                "current_phase_a": 0.26,
                "current_phase_b": 0.27,
                "current_phase_c": 0.28,
                "frequency_grid": 0.59,
                "frequency_phase_a": null,
                "frequency_phase_b": null,
                "frequency_phase_c": null,
                "total_active_energy": null,
                "total_active_energy_1": null,
                "total_active_energy_2": null,
                "total_active_energy_3": null,
                "total_active_energy_4": null,
                "total_forward_active_energy": 0.99,
                "forward_active_energy_sharp": 271978.56,
                "forward_active_energy_peak": 273289.3,
                "forward_active_energy_flat": 274600.04,
                "forward_active_energy_valley": 275910.78,
                "forward_active_energy_1": 271978.56,
                "forward_active_energy_2": 273289.3,
                "forward_active_energy_3": 274600.04,
                "forward_active_energy_4": 275910.78,
                "total_reverse_active_energy": 0.88,
                "reverse_active_energy_sharp": 277221.52,
                "reverse_active_energy_peak": 278532.26,
                "reverse_active_energy_flat": 279843,
                "reverse_active_energy_valley": 281153.74,
                "reverse_active_energy_1": 277221.52,
                "reverse_active_energy_2": 278532.26,
                "reverse_active_energy_3": 279843,
                "reverse_active_energy_4": 281153.74
            }
        }
    ]
}
```

### **Payload示例 -** photovoltaic\_inverter

<pre class="language-json"><code class="lang-json"><strong>{
</strong><strong>    "trace_id": "d882e331-ba8b-4b7a-8ab7-0690786844c8",
</strong>    "mid": "b15d71d6-48f5-4aeb-83e8-2dc828a75701",
    "type": "report_regular",
    "sub_device_id": 1,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1721119850008,
    "data": [
        {
            "type": "photovoltaic_inverter",
            "index": 0,
            "data": {
                "alternating_current_voltage_a": 77.2,
                "alternating_current_voltage_b": 77.3,
                "alternating_current_voltage_c": 77.4,
                "alternating_current_current_a": 77.5,
                "alternating_current_current_b": 77.6,
                "alternating_current_current_c": 77.7,
                "direct_current_voltage": 79.6,
                "direct_current_current": null,
                "direct_current_input_power": null,
                "alternating_current_output_power": 55706.451,
                "total_active_power": null,
                "total_reactive_power": 58524.542,
                "alternating_current_output_frequency": 6671666.7,
                "inverter_efficiency": null,
                "inverter_internal_temp": 78.3,
                "inverter_heatsink_temp": null,
                "running_status": 0,
                "fault_status": 785,
                "alternating_current_output_power_factor": 0.886,
                "ambient_temp": null,
                "irradiance": null
            }
        }
    ]
}
</code></pre>

### **Payload示例 -** alternating\_pail

```json
{
    "trace_id": "d882e331-ba8b-4b7a-8ab7-0690786844c8",
    "mid": "b15d71d6-48f5-4aeb-83e8-2dc828a75701",
    "type": "report_regular",
    "sub_device_id": 1,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1721119850008,
    "data": [
        {
            "type": "alternating_pail",
            "index": 0,
            "data": {
                    "a_phase_voltage": 1.1,
                    "b_phase_voltage": 2.2,
                    "c_phase_voltage": 3.3,
                    "a_phase_current": 0.44,
                    "b_phase_current": 0.55,
                    "c_phase_current": 0.66,
                    "total_active": 50,
                    "active_power_phase_a": 0.099,
                    "active_power_phase_b": 0.099,
                    "active_power_phase_c": 0.099,
                    "total_reactive_power": 0.123,
                    "reactive_power_phase_a": 0.099,
                    "reactive_power_phase_b": 0.099,
                    "reactive_power_phase_c": 0.099,
                    "total_apparent_power": 0.234,
                    "apparent_power_phase_a": 0.099,
                    "apparent_power_phase_b": 0.099,
                    "apparent_power_phase_c": 0.099,
                    "total_power_factor": 8.88,
                    "power_factor_phase_a": 5.55,
                    "power_factor_phase_b": 6.66,
                    "power_factor_phase_c": 7.77,
                    "frequency_grid": 50,
                    "frequency_phase_a": null,
                    "frequency_phase_b": null,
                    "frequency_phase_c": null,
                    "total_electric_energy": 0,
                    "current_electric_energy": 0
            }
        }
    ]
}
```

### **Payload示例 -** direct\_pail

```json
{
    "trace_id": "d882e331-ba8b-4b7a-8ab7-0690786844c8",
    "mid": "b15d71d6-48f5-4aeb-83e8-2dc828a75701",
    "type": "report_regular",
    "sub_device_id": 1,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1721119850008,
    "data": [
        {
            "type": "direct_pail",
            "index": 0,
            "data": {
                    "input_power": 0,
                    "output_power": 0,
                    "input_voltage": 0,
                    "output_voltage": 0,
                    "input_current": 0,
                    "output_current": 0,
                    "a_phase_voltage": 0,
                    "b_phase_voltage": 0,
                    "c_phase_voltage": 0,
                    "total_electric_energy": 0,
                    "current_electric_energy": 0,
                    "frequency_grid": 0,
                    "total_active": 0,
                    "total_reactive_power": null,
                    "total_apparent_power": null,
                    "total_power_factor": null
            }
        }
    ]
}
```

### **Payload示例 -** pail\_meter

```json

{
    "trace_id": "085be8f4-2f7b-488d-8a93-d0c7dcd7f033",
    "mid": "044b29cf-565e-434d-82a6-364411af6a71",
    "type": "report_regular",
    "sub_device_id": 1,
    "device_uid": "xxxxxxxxxx",
    "timestamp": 1705980251899,
    "data": [
        {
            "type": "pail_meter",
            "index": 0,
            "data": {
                "total_active_power": 0.285,
                "active_power_phase_a": 0.11,
                "active_power_phase_b": 0.105,
                "active_power_phase_c": 0.065,
                "total_reactive_power": 0.11,
                "reactive_power_phase_a": 0,
                "reactive_power_phase_b": 0,
                "reactive_power_phase_c": 0.11,
                "total_apparent_power": 0.35,
                "apparent_power_phase_a": 0.11,
                "apparent_power_phase_b": 0.11,
                "apparent_power_phase_c": 0.13,
                "total_power_factor": 0.187,
                "power_factor_phase_a": 1,
                "power_factor_phase_b": 1,
                "power_factor_phase_c": 0.503,
                "voltage_phase_a": 230.1,
                "voltage_phase_b": 230.5,
                "voltage_phase_c": 230.3,
                "current_phase_a": 0,
                "current_phase_b": 0,
                "current_phase_c": 0,
                "frequency_grid": 50,
                "total_active_energy": 25197.5,
                "total_active_energy_1": 0,
                "total_active_energy_2": 0,
                "total_active_energy_3": 0,
                "total_forward_active_energy": 14318.5,
                "forward_active_energy_1": 11,
                "forward_active_energy_2": 10.5,
                "forward_active_energy_3": 13.5,
                "total_reverse_active_energy": 10879,
                "reverse_active_energy_1": 1160,
                "reverse_active_energy_2": 1160.5,
                "reverse_active_energy_3": 1164
            }
        }
    ]
}
```
