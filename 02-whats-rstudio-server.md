RStudio Server 是什么
---


在序言中已经提及，本手册中介绍的 RStudio 都指的是运行在一台远程 Linux 服务器上的 RStudio Server。那么 RStudio Server 究竟是什么？

### RStudio Desktop 与 RStudio Server 有什么区别？
RStudio Desktop 是一个 R IDE，与您已安装在您的本地 Windows，Mac OS X 或 Linux 工作站上的 R 配合工作。RStudio 桌面版是一个**独立的**桌面应用程序，不需要以任何方式连接到 RStudio 服务器版。

RStudio Server 是一个 Linux 服务器上的应用程序，提供了在服务器上运行的 R 环境，而用户通过浏览器来访问。


### 使用 RStudio Server 的好处
在管理员完成服务器端的配置后，用户可以在网页浏览器中使用 R 和 RStudio。在远程服务器上部署 R 和 RStudio 的好处如下：

* 在任何地方，从任何设备（能够浏览互联网的设备，即使是智能手机、平板电脑） 来访问你的 R 工作空间。
* 以非常简单的方式和同事或同学共享代码、数据和其他文件。
* 使得多用户可以共享服务器上强大的计算资源。
* 对管理员来说，中心化的配置和管理 R 、TeX 和各种依赖包，使用户拥有一个统一的开发环境。

RStudio Server 可以运行在各大发行版的 Linux 服务器上，也可以从源代码编译安装。用户使用符合一定标准的浏览器、并拥有管理员发放的账号和密码即可使用。用户享有独立的存储空间和工作环境，并可以通过 RStudio 自由地使用系统的其他资源。



