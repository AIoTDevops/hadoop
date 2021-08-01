1. commodity

CREATE TABLE `t_commodity` (
  `id` int(11) NOT NULL,
  `commodity_name` varchar(50) DEFAULT NULL,
  `commodity_price` decimal(10,2) DEFAULT NULL,
  `commodity_cate_one` int(11) DEFAULT NULL,
  `commodity_cate_two` int(11) DEFAULT NULL,
  `create_user_id` int(11) DEFAULT NULL,
  `status` int(4) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


CREATE TABLE `t_commodity_cate` (
  `id` int(11) NOT NULL,
  `cate_name` varchar(50) DEFAULT NULL,
  `cate_parent_id` int(11) DEFAULT NULL,
  `create_user_id` int(11) DEFAULT NULL,
  `status` int(4) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


2. marketing
CREATE TABLE `t_coupon` (
  `id` int(11) NOT NULL,
  `coupon_name` varchar(50) DEFAULT NULL,
  `coupon_price` decimal(10,2) DEFAULT NULL,
  `create_user_id` int(11) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


CREATE TABLE `t_coupon_member` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `coupon_id` int(11) DEFAULT NULL,
  `member_id` int(11) DEFAULT NULL,
  `coupon_channel` int(4) DEFAULT NULL COMMENT '1 用户购买 2 公司发放',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=801 DEFAULT CHARSET=utf8mb4;



CREATE TABLE `t_coupon_order` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `coupon_id` int(11) DEFAULT NULL,
  `member_id` int(11) DEFAULT NULL,
  `order_id` int(11) DEFAULT NULL COMMENT '商品订单ID',
  `create_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=562 DEFAULT CHARSET=utf8mb4;


3. member

CREATE TABLE `t_member` (
  `id` int(11) NOT NULL,
  `name` varchar(255) DEFAULT NULL,
  `password` varchar(255) DEFAULT NULL,
  `sex` varchar(255) DEFAULT NULL,
  `phone` varchar(255) DEFAULT NULL,
  `address_default_id` int(11) DEFAULT NULL,
  `member_channel` int(4) DEFAULT NULL COMMENT '1 IOS 2 android 3 微信小程序 4 微信公众号 5 h5',
  `mp_open_id` varchar(32) DEFAULT NULL COMMENT '微信公众号openId',
  `status` int(4) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;



CREATE TABLE `t_member_addr` (
  `id` int(11) NOT NULL,
  `member_id` int(11) DEFAULT NULL,
  `contact_person` varchar(50) DEFAULT NULL,
  `contact_phone` varchar(50) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;




4. operation
CREATE TABLE `t_delivery` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `delivery_no` varchar(64) DEFAULT NULL,
  `order_id` int(11) DEFAULT NULL,
  `shop_id` int(11) DEFAULT NULL,
  `postman` int(11) DEFAULT NULL,
  `pick_time` datetime DEFAULT NULL,
  `arrive_time` datetime DEFAULT NULL,
  `member_id` int(11) DEFAULT NULL,
  `member_addr_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=801 DEFAULT CHARSET=utf8mb4;

CREATE TABLE `t_feedback` (
  `id` int(11) NOT NULL,
  `member_id` int(11) DEFAULT NULL,
  `create_user_id` int(11) DEFAULT NULL,
  `feedback_content` tinytext,
  `feedback_type` int(4) DEFAULT NULL COMMENT '1 破损 2 缺货 3 错货 4 投诉',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

CREATE TABLE `t_shop` (
  `id` int(11) NOT NULL,
  `shop_name` varchar(255) DEFAULT NULL,
  `city_id` int(11) DEFAULT NULL,
  `city_name` varchar(255) DEFAULT NULL,
  `area_id` int(11) DEFAULT NULL,
  `area_name` varchar(255) DEFAULT NULL,
  `charge_user` varchar(255) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL ON UPDATE CURRENT_TIMESTAMP,
  `update_time` datetime DEFAULT NULL ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


CREATE TABLE `t_shop_order` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `shop_id` int(11) DEFAULT NULL,
  `order_id` int(11) DEFAULT NULL,
  `start_time` datetime DEFAULT NULL ON UPDATE CURRENT_TIMESTAMP,
  `done_time` datetime DEFAULT NULL ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=801 DEFAULT CHARSET=utf8mb4;


CREATE TABLE `t_user` (
  `id` int(11) NOT NULL,
  `user_name` varchar(50) DEFAULT NULL,
  `user_password` varchar(50) DEFAULT NULL,
  `user_phone` varchar(20) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


5. order

CREATE TABLE `t_order` (
  `order_id` int(11) NOT NULL,
  `member_id` int(11) DEFAULT NULL,
  `origin_price` decimal(10,2) DEFAULT NULL,
  `pay_price` decimal(10,2) DEFAULT NULL,
  `shop_id` int(11) DEFAULT NULL,
  `shop_name` varchar(50) DEFAULT NULL,
  `order_status` int(4) DEFAULT NULL COMMENT '1,进行中 2 已完成 3 已取消',
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`order_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;



CREATE TABLE `t_order_commodity` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `order_id` int(11) NOT NULL,
  `commodity_id` int(11) DEFAULT NULL,
  `commodity_name` varchar(50) DEFAULT NULL,
  `commodity_num` int(4) DEFAULT NULL,
  `commodity_price` decimal(10,2) DEFAULT NULL,
  `create_time` datetime DEFAULT NULL,
  `update_time` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1001 DEFAULT CHARSET=utf8mb4;
