作业告警表: 风险作业数据
CREATE TABLE `zy_alarm` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `alarm_source` varchar(255) DEFAULT NULL COMMENT '告警来源：DW_DEVICE 定位设备监测 XS_UAV 无人机巡视',
  `begin_time` datetime DEFAULT NOT NULL COMMENT '开始时间（发生时间）',
  `end_time` datetime DEFAULT NOT NULL, '不允许为NULL'
  `e_point_id` int(11) DEFAULT NULL,
  `project_name` varchar(125) DEFAULT NULL COMMENT '项目名称及包段名称，如：西安东-安康750千伏线路工程/包1西安蓝田段、古贤～西安东750千伏线路工程/包12',
  `alarm_level` int(11) DEFAULT NULL COMMENT '报警等级：1 低风险   2 中风险   3 高风险'
) ENGINE=InnoDB AUTO_INCREMENT=5051 DEFAULT CHARSET=utf8mb4;

-----
设备信息表: 车辆等设备信息-运动轨迹
CREATE TABLE `sb_device` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `device_code` varchar(255) DEFAULT NULL COMMENT '设备编码',
  `name` varchar(255) DEFAULT NULL COMMENT '设备名称',
  `type` varchar(255) DEFAULT NULL COMMENT '设备类型 01 车辆 02 人在感知 03 工器具',
  `status` varchar(255) DEFAULT NULL COMMENT '设备状态',
  `support_position_upload` char(1) DEFAULT NULL COMMENT '支持位置上报  Y支持   N不支持',
  `support_short_message` char(1) DEFAULT NULL COMMENT '支持短报文上报 Y支持  N不支持',
  `license_plate` varchar(20) DEFAULT NULL COMMENT '车牌号'
) ENGINE=InnoDB AUTO_INCREMENT=47 DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='设备信息表';

-----
设备定位信息表: 设备定位信息-运动轨迹
CREATE TABLE `sb_position` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `device_code` varchar(255) DEFAULT NULL COMMENT '设备编码',
  `device_type` varchar(56) DEFAULT NULL COMMENT '设备类型 01 车辆 02 人在感知 03 工器具',
  `longitude` double DEFAULT NULL COMMENT '经度',
  `latitude` double DEFAULT NULL COMMENT '纬度',
  `altitude` double(255,0) DEFAULT NULL COMMENT '高程',
  `trigger_time` datetime DEFAULT NULL COMMENT '触发时间'
) ENGINE=InnoDB AUTO_INCREMENT=30767 DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='设备定位信息';