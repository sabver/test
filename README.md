>下面是针对每一个会涉及团队开发的分支进行说明，如果是个人建立的分支的话，请将对应说明写在对应分支区域。

 - 版本：1.0 
 - 编写风格：Markdown
 - 编写时间：2017-2-16 
 - 编写人：叶建锋

# 分支
## master
    已弃用。
    
## www.tongxueq.com
    对应正式域名。
    
1. 目录结构  
 - app（APP源码）
 - web（web源码）
	 - Application（后端开发源码）
	     - App/View/Share
			 - activity.html（活动分享）
			 - index.html（直播分享）
			 - kfile.html（知识库分享）	     
	 - Crontab
	 - fis（前端开发源码）
		 - component_modules（外部引用的模块和插件）
		 - components（内部编写的自定义模块和插件）
		 - doc（JSON文档存放处，实时性无法保证）
		 - lib（特殊js存放处）
			 - avalon
			 - jquery2.1.4
			 - ueditor
			 - videojs
			 - css.js
			 - domReady.js
			 - require.js
			 - text.js		 
		 - views
		    - 见下面的views的说明
		 - admin.html（大后台管理员入口）
		 - fis-conf.js（fis3配置文件）
		 - index.html（权限管理入口）
		 - index.js
		 - login.html（大后台登录入口）
		 - mock_test.js
		 - user.html（大后台普通用户入口）	 
	 - Public（Thinkphp存放公共资源，如上传的图片）
	 - QINIU
	 - release（线上访问的代码发布位置）
	 - test（用于本地访问的test模块的发布代码）
	 - ThinkPHP（Thinkphp源码）
	 - composer.json（Thinkphp源码说明）
	 - index.html（可忽略）
	 - index.php（Thinkphp入口文件）
	 - jkf.sql
	 - README.md（可忽略）
 - README.md
 - sql.txt（继续维护中）
 - sql-上线版.txt（继续维护中）
 - sql-正式测试版.txt（继续维护中）
 - 后台开发命名规范.txt（继续维护中）
 - 九型人格数据.txt（继续维护中）
 - 童学圈APP接口列表v1_20160114.xlsx（继续维护中）
 - 童学圈APP接口列表规范文档.xlsx（继续维护中）

**views的说明：**
 - views
	 - admin
		 - circle
		     - index（圈子首页）
		     - list（圈子列表）
		 - console
			 - admin_account（管理员账号管理）
			 - banner（轮播图管理）
			 - config_item（配置项管理）
			 - push_info（推送消息管理）
			 - time_resource（时段资源管理）		 
		 - frame（admin.html引用的js资源）
		 - income/index（收益图表）
		 - index（可忽略）
		 - integral
			 - cash_info（提现通知）
			 - integral_cash（收益提现列表）
			 - integral_rule（收益规则配置）		 
		 - knowledge
			 - a_report（活动举报列表）
			 - activity（活动列表）
			 - e_report（评测举报列表）
			 - evaluating（推荐的评测列表）
			 - index（知识首页）
			 - list（知识列表）
			 - report（知识举报列表）		 
		 - live
			 - index（直播首页）
			 - list（直播列表）
			 - record（审核记录列表）
			 - report（直播举报列表）
			 - returning（回放列表）		 
		 - user
			 - circle（圈子列表）
			 - comment_user（评论权限管理）
			 - cvip（童学圈vip列表）
			 - index（用户首页）
			 - report（用户举报列表）
			 - rvip（回放vip列表）
			 - user（用户列表）
			 - vip（已弃用）		 
	 - demo
		 - modal（可公用模态框组件demo）
		 - page（可忽略）
		 - page_test（page组件demo）
		 - test（可忽略）
		 - validate_mvvm（字段验证工具demo）	 
	 - developer
		 - authority（权限管理）
		 - user_group（用户组管理）	 
	 - login（登录）
	 - mobile
		 - knowledge
			 - evaluating
				 - add（添加评测）
				 - common/url.js（请求链接和域名）
				 - item_pool
					1. survey（调研题）
					2. test（考试题）
					3. type（类型题）
					4. index.html（题库）
					5. index.js			 
				 - more（用户填写考题）
				 - result（个人评测结果）
				 - statistics（在线评测）
				 - type（评测类型）
				 - video（已弃用）			 
			 - more（已弃用）
			 - video（已弃用）		 
		 - live
			 - play（直播分享，现在是后端管理，所以这里是没用的）
			 - signin（活动分享，现在是后端管理，所以这里是没用的）		 
		 - test（测试页面）	 
	 - user	 
		 - frame（uesr.html引用的js资源）
		 - index（用户后台首页）
		 - knowledge
			 - activity（活动列表）
			 - evaluating（我推荐的评测列表）
			 - item_pool（题库列表）
			 - list（知识列表）
			 - type（圈子类别列表）
			 - video（知识视频列表）		 
		 - live/list（直播列表）
    
