CREATE TABLE `ads_prj_rjh_workplanday_di_code` (
  `work_plan_id` varchar(64) NOT NULL COMMENT '作业计划ID',
  `work_plan_code_day` varchar(100) DEFAULT NULL COMMENT '计划编号',
  `work_plan_name` text COMMENT '计划名称',
  `mainsend` varchar(100) DEFAULT NULL COMMENT '报送单位',
  `mainsend_id` varchar(64) DEFAULT NULL COMMENT '报送单位ID',
  `substation_name` varchar(1500) DEFAULT NULL COMMENT '变电站/线路名称',
  `substation_id` varchar(64) DEFAULT NULL COMMENT '变电站/线路ID',
  `voltage_level` varchar(10) DEFAULT NULL COMMENT '电压等级',
  `work_type` varchar(10) DEFAULT NULL COMMENT '作业类型',
  `work_state` varchar(10) DEFAULT NULL COMMENT '计划执行状态',
  `power_cut` varchar(10) DEFAULT NULL COMMENT '是否停电(01 是 02 否)',
  `live_work_flag` varchar(10) DEFAULT NULL COMMENT '是否带电作业（01 是 02 否）',
  `begin_time` datetime DEFAULT NULL COMMENT '计划开工时间',
  `end_time` datetime DEFAULT NULL COMMENT '计划结束时间',
  `workcontents` text COMMENT '作业内容',
  `work_place` varchar(2000) DEFAULT NULL COMMENT '作业地点',
  `work_place_reference` varchar(500) DEFAULT NULL COMMENT '重点参照物',
  `longitude` varchar(50) DEFAULT NULL COMMENT '经度',
  `latitude` varchar(50) DEFAULT NULL COMMENT '纬度',
  `work_org` varchar(100) DEFAULT NULL COMMENT '作业单位',
  `work_org_id` varchar(64) DEFAULT NULL COMMENT '作业单位ID',
  `majorworker_num` varchar(10) DEFAULT NULL COMMENT '主业单位作业人数',
  `outworker_num` varchar(10) DEFAULT NULL COMMENT '外包单位作业人数',
  `industrialworker_num` varchar(10) DEFAULT NULL COMMENT '产业单位作业人数',
  `work_manager` varchar(100) DEFAULT NULL COMMENT '工作负责人',
  `work_manager_id` varchar(64) DEFAULT NULL COMMENT '工作负责人ID',
  `work_manager_contact` varchar(256) DEFAULT NULL COMMENT '工作负责人联系方式',
  `enter_people_name_province` varchar(200) DEFAULT NULL COMMENT '省级到岗到位人员',
  `enter_people_name_province_id` varchar(200) DEFAULT NULL COMMENT '省级到岗到位人员ID',
  `enter_people_name_city` varchar(200) DEFAULT NULL COMMENT '市级到岗到位人员',
  `enter_people_name_city_id` varchar(200) DEFAULT NULL COMMENT '市级到岗到位人员ID',
  `enter_people_name_county` varchar(200) DEFAULT NULL COMMENT '县级到岗到位人员',
  `enter_people_name_county_id` varchar(200) DEFAULT NULL COMMENT '县级到岗到位人员ID',
  `construction_org` varchar(200) DEFAULT NULL COMMENT '施工单位',
  `construction_org_id` varchar(64) DEFAULT NULL COMMENT '施工单位ID',
  `subcontract_org` varchar(1500) DEFAULT NULL COMMENT '分包单位',
  `subcontract_nature` varchar(10) DEFAULT NULL COMMENT '分包单位性质',
  `subcontract_org_id` varchar(1000) DEFAULT NULL COMMENT '分包单位ID',
  `supervisororg` varchar(100) DEFAULT NULL COMMENT '监理单位',
  `supervisororg_id` varchar(64) DEFAULT NULL COMMENT '监理单位ID',
  `workrisk_level` varchar(10) DEFAULT NULL COMMENT '作业风险等级',
  `gridrisk_level` varchar(10) DEFAULT NULL COMMENT '电网风险等级',
  `week_work_plan_id` varchar(128) DEFAULT NULL COMMENT '关联周计划ID',
  `project_name` varchar(64) DEFAULT NULL COMMENT '项目名称',
  `project_id` varchar(64) DEFAULT NULL COMMENT '项目ID',
  `create_time` datetime NOT NULL COMMENT '创建时间',
  `update_time` datetime DEFAULT NULL COMMENT '更新时间',
  `datafill_org` varchar(100) DEFAULT NULL COMMENT '数据填报单位',
  `datafill_org_id` varchar(64) DEFAULT NULL COMMENT '数据填报单位ID',
  `datareport_org` varchar(100) DEFAULT NULL COMMENT '数据上报单位',
  `datareport_org_id` varchar(64) DEFAULT NULL COMMENT '数据上报单位ID',
  `datacommon_id` varchar(64) DEFAULT NULL COMMENT '同一条数据公共ID',
  `province_code` varchar(16) DEFAULT NULL COMMENT '省编码',
  `city_code` varchar(16) DEFAULT NULL COMMENT '市编码',
  `date_indexs` varchar(20) DEFAULT NULL COMMENT '时间索引',
  `inspect_manage_man_id` varchar(64) DEFAULT NULL COMMENT '勘察负责人id',
  `inspectman_id` varchar(64) DEFAULT NULL COMMENT '勘察管理人id',
  `survey_status` varchar(10) DEFAULT NULL COMMENT '勘察状态',
  `wrok_plan_type` varchar(10) DEFAULT NULL COMMENT '计划来源',
  `video_bond_time` varchar(10) DEFAULT NULL COMMENT '布控球开机时间',
  `is_temporary` char(10) DEFAULT NULL COMMENT '是否临时抢修计划（0：临时抢修计划，1：日计划 ）',
  `manage_dep` varchar(100) DEFAULT NULL COMMENT '专业管理部门',
  `cancel_reason` varchar(1000) DEFAULT NULL COMMENT '取消原因',
  `supervise_type` varchar(20) DEFAULT NULL COMMENT '是否督查',
  `real_begin_time` datetime DEFAULT NULL COMMENT '实际开工时间',
  `real_end_time` datetime DEFAULT NULL COMMENT '实际完工时间',
  `title` varchar(100) DEFAULT NULL COMMENT '工作票id',
  `pw_work_type` varchar(10) DEFAULT NULL COMMENT '配网作业类型',
  `is_multi_contents` varchar(10) DEFAULT NULL COMMENT '是否多地点作业',
  `entr_time` time DEFAULT NULL COMMENT '入场时间',
  `left_time` time DEFAULT NULL COMMENT '离场时间',
  `point_code` varchar(500) DEFAULT NULL COMMENT '坐标点',
  PRIMARY KEY (`work_plan_id`,`create_time`),
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `bd_org` (
  `isc_id` varchar(255) NOT NULL,
  `bmmc` varchar(255) DEFAULT NULL COMMENT '部门名称',
  `bmxz` varchar(255) DEFAULT NULL COMMENT '部门性质',
  `bmbm` varchar(255) DEFAULT NULL COMMENT '部门编码',
  `sjbm_id` varchar(255) DEFAULT NULL COMMENT '上级部门id',
  `xssx` int(11) DEFAULT NULL COMMENT '显示顺序',
  `cjsj` datetime DEFAULT NULL COMMENT '创建时间',
  `tbsj` datetime DEFAULT NULL COMMENT '同步时间',
  `cxsj` datetime DEFAULT NULL COMMENT '撤销时间',
  `sfyx` int(11) DEFAULT NULL COMMENT '数据有效性',
  `ssws_id` varchar(255) DEFAULT NULL COMMENT '所属网省id',
  `ssds_id` varchar(255) DEFAULT NULL COMMENT '所属地市id',
  `ssgd_id` varchar(255) DEFAULT NULL COMMENT '所属供电公司id',
  `dwjb` varchar(255) DEFAULT NULL COMMENT '单位级别',
  `path` varchar(1000) DEFAULT NULL COMMENT '组织全路径',
  `path_id` varchar(1000) DEFAULT NULL COMMENT '组织全路径id',
  `ssywdw_id` varchar(255) DEFAULT NULL COMMENT '所属运维单位id',
  `zzjgqc` varchar(255) DEFAULT NULL COMMENT '组织机构全称',
  `sjbmmc` varchar(255) DEFAULT NULL COMMENT '上级部门名称',
  `sswsmc` varchar(255) DEFAULT NULL COMMENT '所属网省名称',
  `ssdsmc` varchar(255) DEFAULT NULL COMMENT '所属地市名称',
  `ssgdmc` varchar(255) DEFAULT NULL COMMENT '所属供电公司名称',
  `ssywdwmc` varchar(255) DEFAULT NULL COMMENT '所属运维单位名称',
  `sfcx` int(11) DEFAULT NULL COMMENT '是否撤销',
  `extend_field_update_time` datetime DEFAULT NULL COMMENT '从中台导出时间',
  `create_time` datetime DEFAULT NULL COMMENT '创建时间',
  `update_time` datetime DEFAULT NULL COMMENT '更新时间',
  `extend_type` int(11) DEFAULT NULL COMMENT '扩展类型，1 省公司信通审批处室  2 省公司数字化部审批处室  3 省公司专业部门审批处室  4 地市数字化专业部门审批处室  5 当前单位审批部门',
  PRIMARY KEY (`isc_id`) USING BTREE,
  KEY `bd_org_isc_id_IDX` (`isc_id`) USING BTREE,
  KEY `bd_org_bmxz_IDX` (`bmxz`) USING BTREE,
  KEY `bd_org_ssws_id_IDX` (`ssws_id`) USING BTREE,
  KEY `bd_org_dwjb_IDX` (`dwjb`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC;

-----

CREATE TABLE `e_point` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `project` varchar(255) DEFAULT NULL COMMENT '项目',
  `longitude` double DEFAULT NULL COMMENT '经度',
  `latitude` double DEFAULT NULL COMMENT '纬度',
  `point_code` varchar(56) DEFAULT NULL COMMENT '点位编码',
  `remark` varchar(255) DEFAULT NULL,
  `geo_point` point DEFAULT NULL COMMENT '坐标',
  `sort` int(5) DEFAULT NULL COMMENT '杆塔顺序',
  PRIMARY KEY (`id`),
  KEY `e_point_project_IDX` (`project`) USING BTREE,
  KEY `e_point_point_code_IDX` (`point_code`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=14704 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `e_point_code` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `project` varchar(255) DEFAULT NULL COMMENT '项目',
  `point_code_` varchar(56) DEFAULT NULL COMMENT '点位编码',
  `project_code` varchar(255) DEFAULT NULL COMMENT '包段编码',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=14328 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `e_point_uav_resource` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `uav_resource_id` varchar(125) DEFAULT NULL COMMENT '无人机资源id',
  `e_point_id` varchar(125) DEFAULT NULL COMMENT 'e基建原始坐标点位',
  `plan_id` varchar(125) DEFAULT NULL COMMENT '作业计划id',
  `check_status` int(11) DEFAULT NULL COMMENT '核查状态 0 未核查   1 已核查',
  `risk_level` int(11) DEFAULT NULL COMMENT '风险等级  风险等级 0无风险   1低风险   2中风险    3高风险',
  `check_time` datetime DEFAULT NULL COMMENT '核查时间',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `check_remark` varchar(300) DEFAULT NULL COMMENT '核查描述',
  `data_resource` int(1) DEFAULT NULL COMMENT '数据来源',
  `ai_check_status` tinyint(1) DEFAULT NULL COMMENT '核查状态 0 未核查   1 已核查',
  `ai_risk_level` tinyint(1) DEFAULT NULL COMMENT '风险等级  风险等级 0无风险   1低风险   2中风险    3高风险',
  `is_ai` tinyint(1) DEFAULT NULL COMMENT '是否ai',
  PRIMARY KEY (`id`),
  KEY `e_point_uav_resource_uav_resource_id_IDX` (`uav_resource_id`) USING BTREE,
  KEY `e_point_uav_resource_plan_id_IDX` (`plan_id`) USING BTREE,
  KEY `e_point_uav_resource_check_status_IDX` (`check_status`) USING BTREE,
  KEY `e_point_uav_resource_risk_level_IDX` (`risk_level`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=307 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `e_project` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `project_name` varchar(255) DEFAULT NULL COMMENT '工程名称',
  `project_name_bak` varchar(255) DEFAULT NULL COMMENT '工程名称',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `e_project_bao_duan` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `e_project_name` varchar(255) DEFAULT NULL COMMENT '工程名称',
  `bao_duan` varchar(255) DEFAULT NULL COMMENT '包段',
  `project_baoduan` varchar(255) DEFAULT NULL COMMENT '标段',
  `code` varchar(255) DEFAULT NULL COMMENT '人员编码或部门编码',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=22 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `e_team` (
  `id` varchar(64) NOT NULL,
  `name` varchar(255) DEFAULT NULL COMMENT '施工单位队伍名称',
  `pid` varchar(64) DEFAULT NULL,
  `charge` varchar(64) DEFAULT NULL COMMENT '负责人',
  `tel` varchar(64) DEFAULT NULL COMMENT '电话',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `del_flag` int(1) DEFAULT NULL,
  `bd` varchar(255) DEFAULT NULL COMMENT '标段',
  `station_info` varchar(255) DEFAULT NULL COMMENT '驻地信息',
  `station_longitude` varchar(255) DEFAULT NULL COMMENT '驻地位置（经度）',
  `station_latitude` varchar(255) DEFAULT NULL COMMENT '驻地位置（纬度）',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `sb_device` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `device_code` varchar(255) DEFAULT NULL COMMENT '设备编码',
  `name` varchar(255) DEFAULT NULL COMMENT '设备名称',
  `type` varchar(255) DEFAULT NULL COMMENT '设备类型 01 车辆 02 人在感知 03 工器具',
  `model` varchar(255) DEFAULT NULL COMMENT '型号',
  `org` varchar(255) DEFAULT NULL COMMENT '所属单位',
  `custodial_staff` varchar(255) DEFAULT NULL COMMENT '保管人',
  `custodial_staff_phone` varchar(255) DEFAULT NULL COMMENT '保管人联系电话',
  `status` varchar(255) DEFAULT NULL COMMENT '设备状态',
  `position_terminal_code` varchar(255) DEFAULT NULL COMMENT '定位终端编号',
  `position_terminal_type` varchar(255) DEFAULT NULL COMMENT '定位终端类型',
  `beidou_code` varchar(255) DEFAULT NULL COMMENT '北斗卡号',
  `support_position_upload` char(1) DEFAULT NULL COMMENT '支持位置上报  Y支持   N不支持',
  `support_short_message` char(1) DEFAULT NULL COMMENT '支持短报文上报 Y支持  N不支持',
  `remark` varchar(255) DEFAULT NULL COMMENT '备注',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `e_point_id` int(11) DEFAULT NULL COMMENT '所属标段id',
  `contractor` varchar(100) DEFAULT NULL COMMENT '施工单位',
  `subcontractor` varchar(100) DEFAULT NULL COMMENT '分包单位',
  `license_plate` varchar(20) DEFAULT NULL COMMENT '车牌号',
  `vehicle_registration` varchar(100) DEFAULT NULL COMMENT '行驶证文件地址',
  `e_point_project` varchar(255) DEFAULT NULL COMMENT '标段名',
  `is_resident` tinyint(1) DEFAULT NULL COMMENT '是否常驻',
  `e_point_point_code` varchar(56) DEFAULT NULL COMMENT '杆塔',
  `work_plan_id` varchar(64) DEFAULT NULL COMMENT '作业计划id',
  `is_plan_id` tinyint(4) DEFAULT NULL COMMENT '是否关联作业地点',
  `picture` varchar(100) DEFAULT NULL COMMENT '照片文件地址',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=182 DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='设备信息主表';

-----

CREATE TABLE `sb_device_alarm_config` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `device_type` varchar(255) DEFAULT NULL COMMENT '设备类型  01车辆  02人在感知  03工器具',
  `device_code` varchar(255) DEFAULT NULL COMMENT '设备编码',
  `alarm_level` int(11) DEFAULT NULL COMMENT '告警级别  1低风险   2中风险   3高风险',
  `distance` int(11) DEFAULT NULL COMMENT '距离',
  `time_span` int(11) DEFAULT NULL COMMENT '时间跨度,单位分钟',
  `limit_val` int(11) DEFAULT NULL COMMENT '限制次数',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `updator` varchar(255) DEFAULT NULL COMMENT '修改人',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=945 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `sb_device_attributes` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `device_id` bigint(20) DEFAULT NULL COMMENT '设备id',
  `attribute_name` varchar(255) DEFAULT NULL COMMENT '属性名',
  `attribute_value` varchar(255) DEFAULT NULL COMMENT '属性值',
  PRIMARY KEY (`id`),
  KEY `sb_device_attributes_sb_device_FK` (`device_id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='设备扩展属性';

-----

CREATE TABLE `sb_position` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `device_code` varchar(255) DEFAULT NULL COMMENT '设备编号',
  `device_type` varchar(56) DEFAULT NULL COMMENT '设备类型 01 车辆 02 人在感知 03 工器具',
  `longitude` double DEFAULT NULL COMMENT '经度',
  `latitude` double DEFAULT NULL COMMENT '纬度',
  `altitude` double(255,0) DEFAULT NULL COMMENT '高程',
  `coordinate` varchar(255) DEFAULT NULL COMMENT '坐标',
  `trigger_time` datetime DEFAULT NULL COMMENT '触发时间',
  `alarm_type` varchar(56) DEFAULT NULL COMMENT '报警类型（探针报警含类型）',
  `alarm_info` varchar(56) DEFAULT NULL COMMENT '报警信息描述',
  `remark` varchar(255) DEFAULT NULL COMMENT '备注',
  `create_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `sb_position_device_code_IDX` (`device_code`) USING BTREE,
  KEY `sb_position_trigger_time_IDX` (`trigger_time`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=103871 DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='设备定位信息';

-----

CREATE TABLE `sys_baoduan_code` (
  `baoduan_id` int(11) NOT NULL COMMENT '包段id',
  `code` varchar(255) NOT NULL COMMENT '人员编码或部门编码或公司编码'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='包段和人员或部门或公司的关联表';

-----

CREATE TABLE `sys_isc_org` (
  `org_id` varchar(128) NOT NULL COMMENT '部门ID',
  `org_name` varchar(400) DEFAULT NULL COMMENT '部门名称',
  `org_type` varchar(120) DEFAULT NULL,
  `parent_id` varchar(128) DEFAULT NULL COMMENT '上级部门ID',
  `org_path` varchar(1000) DEFAULT NULL COMMENT '全路径部门Id',
  `org_name_path` varchar(1000) DEFAULT NULL COMMENT '全路径部门名称',
  `cms_org_no` varchar(32) DEFAULT NULL COMMENT '营销机构编码',
  `cms_org_name` varchar(128) DEFAULT NULL COMMENT '营销机构编码名称',
  PRIMARY KEY (`org_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `sys_isc_user` (
  `user_id` varchar(128) NOT NULL COMMENT '用户ID',
  `baseorg_id` varchar(128) DEFAULT NULL COMMENT '部门Id',
  `username` varchar(480) DEFAULT NULL COMMENT '用户名称',
  `namecode` varchar(400) DEFAULT NULL COMMENT '用户OA',
  `title` varchar(320) DEFAULT NULL,
  `org_name` varchar(400) DEFAULT NULL COMMENT '部门名称',
  `org_path` varchar(1000) DEFAULT NULL COMMENT '全路径id',
  `org_name_path` varchar(1000) DEFAULT NULL COMMENT '全路径名称',
  `parent_org_id` varchar(320) DEFAULT NULL COMMENT '上级部门id',
  `parent_org_name` varchar(320) DEFAULT NULL COMMENT '上级部门名称',
  PRIMARY KEY (`user_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `sys_role` (
  `id` int(11) NOT NULL AUTO_INCREMENT COMMENT '角色主键id',
  `role` int(11) NOT NULL COMMENT '角色：1：超级管理员；2：普通角色',
  `role_name` varchar(30) NOT NULL COMMENT '角色名称',
  `create_time` datetime DEFAULT NULL COMMENT '创建时间',
  `update_time` datetime DEFAULT NULL COMMENT '更新时间',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8mb4 COMMENT='角色表';

-----

CREATE TABLE `sys_user_role` (
  `user_id` varchar(255) NOT NULL COMMENT '人员编码',
  `role_id` int(11) NOT NULL COMMENT '角色id',
  PRIMARY KEY (`user_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='人员和角色关联表';

-----

CREATE TABLE `uav` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `address` varchar(125) DEFAULT NULL COMMENT '位置',
  `autopliot_sn` varchar(125) DEFAULT NULL COMMENT '飞控编号',
  `channel` varchar(125) DEFAULT NULL COMMENT '通道',
  `created_at` varchar(125) DEFAULT NULL COMMENT '创建时间',
  `custom_name` varchar(125) DEFAULT NULL COMMENT '自定义名称',
  `uav_id` bigint(11) DEFAULT NULL COMMENT 'id',
  `is_update` tinyint(1) DEFAULT NULL COMMENT '是否可更新',
  `manufacturer` varchar(125) DEFAULT NULL COMMENT '厂商',
  `product_id` bigint(11) DEFAULT NULL COMMENT '无人机对应更新飞控程序唯一标识',
  `registration_no` varchar(125) DEFAULT NULL COMMENT '无人机登记号',
  `total_count` int(11) DEFAULT NULL COMMENT '飞行总架次',
  `type` varchar(125) DEFAULT NULL COMMENT '类别',
  `type_id` bigint(11) DEFAULT NULL COMMENT '类别id',
  `uav_fversion` varchar(125) DEFAULT NULL COMMENT '无人机当前飞控版本',
  `uav_model` varchar(125) DEFAULT NULL COMMENT '型号',
  `uav_model_id` bigint(11) DEFAULT NULL COMMENT '型号id',
  `uav_sn` varchar(125) DEFAULT NULL COMMENT '编号',
  `uav_state` int(11) DEFAULT NULL COMMENT '无人机状态 0离线 1在线 2更新中',
  `updated_at` varchar(125) DEFAULT NULL COMMENT '更新时间',
  `pic` varchar(255) DEFAULT NULL COMMENT '照片',
  `driver` varchar(64) DEFAULT NULL COMMENT '飞手',
  `tel` varchar(64) DEFAULT NULL COMMENT '电话',
  `data_recource` int(1) DEFAULT NULL COMMENT '数据来源',
  `spot` varchar(255) DEFAULT NULL COMMENT '点位',
  `binds` varchar(500) DEFAULT NULL COMMENT '可巡飞标段',
  `entry_at` datetime DEFAULT NULL COMMENT '进入系统时间',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=47 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `uav_flight_missions` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `mession_id` varchar(64) DEFAULT NULL COMMENT '任务ID',
  `e_point_point_code` varchar(60) DEFAULT NULL COMMENT 'e基建点位编号',
  `e_point_project` varchar(255) DEFAULT NULL COMMENT 'e基建项目',
  `alarm_id` int(11) DEFAULT NULL COMMENT '告警id',
  `work_plan_id` varchar(64) DEFAULT NULL COMMENT '作业计划id',
  `work_plan_name` text COMMENT '作业名称',
  `work_place` varchar(2000) DEFAULT NULL COMMENT '作业地点',
  `task_person_name` varchar(20) DEFAULT NULL COMMENT '任务下发人',
  `task_status` tinyint(1) DEFAULT NULL COMMENT '执行状态：1 待创建，2 待开始 3 执行中',
  `longitude` double DEFAULT NULL COMMENT '经度',
  `latitude` double DEFAULT NULL COMMENT '纬度',
  `uav_resource_id` int(11) DEFAULT NULL COMMENT '无人机资源id',
  `check_status` tinyint(1) DEFAULT NULL COMMENT '核查状态 0 待核查   1 已核查属实 2 已核查不属实',
  `risk_level` tinyint(1) DEFAULT NULL COMMENT '风险等级  风险等级 1无风险   2低风险   3中风险    4高风险',
  `check_remark` varchar(300) DEFAULT NULL COMMENT '核查描述',
  `check_time` datetime DEFAULT NULL COMMENT '核查时间',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `mession_type` int(1) DEFAULT NULL COMMENT '任务类型',
  `mession_name` varchar(255) DEFAULT NULL COMMENT '任务名称',
  `plan_no` varchar(50) DEFAULT NULL COMMENT '计划编号',
  `plan_name` varchar(100) DEFAULT NULL COMMENT '计划名称',
  `plan_status` tinyint(2) DEFAULT NULL COMMENT '计划状态',
  `plan_state` tinyint(2) DEFAULT NULL COMMENT '计划列表显示状态',
  `plan_type` tinyint(2) DEFAULT NULL COMMENT '任务类型',
  `start_site_name` varchar(100) DEFAULT NULL COMMENT '起飞机库名称',
  `start_site_sn` varchar(50) DEFAULT NULL COMMENT '起飞机库sn',
  `land_site_name` varchar(100) DEFAULT NULL COMMENT '降落机库名称',
  `land_site_sn` varchar(50) DEFAULT NULL COMMENT '降落机库sn',
  `uav_type` tinyint(2) DEFAULT NULL COMMENT '计划设备类型',
  `uav_model_name` varchar(100) DEFAULT NULL COMMENT '无人机型号',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=184 DEFAULT CHARSET=utf8mb4 COMMENT='飞行';

-----

CREATE TABLE `uav_plan` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `plan_no` varchar(50) DEFAULT NULL COMMENT '计划编号',
  `plan_name` varchar(100) DEFAULT NULL COMMENT '计划名称',
  `plan_status` tinyint(2) DEFAULT NULL COMMENT '计划状态',
  `plan_state` tinyint(2) DEFAULT NULL COMMENT '计划列表显示状态',
  `plan_type` tinyint(2) DEFAULT NULL COMMENT '任务类型',
  `start_site_name` varchar(100) DEFAULT NULL COMMENT '起飞机库名称',
  `start_site_sn` varchar(50) DEFAULT NULL COMMENT '起飞机库名称',
  `land_site_name` varchar(100) DEFAULT NULL COMMENT '降落机库名称',
  `land_site_sn` varchar(50) DEFAULT NULL COMMENT '降落机库名称',
  `uav_model_name` varchar(100) DEFAULT NULL COMMENT '降落机库名称',
  `uav_type` tinyint(2) DEFAULT NULL COMMENT '计划设备类型',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `uav_plan_plan_name_IDX` (`plan_name`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=41 DEFAULT CHARSET=utf8mb4 COMMENT='飞行计划';

-----

CREATE TABLE `uav_resource` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `plan_no` varchar(255) DEFAULT NULL COMMENT '任务编号',
  `record_no` varchar(255) DEFAULT NULL COMMENT '架次编号',
  `file_type` varchar(125) DEFAULT NULL COMMENT '文件类型',
  `created_at` datetime DEFAULT NULL COMMENT '资源生成时间',
  `file_name` varchar(125) DEFAULT NULL COMMENT '文件名称',
  `file_url` varchar(255) DEFAULT NULL COMMENT '文件路径',
  `file_id` varchar(125) DEFAULT NULL COMMENT '文件id',
  `longitude` double DEFAULT NULL COMMENT '经度',
  `latitude` double DEFAULT NULL COMMENT '纬度',
  `altitude` double DEFAULT NULL COMMENT '高度',
  `create_time` datetime DEFAULT NULL,
  `geo_point` point DEFAULT NULL COMMENT '文件坐标',
  `data_resource` int(1) DEFAULT NULL COMMENT '数据来源',
  `mession_id` varchar(64) DEFAULT NULL COMMENT '任务ID',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1675 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `uav_site` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `address` varchar(255) DEFAULT NULL COMMENT '位置',
  `created_at` varchar(125) DEFAULT NULL COMMENT '创建时间',
  `custom_name` varchar(125) DEFAULT NULL COMMENT '自定义名称',
  `hangar_fversion` varchar(225) DEFAULT NULL COMMENT '主控M1程序版本号',
  `site_id` bigint(11) DEFAULT NULL COMMENT 'id',
  `is_online` int(11) DEFAULT NULL COMMENT '是否在线',
  `is_update` tinyint(1) DEFAULT NULL COMMENT '是否更新',
  `manufacturer` varchar(125) DEFAULT NULL COMMENT '厂商',
  `site_model` varchar(125) DEFAULT NULL COMMENT '型号',
  `site_model_id` bigint(11) DEFAULT NULL COMMENT '站点型号id',
  `site_sn` varchar(125) DEFAULT NULL COMMENT '编号',
  `station_type` varchar(125) DEFAULT NULL COMMENT '站点类型',
  `type` varchar(125) DEFAULT NULL COMMENT '类别',
  `type_id` int(11) DEFAULT NULL COMMENT '类别id',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=20 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `uav_telemetry` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `sn_id` varchar(125) DEFAULT NULL COMMENT '飞控编号',
  `is_connected` tinyint(1) DEFAULT NULL COMMENT 'true正常，false断连',
  `warn_type` int(11) DEFAULT NULL COMMENT '0无风险；1三级缓冲区（发现），2二级缓冲区（靠近），3一级缓冲区（抵达），4地面风险',
  `nav_status` int(11) DEFAULT NULL,
  `single_dual_link` tinyint(1) DEFAULT NULL,
  `time_stamp` double DEFAULT NULL,
  `uav_lat` double DEFAULT NULL,
  `uav_lon` double DEFAULT NULL,
  `uav_h_m_s_l` double DEFAULT NULL,
  `v_gnd` double DEFAULT NULL,
  `v_north` double DEFAULT NULL,
  `v_east` double DEFAULT NULL,
  `v_down` double DEFAULT NULL,
  `num_s_v` int(11) DEFAULT NULL,
  `p_d_o_p` double DEFAULT NULL,
  `pos_type` int(11) DEFAULT NULL,
  `t_a_s` double DEFAULT NULL,
  `r_p_m` int(11) DEFAULT NULL,
  `left_r_p_m` int(11) DEFAULT NULL,
  `right_r_p_m` int(11) DEFAULT NULL,
  `throttle` int(11) DEFAULT NULL,
  `uav_pitch` double DEFAULT NULL,
  `uav_yaw` double DEFAULT NULL,
  `uav_roll` double DEFAULT NULL,
  `main_power_v` double DEFAULT NULL,
  `main_power_a` double DEFAULT NULL,
  `ap_mode` int(11) DEFAULT NULL,
  `photo_num` int(11) DEFAULT NULL,
  `tracker` int(11) DEFAULT NULL,
  `take_off` tinyint(1) DEFAULT NULL,
  `gps_heading` double DEFAULT NULL,
  `rtk_ext_sol_stat` double DEFAULT NULL,
  `flight_distance` double DEFAULT NULL,
  `cur_flight_time` varchar(125) DEFAULT NULL,
  `assi_mode` int(11) DEFAULT NULL,
  `rssi_status` tinyint(1) DEFAULT NULL,
  `sbus_status` int(11) DEFAULT NULL,
  `uav_alt` double DEFAULT NULL,
  `tx` double DEFAULT NULL,
  `rx` double DEFAULT NULL,
  `mag_cali_status` int(11) DEFAULT NULL,
  `lidar_forward_dist` double DEFAULT NULL,
  `lidar_downward_dist` double DEFAULT NULL,
  `lidar_left_dist` double DEFAULT NULL,
  `lidar_right_dist` double DEFAULT NULL,
  `lidar_back_dist` double DEFAULT NULL,
  `lidar_forward_state` tinyint(1) DEFAULT NULL,
  `lidar_downward_state` tinyint(1) DEFAULT NULL,
  `lidar_left_state` tinyint(1) DEFAULT NULL,
  `lidar_right_state` tinyint(1) DEFAULT NULL,
  `lidar_back_state` tinyint(1) DEFAULT NULL,
  `cam_status` int(11) DEFAULT NULL,
  `cam_depth` double DEFAULT NULL,
  `wind_speed` double DEFAULT NULL,
  `south_wind` double DEFAULT NULL,
  `west_wind` double DEFAULT NULL,
  `device_model1` varchar(125) DEFAULT NULL,
  `device_model2` varchar(125) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `trigger_time` datetime DEFAULT NULL COMMENT '时间戳，由time_stamp格式化而来',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=640 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `weather_risk` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `work_plan_id` varchar(64) DEFAULT NULL COMMENT '作业计划id',
  `work_plan_name` varchar(1024) DEFAULT NULL COMMENT '作业名称',
  `work_contents` varchar(3072) DEFAULT NULL COMMENT '作业内容',
  `work_state` varchar(64) DEFAULT NULL COMMENT '作业状态',
  `work_org` varchar(256) DEFAULT NULL COMMENT '作业单位',
  `work_org_id` varchar(64) DEFAULT NULL COMMENT '作业单位id',
  `longitude` double DEFAULT NULL COMMENT '作业经度',
  `latitude` double DEFAULT NULL COMMENT '作业纬度',
  `risk_type` varchar(64) DEFAULT NULL COMMENT '风险类型',
  `risk_type_name` varchar(64) DEFAULT NULL COMMENT '风险类型名称',
  `val` double DEFAULT NULL COMMENT '风险值',
  `pre_time` datetime DEFAULT NULL COMMENT '风险开始时间',
  `data_time` datetime DEFAULT NULL COMMENT '风险结束时间',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `construction_org_id` varchar(64) DEFAULT NULL COMMENT '施工单位id',
  `construction_org` varchar(256) DEFAULT NULL COMMENT '施工单位',
  PRIMARY KEY (`id`),
  UNIQUE KEY `weather_risk_un` (`work_plan_id`,`risk_type`,`data_time`),
  KEY `weather_risk_work_plan_id_IDX` (`work_plan_id`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=401 DEFAULT CHARSET=utf8mb4 COMMENT='气象预警';

-----

CREATE TABLE `zy_alarm` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `alarm_source` varchar(255) DEFAULT NULL COMMENT '告警来源：DW_DEVICE 定位设备监测       XS_UAV 无人机巡视',
  `device_code` varchar(256) DEFAULT NULL COMMENT '告警来源为DW_DEVICE时，存设备编码；告警来源为XS_UAV时，存资源ID',
  `begin_time` datetime DEFAULT NULL COMMENT '开始时间（发生时间）',
  `end_time` datetime DEFAULT NULL COMMENT '(暂时不合并报警)',
  `e_point_id` int(11) DEFAULT NULL,
  `e_point_code` varchar(125) DEFAULT NULL COMMENT 'e基建点位code',
  `project_name` varchar(125) DEFAULT NULL COMMENT '项目名称',
  `alarm_level` int(11) DEFAULT NULL COMMENT '报警等级 1 低风险   2 中风险   3 高风险',
  `check_status` int(11) DEFAULT NULL COMMENT '核查状态：0 未核查（初始默认）   1 已核查属实     2 已核查不属实',
  `check_remark` varchar(256) DEFAULT NULL COMMENT '核查备注',
  `check_time` datetime DEFAULT NULL COMMENT '核查时间',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `zy_alarm_e_point_id_IDX` (`e_point_id`) USING BTREE,
  KEY `zy_alarm_device_code_IDX` (`device_code`) USING BTREE,
  KEY `zy_alarm_e_point_code_IDX` (`e_point_code`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=5911 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `zy_alarm_config` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `device_type` varchar(125) DEFAULT NULL COMMENT '设备类型  01车辆  02人在感知  03工器具',
  `alarm_level` varchar(125) DEFAULT NULL COMMENT '告警级别  1低风险   2中风险   3高风险',
  `distance` int(11) DEFAULT NULL COMMENT '距离',
  `time_span` int(11) DEFAULT NULL COMMENT '时间跨度,单位分钟',
  `limit_val` int(11) DEFAULT NULL COMMENT '限制次数',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `updator` varchar(125) DEFAULT NULL COMMENT '修改者',
  KEY `id` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `zy_alarm_sigle_point` (
  `id` int(11) DEFAULT NULL,
  `device_code` varchar(125) DEFAULT NULL COMMENT '设备编号',
  `device_type` varchar(125) DEFAULT NULL COMMENT '设备类型',
  `begin_time` datetime DEFAULT NULL COMMENT '开始时间',
  `end_time` datetime DEFAULT NULL COMMENT '结束时间',
  `e_point_id` int(11) DEFAULT NULL COMMENT '作业点id',
  `e_point_code` varchar(125) DEFAULT NULL COMMENT '作业点code',
  `project_name` varchar(125) DEFAULT NULL COMMENT '项目名称',
  `alarm_level` int(11) DEFAULT NULL COMMENT '告警级别',
  `create_time` datetime DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `zy_alarm_synthesize_config` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `alarm_level` int(255) DEFAULT NULL COMMENT '告警级别  1低风险   2中风险   3高风险',
  `time_span` int(255) DEFAULT NULL COMMENT '时间跨度，单位分钟',
  `single_alarm_level` int(255) DEFAULT NULL COMMENT '判定目标（由几种设备类型报的某一种风险，字段定义检查的”风险“等级）：单项报警级别，1联合判定低风险  2联合判定中风险',
  `single_alarm_device_type_num` int(255) DEFAULT NULL COMMENT '上报该风险等级的设备类别数量',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  `updator` varchar(255) DEFAULT NULL COMMENT '修改人',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb4;

-----

CREATE TABLE `zy_person` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL COMMENT '姓名',
  `gender` varchar(255) DEFAULT NULL COMMENT '性别',
  `company` varchar(255) DEFAULT NULL COMMENT '公司',
  `outsourcing_team` varchar(255) DEFAULT NULL COMMENT '外包队伍名称',
  `position` varchar(255) DEFAULT NULL COMMENT '岗位',
  `data_source` tinyint(4) DEFAULT NULL COMMENT '数据来源：1 系统录入  2 系统导入  3 风控接入',
  `type` tinyint(4) DEFAULT NULL COMMENT '人员类别： 1在编人员   2外包人员',
  `remark` varchar(255) DEFAULT NULL COMMENT '北斗设备编号',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='作业人员表';

-----

CREATE TABLE `zy_plan` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `plan_code` varchar(255) DEFAULT NULL COMMENT '计划编码',
  `name` varchar(255) DEFAULT NULL COMMENT '计划名称',
  `scheduled_begin_time` datetime DEFAULT NULL COMMENT '计划开始时间',
  `scheduled_end_time` datetime DEFAULT NULL COMMENT '计划开始结束',
  `actual_start_time` datetime DEFAULT NULL COMMENT '实际开始时间',
  `actual_end_time` datetime DEFAULT NULL COMMENT '实际结束时间',
  `corrdinate` varchar(255) DEFAULT NULL COMMENT '作业位置坐标',
  `create_time` datetime DEFAULT NULL COMMENT '数据同步时间',
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='作业计划（风控平台接入）';

-----

CREATE TABLE `zy_plan_device` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `plan_id` bigint(20) DEFAULT NULL COMMENT '计划id',
  `device_id` bigint(20) DEFAULT NULL COMMENT '设备id',
  `status` varchar(20) DEFAULT NULL COMMENT '关系状态  KEEP保持   RELIEVE已接触',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `zy_plan_device_zy_plan_FK` (`plan_id`),
  KEY `zy_plan_device_sb_device_FK` (`device_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='作业计划与设备关系表';

-----

CREATE TABLE `zy_plan_org` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `org_isc_id` varchar(255) NOT NULL,
  `name` varchar(100) DEFAULT NULL,
  `plan_org_id` varchar(100) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `zy_plan_org_org_isc_id_IDX` (`org_isc_id`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8mb4 COMMENT='风险作业org对应表';

-----

CREATE TABLE `zy_plan_person` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `plan_id` bigint(20) DEFAULT NULL COMMENT '计划id',
  `person_id` varchar(30) DEFAULT NULL COMMENT '人员id',
  `status` varchar(20) DEFAULT NULL COMMENT '关系状态  KEEP保持   RELIEVE已接触',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `zy_plan_person_zy_plan_FK` (`plan_id`),
  KEY `zy_plan_person_zy_person_FK` (`person_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 ROW_FORMAT=DYNAMIC COMMENT='作业计划绑定人员与设备关系表';