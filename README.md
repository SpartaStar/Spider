SpartaSpider是基于搜狗微信的爬虫,使用python语言和scrapy框架，实现了爬取主页中各分类各页数据，爬取和更新公众号信息，爬取和更新文章信息，搜索关键字信息，发表特定文章到wordpress上等等。

主要的文件的详细功能列表如下：

item.py:
	
	SpartaTagInfoItem #类别信息临时结构

	SpartaTagGzhInfoItem #类别公众号表

	SpartaTagArticleInfoItem #热文记录表

	SpartaTmpArticleInfoItem #文章临时存储

	SpartaArticleItem #文章表

	SpartaGzhItem #公众号表

	SpartaGzhArticleInfoItem #公众号主页的具体信息

	SpartaSearchItem #搜索表

	SpartaWpPostsItem #wordpress的wp_posts文章表

	SpartaWpTermRelationShipsItem #wordpress的wp_term_relationships文章关系表
 
sparta_api.py:
	
	getSpartaTagInfo #获取搜狗微信标签类别页详细内容
	
	getSpartaArticleInfo #获取搜狗微信文章url对应的详细内容

	getSearchGzhInfo #获取搜狗微信搜索公众号返回的详细内容
		
	getSearchGzhFirstInfo #获取公众号微信号wechatid的信息
		
	getSpartaGzhInfo #获取搜狗微信作者url对应的详细内容
	
sparta_base.py:

	get #封装request库get方法
	
	get_html_and_carry_item ##封装request库get方法,并可携带数据
	
	getElemText #抽取lxml.etree库中elem对象中文字
	
	getSearchGzhText #通过搜狗搜索获取关键字返回的文本
	
	replace_html #替换转义内容为正常内容
	
sparta_db.py: #封装了pymysql的类
	
sparta_define.py: #宏定义
	
sparta_gzh_url.py: #热门公众号信息拉取和更新

sparta_url.py: #爬取文章具体信息

sparta_index.py: #爬取搜狗微信主页各类别各页数据

sparta_search.py: #搜索特定关键字返回的信息

sparta_config.py: #配置信息

sparta_publish_wp: #发表文章到wordpress

使用方法：
	执行sparta.sh:
	
	echo "欢迎使用sparta"
	echo "使用方法说明如下："
	echo "(1):  ./sparta.sh sparta_index    //爬取搜狗微信主页各类别各页数据入临时公众号表和热点文章表中"
	echo "(2):  ./sparta.sh sparta_gzh_url  //临时公众号表取特定数目公众号url爬取公众号具体信息和文章临时信息"
	echo "(3):  ./sparta.sh sparta_url      //临时文章表取特定数目文章url爬取文章具体信息"
	echo "(4):  ./sparta.sh sparta_search   //搜索特定关键字返回的信息"

问题和技术交流: 745226897
