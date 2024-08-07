# 更新记录

## 2024.03.15

* 更新接口
  * [一级EMS充放电策略](api/http/emu-v1.0/charge-strategy.md)settings由原来8个增加到12个

## 2024.03.14

* 更新接口
  * [二级EMS充放电策略](api/mqtt/level-2-ems/charge-strategy.md)创建后返回策略ID

## 2024.03.13

* 更新接口
  * [二级EMS充放电策略](api/mqtt/level-2-ems/charge-strategy.md)支持按日配置

## 2024.03.11

* 更新接口
  * [二级EMS充放电策略](api/mqtt/level-2-ems/charge-strategy.md)新增`apply_to_all`字段

## 2024.03.08

* 更新接口
  * [二级EMS充放电策略](api/mqtt/level-2-ems/charge-strategy.md)时间区间
  * 电表相关接口英文名统一为`elemeter`
* 新增接口
  * [二级EMS电表设备信息](api/mqtt/level-2-ems/sub-elemeter.md)相关接口

## 2024.03.01

* 新增接口
  * [二级EMS](api/mqtt/level-2-ems/)相关接口

## 2024.01.02

* 新增接口
  * [实时获取](api/http/emu-v1.0/common-sync.md)相关接口

## 2023.11.28

* 更新接口
  * [设备事件](api/mqtt/emu/device-event.md)系数处理

## 2023.11.21

* 新增接口
  * [PCS控制](api/http/emu-v1.0/pcs-control.md)相关接口
  * [BMS控制](api/http/emu-v1.0/bms-control.md)相关接口
* 更新接口
  * [保护策略](api/http/emu-v1.0/protection-strategy.md)chargeDepth新增`charge_max_vol`、`discharge_min_vol`字段
