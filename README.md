
带有自定义kafka插件my_plugin扩展的emqx3.1
------------------

编译环境配置
------------------
1.安装erlang/otp21.2   emqx3.1使用eralng21.1编译  
>>1)erlang/otp要使用的版本参考emqx的git源码文档https://github.com/emqx/emqx-rel，我这里emqx3.1应使用erlang/otp21.2  
>>2)erlang/otp编译安装参考https://www.cnblogs.com/datacoding/p/6937493.html  

2.安装rebar3     https://www.rebar3.org/docs/getting-started#section-installing-from-source  
    源码安装rebar3 https://github.com/erlang/rebar3.git下载源码，执行bootstrap.cmd,然后拷贝rebar3.cmd和rebar3文件  
    到自定义目录，并且配置环境变量  
3.在根目录中运行make命令，编译后的结果在_rel下  

自定义插件方法以my_plugin为例
------------------
 1.下载插件模板https://github.com/emqx/emqx-plugin-template，注意插件模板源码分支版本与emqx要一致，我这里使用3.1版本  
 2.将插件模板放置于emqx项目的deps目录下，并修改文件夹名称、以及src下的源码文件名my_plugin  
 3.修改插件模板目录中的Makefile文件  
    PROJECT项修改为PROJECT = my_plugin  
    BUILD_DEPS项中增加ekaf依赖，并指定git地址  
    BUILD_DEPS = emqx cuttlefish ekaf  
    dep_ekaf = git https://github.com/helpshift/ekaf.git master  
    app.config项中修改配置文件名等  
 
 4.修改emqx中的Makefile文件，增加DEPS += my_plugin， 为了让编译emqx时引导编译插件my_plugin  
 5.在relx.config中的{relx,{release, 片段内增加  
   ekaf,  
   {my_plugin, load},  
   目的是将ekaf、my_plugin打入编译后的lib中，如果在插件中引用了其他第三方依赖，也要再此添加  
