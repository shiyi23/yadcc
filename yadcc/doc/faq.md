# FAQ

- Q：搭建环境存在一些问题，调试无从下手。

  A：可以参考我们的[调试指引](doc/debugging.md)。

- Q：编译器的输出始终是英文的，无论本地及服务端的`LANG`如何配置。

  A：为了保证集群环境整体一致，`yadcc`服务端在运行编译器（`gcc` / `g++` / ...）之前会重置环境变量，因此`LANG`不会生效。否则可能会出现同一批编译有些错误提示是中文有些错误提示是英文（因为不同的编译机环境变量配置不同）。

- Q：ARM机型支持吗？

  A：目前我们测试环境的调度器及缓存服务器即部署在ARM机器上。守护进程和客户端暂时没有完成ARM支持。目前来说没有技术上的制约（主要是几个`__rdtsc()`换一下就可以），后续版本我们会提供支持。