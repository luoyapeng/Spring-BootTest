settle_detail	CREATE TABLE `settle_detail` (
  `id` bigint(20) unsigned NOT NULL AUTO_INCREMENT COMMENT '自增主键',
  `pk_detail` varchar(30) NOT NULL COMMENT '业务唯一编码',
  `uuid` varchar(36) DEFAULT NULL COMMENT '全局流水号',
  `subid` varchar(20) DEFAULT NULL COMMENT '子交易流水号',
  `busi_id` varchar(10) NOT NULL COMMENT '业务大类编码',
  `ta_code` varchar(10) DEFAULT NULL COMMENT 'ta编码',
  `prod_code` varchar(60) NOT NULL COMMENT '产品代码',
  `busi_type` varchar(60) DEFAULT NULL COMMENT '业务大类',
  `prod_name` varchar(60) DEFAULT NULL COMMENT '产品名称',
  `create_date` varchar(10) NOT NULL COMMENT '制单日期',
  `payer_acct` varchar(32) DEFAULT NULL COMMENT '付款人账号',
  `payer_name` varchar(60) DEFAULT NULL COMMENT '付款人名称',
  `payer_addr` varchar(70) DEFAULT NULL COMMENT '付款人地址',
  `payer_opbk` varchar(14) DEFAULT NULL COMMENT '付款人开户行行号',
  `payer_bank` varchar(14) DEFAULT NULL COMMENT '付款行行号',
  `payee_acct` varchar(32) DEFAULT NULL COMMENT '收款人账号',
  `payee_name` varchar(60) DEFAULT NULL COMMENT '收款人名称',
  `payee_addr` varchar(70) DEFAULT NULL COMMENT '收款人地址',
  `payee_opbk` varchar(14) DEFAULT NULL COMMENT '收款人开户行行号',
  `payee_opbk_name` varchar(70) DEFAULT NULL COMMENT '收款人开户行行名',
  `payee_bank` varchar(14) DEFAULT NULL COMMENT '收款行行号',
  `tx_user` varchar(10) DEFAULT NULL COMMENT '经办柜员',
  `tx_date` varchar(10) DEFAULT NULL COMMENT '处理日期',
  `cur` varchar(3) DEFAULT NULL COMMENT '币种',
  `amount` decimal(28,8) DEFAULT NULL COMMENT '金额',
  `settle_path` varchar(8) DEFAULT NULL COMMENT '汇路',
  `settle_status` char(2) DEFAULT NULL COMMENT '结算状态',
  `sys_code` varchar(6) DEFAULT NULL COMMENT '系统编码',
  `sys_no` bigint(20) DEFAULT NULL COMMENT '系统编号',
  `sys_name` varchar(60) DEFAULT NULL COMMENT '系统名称',
  `gl_inst` varchar(10) DEFAULT NULL COMMENT '记账机构',
  `auto_flag` varchar(4) DEFAULT NULL COMMENT '自动清算标识',
  `settle_start_date` varchar(10) NOT NULL COMMENT '清结算开始日期',
  `settle_end_date` varchar(10) NOT NULL COMMENT '清结算结束日期',
  `ts` varchar(19) DEFAULT NULL COMMENT '时间戳',
  `has_sub` varchar(4) DEFAULT NULL COMMENT '是否有子单',
  `settle_sys` varchar(10) DEFAULT NULL COMMENT '记账系统',
  `check_flag` varchar(10) DEFAULT NULL COMMENT '对账标识',
  `remark1` varchar(70) DEFAULT NULL COMMENT '处理附言',
  `remark2` varchar(255) DEFAULT NULL COMMENT '记账状态详情',
  PRIMARY KEY (`id`) USING BTREE,
  UNIQUE KEY `UNIQ_SETTLE_DETAIL_INDEX` (`pk_detail`)
) ENGINE=InnoDB AUTO_INCREMENT=231 DEFAULT CHARSET=utf8 ROW_FORMAT=COMPACT COMMENT='结算详情记录表'


