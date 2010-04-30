--- 
permalink: /2009/09/converting-from-myisam-to-innodb-takes.html
layout: post
title: Converting from MyISAM to InnoDB takes a long time
tags: 
- sql
- mysql
---
Wow, I didn't think that with around 80 million rows, MySQL would take 7 hours to convert from MyISAM to InnoDB. 

  mysql> alter table metaward_achiever ENGINE=INNODB;
  Query OK, 76756189 rows affected (6 hours 53 min 57.07 sec)
  Records: 76756189  Duplicates: 0  Warnings: 0

  mysql> show create table metaward_achiever;
  | metaward_achiever | CREATE TABLE `metaward_achiever` (
    `id` int(11) NOT NULL AUTO_INCREMENT,
    `modified` datetime NOT NULL,
    `created` datetime NOT NULL,
    `award_id` int(11) NOT NULL,
    `alias_id` int(11) NOT NULL,
    `count` int(11) NOT NULL,
    PRIMARY KEY (`id`),
    KEY `metaward_achiever_award_id` (`award_id`),
    KEY `metaward_achiever_alias_id` (`alias_id`)
  ) ENGINE=InnoDB AUTO_INCREMENT=77166947 DEFAULT CHARSET=utf8 |
