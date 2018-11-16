### 一键生成CRUD,包括控制器、模型、视图、JS、语言包、菜单等

-----

````

//生成fa_test表的CRUD
php think crud -t test
//生成fa_test表的CRUD且一键生成菜单
php think crud -t test -u 1
//删除fa_test表生成的CRUD
php think crud -t test -d 1
 
````


###  一键生成控制器菜单和规则

---

````

//一键生成test控制器的权限菜单
php think menu -c test
//一键生成mydir/test控制器的权限菜单
php think menu -c mydir/test
//删除test控制器生成的菜单
php think menu -c test -d 1
//一键全部重新所有控制器的权限菜单
php think menu -c all-controller

````

###  一键生成API接口文档

````

/一键生成API文档
php think api --force=true
//指定https://www.example.com为API接口请求域名,默认为空
php think api -u https://www.example.com --force=true
//输出自定义文件为myapi.html,默认为api.html
php think api -o myapi.html --force=true
//修改API模板为mytemplate.html，默认为index.html
php think api -e mytemplate.html --force=true
//修改标题为FastAdmin,作者为作者
php think api -t FastAdmin -a Karson --force=true
//查看API接口命令行帮助
php think api -h


-u, --url[=URL]            默认API请求URL地址 [default: ""]
-m, --module[=MODULE]      模块名(admin/index/api) [default: "api"]
-o, --output[=OUTPUT]      输出文件 [default: "api.html"]
-e, --template[=TEMPLATE]  模板文件 [default: "index.html"]
-f, --force[=FORCE]        覆盖模式 [default: false]
-t, --title[=TITLE]        文档标题 [default: "FastAdmin"]
-a, --author[=AUTHOR]      文档作者 [default: "FastAdmin"]
-c, --class[=CLASS]        扩展类 (multiple values allowed)
-l, --language[=LANGUAGE]  语言 [default: "zh-cn"]

````

控制器注释

|名称|描述|示例|
|---|---|---|
|@ApiSector|API分组名称|(测试分组)|
|@ApiRoute|API接口URL,此@ApiRoute只是基础URL|	(/api/test)|
|@ApiInternal|忽略的控制器,表示此控制将不加入API文档|无|

方法注释


|名称|	描述|	示例|
|---|---|---|
|@ApiTitle|	API接口的标题,为空时将自动匹配注释的文本信息|	(测试标题)|
|@ApiSummary|	API接口描述	|(测试描述)|
|@ApiRoute|	API接口地址,为空时将自动计算请求地址	|(/api/test/index)|
|@ApiMethod|	API接口请求方法,默认为GET	|(POST)|
|@ApiSector|	API分组,默认按钮控制器或控制器的@ApiSector进行分组|	(测试分组)|
|@ApiParams|	API请求参数,如果在@ApiRoute中有对应的{@参数名}，将进行替换|	(name="id", type="integer", required=true, description="会员ID")|
|@ApiHeaders|	API请求传递的Headers信息|	(name=token, type=string, required=true, description="请求的Token")|
|@ApiReturn|	API返回的结果示例|	({"code":1,"msg":"返回成功"})|
|@ApiReturnParams|	API返回的结果参数介绍|	(name="code", type="integer", required=true, sample="0")|
|@ApiReturnHeaders|	API返回的Headers信息	|(name="token", type="integer", required=true, sample="123456")|
|@ApiInternal|	忽略的方法,表示此方法将不加入文档|	无|


### 一键管理插件

````

//创建一个myaddon本地插件，常用于开发自己的插件时使用
php think addon -a myaddon -c create
//刷新插件缓存，如果禁用启用了插件，部分文件需要刷新才会生效
php think addon -a example -c refresh
//远程安装example插件
php think addon -a example -c install
//卸载本地的example插件
php think addon -a example -c uninstall
//启用本地的example插件
php think addon -a example -c enable
//禁用本地的example插件
php think addon -a example -c disable
//升级本地的example插件
php think addon -a example -c upgrade
//将本地的example插件打包成zip文件
php think addon -a example -c package


````



