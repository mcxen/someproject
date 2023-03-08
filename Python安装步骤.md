因为平时经常会用到Python，今天重装了系统，正好就把Python在WIN10系统中的安装及配置过程记录一下。



## 下载

首先我们要下载Python的Windows系统安装程序，在下载前，你先要搞清楚你的系统是你32位windows还是64位。

- 右键点击我的电脑，选择属性，在弹出的关于页面，系统类型处就可以看到。

接下来，我们打开[Python官网](https://nie.su/go/aHR0cHM6Ly93d3cucHl0aG9uLm9yZy8)，在，将鼠标移动到Downloads菜单，然后点击下拉菜单的windows，我们就可以看到**Python Releases for Windows**字样。

> 你也可以从 **[https://www.python.org/downloads/windows/](https://nie.su/go/aHR0cHM6Ly93d3cucHl0aG9uLm9yZy9kb3dubG9hZHMvd2luZG93cy8)** 直达。

这里最上面就是Python的最新的发布版本，一般有Python3和Python2两个版本，我们今天就以安装最新的Python3.10.4为例。

[![点击放大图片](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/5cabebbf060f29630dead6536f9096ca.webp)](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/5cabebbf060f29630dead6536f9096ca.webp)

至此，我们的安装程序就下载好了，当然你也可以选择下面的`Pre-releases` 和`Stable Releases` 的其他版本。



## 安装

双击打开我们下载的安装程序**python-3.10.4-amd64.exe**，进入安装页面，然后按照下图中的安装过程安装即可。

1. 默认安装直接选`Install Now`（我这里是升级所以选Upgrade Now）,如果需要自定义安装路径就选 `Customize installation` ；
2. 功能选择这里，由于都是需要用到的，不建议修改，直接点 `Next` 下一步；

> Documentation：创建文档文件
>
> **pip：**安装第三方工具Python包
>
> **ttd/tk and IDLE：**桌面程序包
>
> **Python test suite：**Python测试
>
> **py launcher：**启动器
>
> **for all users(requires elevation)：**可以使所有用户使用

1. 上边的高级选项也不用管，在下面修改安装路径就行，完了直接就点击 `Install` 就可以了;
2. 安装进度，等着绿色进度条走完就行，一般不会有什么问题；
3. 成功安装后会显示 Setup was successful 页面，点击 `Close` 关闭安装窗口即可。

[![点击放大图片](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/cd98e9226b8438be9cd8f3105634a602.webp)](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/cd98e9226b8438be9cd8f3105634a602.webp)



## 配置

程序安装完成后并不是立刻能使用，我们还需要把Python的环境变量设置一下，才能让系统正确的识别到Python，具体流程如下：

右击桌面上的 `此电脑` —> `属性` —> `高级系统设置` —>右下角 `环境变量` —>双击 `系统变量` 里的 `Path` —>点击 `新建` —>输入刚才的安装位 `D:\Python310` ，以及\Scripts，得到新建后的结果，然后一步步 `确定` 回去。（看下图）

[![点击放大图片](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/fc92158defebcd23f4038d0099e9d8c9.webp)](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/fc92158defebcd23f4038d0099e9d8c9.webp)



## 验证

完成了上面的步骤，我们的Python3.10就算完整的安装成功了。我们打开**命令提示符**（ `WIN+R` 输入cmd）或者 **Windows PowerShell**在命令行输入 `python` ，如果显示版本号及信息就表示我们安装成功了。（如下图）

[![点击放大图片](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/5f491efb3b212e67dd927c0af833e475.webp)](https://gcore.jsdelivr.net/gh/love2wind/cloudimg/img/5f491efb3b212e67dd927c0af833e475.webp)



## 问题

然而我这次在安装并设置以后，在验证的时候却出现了一个以外情况，在命令行输入 python 后，并没有显示版本信息，而是直接弹出了应用商店。😂😂😂这还是没有见过的情况，Google一下才发现我并不是个例，罪魁祸首就是应用商店的环境变量和Python的环境变量冲突导致。看上图3中我用绿色框出的就是应用商店的环境变量 `%USERPROFILE%\AppData\Local\Microsoft\WindowsApps`



### 解决

- **第一种：**把应用商店的环境变量 `%USERPROFILE%\AppData\Local\Microsoft\WindowsApps` 下移到Python的环境变量下面；但是我用这种办法并没有成功，但是我看有人这样是成功了的。
- 第二种：直接删除应用商店的环境变量；我就用的这种办法成功了。

到了这里Python在Win10系统的安装及配置过程就彻底完成了，如果你在安装的过程中有什么问题可以留言交流。