# 183、常用存储弓|擎？ InnoDB 与MylSAM的区别？

常用的存储引擎包括InnoDB、MyISAM、Memory、Archive、CSV、Blackhole等。其中，InnoDB和MyISAM是MySQL中最常用的两种存储引擎，它们的主要区别如下：

1. 事务支持：InnoDB支持事务，而MyISAM不支持事务。
2. 锁机制：InnoDB采用行级锁，支持多版本并发控制（MVCC），可以实现更高的并发性和更好的读写性能；而MyISAM采用表级锁，只有在读取和更新表时才会对整个表加锁，因此并发性相对较低。
3. 索引结构：InnoDB的主键索引采用B+树结构，数据文件本身就是索引文件，因此查询效率较高；而MyISAM的索引采用B树结构，数据文件与索引文件分开存储，因此查询效率相对较低。
4. 空间占用：InnoDB占用的空间相对较大，因为它需要维护事务日志、回滚日志等；而MyISAM占用的空间相对较小，因为它不需要维护这些额外的信息。
5. 支持全文检索：MyISAM支持全文检索，而InnoDB不支持。 综上所述，InnoDB适合于要求数据完整性和事务支持的应用，如电子商务、金融等；而MyISAM适合于读写比较少、对性能要求较高的应用，如博客、新闻等。当然，选择存储引擎还要根据具体的应用场景和需求进行选择。
