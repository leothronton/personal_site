---
title: 在Scrapy使用splash爬取动态页面
author: leo_thronton
type: post
date: 2018-10-24T09:48:14+00:00
url: /2018/10/24/在scrapy使用splash爬取动态页面-3/
timeline_notification:
  - 1540374497
categories:
  - 爬虫

---
在windwos中启动Docker Quickstart Terminal后运行splash：

    docker run -p 8050:8050 -p 8051:8051 scrapinghub/splash
    

表示:Splash现在在端口8050（http）和5023（telnet）上的192.168.99.100处可用。

启动后在浏览器中输入192.168.99.100：8050 验证是否启动成功。

* * *

在scrapy项目文件settings.py中添加：

    SPLASH_URL = 'http://192.168.99.100:8050/'
    
    # 开启Splash的两个下载中间件并调整HttpCompressionMiddleware的次序
    DOWNLOADER_MIDDLEWARES = {
        'scrapy_splash.SplashCookiesMiddleware': 723,
        'scrapy_splash.SplashMiddleware': 725,
        'scrapy.downloadermiddlewares.httpcompression.HttpCompressionMiddleware': 810,
    }
    # 设置去重过滤器
    DUPEFILTER_CLASS = 'scrapy_splash.SplashAwareDupeFilter'
    
    # 用来支持cache_args（可选）
    SPIDER_MIDDLEWARES = {
        'scrapy_splash.SplashDeduplicateArgsMiddleware': 100,
    }
    

在爬虫文件pider.py中添加

    def start_requests(self):
            script = '''
                function main(splash)
                    splash:set_viewport_size(1028, 10000)
                    splash:go(splash.args.url)
                    local scroll_to = splash:jsfunc("window.scrollTo")
                    scroll_to(0, 2000)
                    splash:wait(5)
    
                    return {png=splash:png()}
                    
                end
              '''
    
            for url in self.start_urls:
                #yield SplashRequest(url, args={'images': 0, 'timeout': 10})
                yield SplashRequest(url, callback=self.parse, meta = {'dont_redirect': True,
                                                                      'splash':{'args': {'lua_source':script,
                                                                                         'images':0, 
                                                                                         'timeout': 20
                                                                                        },
                                                                                'endpoint':'execute',
                                                                                }
                                                                     }
                                   )