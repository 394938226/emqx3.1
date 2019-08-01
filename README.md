
带有自定义kafka插件扩展的emqx3.1
------------------

编译环境配置
------------------
1.安装erlang/otp21.2   emqx3.1使用eralng21.1编译
    1)erlang/otp要使用的版本参考emqx的git源码文档https://github.com/emqx/emqx-rel，我这里emqx3.1应使用erlang/otp21.2
    2)erlang/otp编译安装参考https://www.cnblogs.com/datacoding/p/6937493.html

2.安装rebar3     https://www.rebar3.org/docs/getting-started#section-installing-from-source
    源码安装rebar3 https://github.com/erlang/rebar3.git下载源码，执行bootstrap.cmd,然后拷贝rebar3.cmd和rebar3文件
    到自定义目录，并且配置环境变量


Build Docker Image
------------------