settle_dtl	CREATE TABLE `settle_dtl` (
  `id` bigint(20) unsigned NOT NULL AUTO_INCREMENT COMMENT '自增主键',
  `busi_id` varchar(10) NOT NULL COMMENT '业务大类编码',
  `prod_code` varchar(60) NOT NULL COMMENT '产品代码',
  `settle_date` varchar(10) NOT NULL COMMENT '制单日期',
  `busi_type` varchar(60) NOT NULL COMMENT '业务大类',
  `prod_name` varchar(60) DEFAULT '' COMMENT '产品名称',
  `uuid` varchar(36) DEFAULT NULL COMMENT '全局流水号',
  `payer_acct` varchar(32) DEFAULT NULL COMMENT '付款人账号',
  `payer_name` varchar(60) DEFAULT NULL COMMENT '付款人名称',
  `payer_addr` varchar(70) DEFAULT NULL COMMENT '付款人地址',
  `payer_opbk` varchar(14) DEFAULT NULL COMMENT '付款人开户行行号',
  `payer_bank` varchar(14) DEFAULT NULL COMMENT '付款行行号',
  `payee_acct` varchar(32) DEFAULT NULL COMMENT '收款人账号',
  `payee_name` varchar(60) DEFAULT NULL COMMENT '收款人名称',
  `payee_addr` varchar(70) DEFAULT NULL COMMENT '收款人地址',
  `payee_opbk` varchar(14) DEFAULT NULL COMMENT '收款人开户行行号',
  `payee_opbk_name` varchar(70) DEFAULT NULL COMMENT '收款人开户行行名',
  `payee_bank` varchar(14) DEFAULT NULL COMMENT '收款行行号',
  `tx_user` varchar(10) DEFAULT NULL COMMENT '经办柜员',
  `auth_user` varchar(10) DEFAULT NULL COMMENT '授权柜员',
  `tx_date` varchar(10) DEFAULT NULL COMMENT '处理日期',
  `cur` varchar(3) DEFAULT NULL COMMENT '币种',
  `amount` decimal(28,8) DEFAULT NULL COMMENT '金额',
  `settle_path` varchar(8) DEFAULT NULL COMMENT '汇路',
  `remark1` varchar(70) DEFAULT NULL COMMENT '附言',
  `settle_status` char(2) DEFAULT NULL COMMENT '结算状态',
  `remark2` varchar(255) DEFAULT NULL COMMENT '备用',
  `ta_code` varchar(10) DEFAULT NULL COMMENT 'ta编码',
  `sys_code` varchar(6) DEFAULT NULL COMMENT '系统编码',
  `sys_no` bigint(20) DEFAULT NULL COMMENT '系统编号',
  `sys_name` varchar(60) DEFAULT NULL COMMENT '系统名称',
  `gl_inst` varchar(10) DEFAULT NULL COMMENT '记账机构',
  `auto_flag` varchar(4) DEFAULT NULL COMMENT '自动清算标识',
  `subid` varchar(20) DEFAULT '~' COMMENT '子交易流水号',
  `settle_start_date` varchar(10) DEFAULT '~' COMMENT '清算开始日期',
  `settle_end_date` varchar(10) DEFAULT '~' COMMENT '清算结束日期',
  `ts` varchar(19) DEFAULT NULL COMMENT '时间戳',
  `has_sub` varchar(4) DEFAULT NULL COMMENT '是否有子单',
  `create_date` varchar(10) NOT NULL COMMENT '制单日期',
  `bill_status` varchar(20) NOT NULL DEFAULT '' COMMENT '单据状态',
  PRIMARY KEY (`id`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=1111 DEFAULT CHARSET=utf8 ROW_FORMAT=COMPACT COMMENT='结算详情表'


settle_dtl_b	CREATE TABLE `settle_dtl_b` (
  `id` bigint(20) unsigned NOT NULL AUTO_INCREMENT COMMENT '自增主键',
  `pk_detail_b` varchar(30) NOT NULL COMMENT '业务唯一编码',
  `uuid` varchar(36) DEFAULT NULL COMMENT '全局流水号',
  `pid` varchar(30) DEFAULT NULL COMMENT '父单据业务编码',
  `subid` varchar(20) DEFAULT NULL COMMENT '子交易流水号',
  `amount` decimal(28,8) DEFAULT NULL COMMENT '金额',
  `amount_type` char(2) DEFAULT NULL COMMENT '费用',
  `payer_acct` varchar(32) DEFAULT NULL COMMENT '付款人账号',
  `payer_name` varchar(60) DEFAULT NULL COMMENT '付款人名称',
  `payer_addr` varchar(70) DEFAULT NULL COMMENT '付款人地址',
  `payer_opbk` varchar(14) DEFAULT NULL COMMENT '付款人开户行行号',
  `payer_channel` varchar(20) DEFAULT NULL COMMENT '渠道来源',
  `payee_acct` varchar(32) DEFAULT '' COMMENT '收款人账号',
  `payee_name` varchar(60) DEFAULT '' COMMENT '收款人名称',
  `payee_addr` varchar(70) DEFAULT '' COMMENT '收款人开户行地址',
  `payee_opbk` varchar(14) DEFAULT '' COMMENT '收款人开户行行号',
  `settlement_id` varchar(60) DEFAULT NULL COMMENT '结算Id',
  `settle_status` char(2) DEFAULT NULL,
  `create_date` varchar(10) DEFAULT NULL,
  `tx_date` varchar(20) DEFAULT '' COMMENT '处理时间',
  `tx_user` varchar(60) DEFAULT '' COMMENT '处理人',
  `remark2` varchar(255) DEFAULT '' COMMENT '附言',
  `ts` varchar(19) DEFAULT NULL COMMENT '时间戳',
  `prod_code` varchar(60) DEFAULT '' COMMENT '产品代码',
  `tran_type` varchar(60) DEFAULT '' COMMENT '交易类型',
  `gl_inst` varchar(60) DEFAULT '' COMMENT '记账机构',
  `settle_start_date` varchar(20) DEFAULT '' COMMENT '清算开始时间',
  `settle_end_date` varchar(20) DEFAULT '' COMMENT '清算结束时间',
  `bill_status` varchar(20) DEFAULT '' COMMENT '单据状态',
  `settle_sys` varchar(10) DEFAULT NULL COMMENT '记账系统',
  `check_flag` varchar(10) DEFAULT NULL COMMENT '对账标识',
  PRIMARY KEY (`id`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=1738 DEFAULT CHARSET=utf8 ROW_FORMAT=COMPACT COMMENT='结算详情子表'


settle_path	CREATE TABLE `settle_path` (
  `id` bigint(20) unsigned NOT NULL AUTO_INCREMENT COMMENT '自增主键',
  `busi_id` varchar(8) NOT NULL COMMENT '业务大类ID',
  `prod_code` varchar(60) NOT NULL COMMENT '产品代码',
  `busi_type` varchar(60) DEFAULT NULL COMMENT '业务大类',
  `prod_name` varchar(60) DEFAULT NULL COMMENT '产品名称',
  `payer_acct` varchar(32) DEFAULT NULL COMMENT '付款人账号',
  `payer_name` varchar(60) DEFAULT NULL COMMENT '付款人名称',
  `payer_addr` varchar(70) DEFAULT NULL COMMENT '付款人地址',
  `payer_opbk` varchar(14) DEFAULT NULL COMMENT '付款人开户行行号',
  `payer_bank` varchar(14) DEFAULT NULL COMMENT '付款行行号',
  `payee_acct` varchar(32) DEFAULT NULL COMMENT '收款人账号',
  `payee_name` varchar(60) DEFAULT NULL COMMENT '收款人名称',
  `payee_addr` varchar(70) DEFAULT NULL COMMENT '收款人地址',
  `payee_opbk` varchar(14) DEFAULT NULL COMMENT '收款人开户行行号',
  `payee_bank` varchar(14) DEFAULT NULL COMMENT '收款行行号',
  `tx_user` varchar(10) DEFAULT NULL COMMENT '经办柜员',
  `tx_date` varchar(8) DEFAULT NULL COMMENT '交易日期',
  `remark1` varchar(60) DEFAULT NULL COMMENT '备用',
  `ta_code` varchar(8) DEFAULT NULL COMMENT 'ta_code',
  `payee_opbk_name` varchar(60) DEFAULT NULL COMMENT '收款开户行名',
  `sys_code` varchar(6) DEFAULT NULL COMMENT '系统编码',
  `sys_no` bigint(20) DEFAULT NULL COMMENT '系统编号',
  `sys_name` varchar(60) DEFAULT NULL COMMENT '系统名称',
  `gl_inst` varchar(10) DEFAULT NULL COMMENT '记账机构',
  PRIMARY KEY (`id`) USING BTREE,
  UNIQUE KEY `SETTLE_PATH_INDEX` (`busi_id`,`prod_code`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=45 DEFAULT CHARSET=utf8 ROW_FORMAT=COMPACT COMMENT='汇路信息表'


settle_path_rela	CREATE TABLE `settle_path_rela` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT '自增主键',
  `busi_id` varchar(10) NOT NULL COMMENT '业务大类ID',
  `prod_code` varchar(60) NOT NULL COMMENT '产品代码',
  `is_clearing` varchar(10) DEFAULT NULL COMMENT '清算标识',
  `auto_generate` varchar(10) DEFAULT NULL COMMENT '自动生成结算单',
  `auto_settle` varchar(10) DEFAULT NULL COMMENT '自动结算',
  `generate_period` varchar(10) DEFAULT NULL COMMENT '生成频率',
  `start_date` varchar(20) DEFAULT NULL COMMENT '开始日期',
  `end_date` varchar(20) DEFAULT NULL COMMENT '结束日期',
  `generate_pattern` varchar(20) DEFAULT NULL COMMENT '生成方式',
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_SETTLE_PATH_RELA_INDEX` (`busi_id`,`prod_code`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=20 DEFAULT CHARSET=utf8