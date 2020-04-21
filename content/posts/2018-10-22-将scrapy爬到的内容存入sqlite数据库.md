---
title: 将scrapy爬到的内容存入sqlite数据库
author: leo_thronton
type: post
date: 2018-10-22T08:41:49+00:00
url: /2018/10/22/将scrapy爬到的内容存入sqlite数据库/
timeline_notification:
  - 1540197712
categories:
  - 爬虫

---
这个方法需要手动创建数据库文件并将表建立好，否则程序运行会出错。

[settings.py][1]

    # sqlite 配置
    SQLITE_DB_NAME = 'Data.db'                      #数据库名称
    SQLITE_TABLE_NAME = 'table'                     #表名称
    ITEM_PIPELINES={
         'dirName.pipelines.Sqlite3Pipeline': 400,
        }
    

[pipelines.py][2]

    import sqlite3
    
    class Sqlite3Pipeline(object):
    
        def __init__(self, sqlite_file, sqlite_table):
            self.sqlite_file = sqlite_file
            self.sqlite_table = sqlite_table
            
        @classmethod
        def from_crawler(cls, crawler):
            return cls(
                sqlite_file = crawler.settings.get('SQLITE_DB_NAME'), # 从 settings.py 提取
                sqlite_table = crawler.settings.get('SQLITE_TABLE_NAME', 'items')
            )
    
        def open_spider(self, spider):
            self.conn = sqlite3.connect(self.sqlite_file)
            self.cur = self.conn.cursor()
    
        def close_spider(self, spider):
            self.conn.close()
    
        def process_item(self, item, spider):
    
            values = (
            item['A'],
            item['B'],
            item['C'],
            item['D'],
            item['E']
            )
            
            sql = 'INSERT INTO proxy VALUES (?,?,?,?,?)'    #注意插入的数据个数
            self.cur.execute(sql, values)
            self.conn.commit()
            
            return item        
    

&nbsp;

&nbsp;

 [1]: http://settings.py
 [2]: http://pipelines.py