2. 代码提交     
     - 通常我们会在个人分支进行开发，假设为分支test，如果我们需要将自己的分支合并到http://www.tongxueq.cn分支（测试域名分支）或者http://www.tongxueq.com分支（正式域名分支），我们可以有如下合并操作：    
    1. 假设现在你在test分支。
    2. git commit -am "commit message"
    3. git pull origin test
    4. git push origin test
    5. git checkout http://www.tongxueq.cn（切换到测试分支）
    6. git pull origin http://www.tongxueq.cn
    7. git merge --no-ff -m "merge message" test（合并test分支）
    8. 如果遇到冲突，解决冲突后进行重复提交操作。
    9. 在操作7步的时候，有后端开发者反馈会出现代码覆盖的情况，这里有个另外的“合并”操作可以避免这个问题。
    10. git checkout test -- 文件夹名称（这段指令的意义是只从test分支拉取自己改过的代码，不需要整个分支进行拉取，避免覆盖其他模块代码），具体的参考可以查看：http://jasonrudolph.com/blog/2009/02/25/git-tip-how-to-merge-specific-files-from-another-branch/
    11. 进行了上述的checkout操作之后，就进行提交操作。
     
   
3. 发布流程
    - 发布代码前，需要修改域名，修改位置如下：
        - fis/components/common/js/domian.js
        - fis/views/mobile/knowledge/evaluating/common/url.js
        - fis/fis-conf.js（根据发布的文件夹，添加/test或者/release）
    - 发布到本地测试
        - 域名修改为http://127.0.0.1/TXQ-A151125/web
        - 用控制台cd命令移动到fis目录下
        - fis3 release -d ../test -wc
    - 发布到测试域名
        - 域名修改为http://www.tongxueq.cn
        - 用控制台cd命令移动到fis目录下
        - fis3 release -d ../release prod
    - 发布到正式域名
        - 域名修改为http://www.tongxueq.com
        - 用控制台cd命令移动到fis目录下
        - fis3 release -d ../release prod     

    
## http://www.tongxueq.cn
    对应测试域名。


# 附录
## 前端技术清单

 - 打包工具：fis3
 - MVVM框架：avalon1.5
 - AMD：requirejs
 - dom操作：jquery2.1.4
 - 其他：bootstrap3.0.3、toastr...

## 访问链接
 - 正式域名
     - 后台超管/用户管理地址：www.tongxueq.com  
 - 测试域名
     - 后台超管/用户管理地址：www.tongxueq.cn

 - 本地测试
     - 后台超管/用户管理地址：http://127.0.0.1/TXQ-A151125/web/test/login.html

## 测试用的登录账号
     - 正式域名：
        - 超管：10000 JeekUp2016
        - 用户：15989239460 123456
     - 测试域名：
        - 超管：10000 JeekUp2016
        - 用户：15989239460 123456    

    



