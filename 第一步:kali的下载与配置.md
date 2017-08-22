* #### 登陆kali的官网<https://www.kali.org>,并下载kali对应平台的IOS镜像
  * 我使用的是windows平台,在此演示Windows平台下的简单操作方式
  * [kali 64 2017](http://cdimage.kali.org/kali-2017.1/kali-linux-2017.1-amd64.iso)
* #### 百度一个Vmware虚拟机下载安装,需要破解或直接百度一个密钥就长期能使用,否则只有30天
  * 我是直接在百度上搜索下载的[Vmware 12](https://www.baidu.com/link?url=OnpkZVL2xczWDsJxPDw-GoxStZibtaG20qEiIozTdcLhY7N-UvGWREZy98gBPikHPeGZKJB1Rs2JDI2rdPxy9j855dh321aU0edIWJS4EY_&wd=&eqid=992fdb3c0000b97100000004599ca73c)
  * VMware Workstation 12序列号: 5A02H-AU243-TZJ49-GTC7K-3C61N
* #### 在`Vm`上安装`kali`
  * 我找到了一篇非常详细kali虚拟机安装[blog](http://blog.csdn.net/u012318074/article/details/71601382)`非常感谢这位博主`
    * 主要`特别注意`:如果你的网络不好,没有翻墙外网,`apt`会找不到源而失败,我们只需要点击返回,跳过这步,等安装完成后进入系统的命令行选择国内的源下载安装即可
    ![网络镜像配置步骤](https://raw.githubusercontent.com/Caogenyuan/kali-msf/master/res/1.png)
    * 如果你的`apt`没有安装上,就在安装结束后进入kali系统打开终端
    * linux简单命令介绍
      <pre><code>命令行里面的复制:ctrl+shift+c 粘贴:ctrl+shift+v 退出当前命令执行：ctrl+z</code></pre>
    </br>
     1.首先检查kali版本
      <pre><code>lsb_release -a</code></pre>
    </br>
     2.打开源地址保存文件,在所有deb前用#号注释,然后添加对应版本的源地址
      <pre><code>leafpad /etc/apt/sources.list</code></pre>
    </br>
      如果你使用的是我提供的kali 64 2017的版本可以使用下面的源地址,否则使用对应版本的deb源地址即可
      <pre><code>
        #中科大
        deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
        deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib

          #浙大
          deb http://mirrors.zju.edu.cn/kali kali-rolling main contrib non-free
          deb-src http://mirrors.zju.edu.cn/kali kali-rolling main contrib non-free

          #东软大学
          deb http://mirrors.neusoft.edu.cn/kali kali-rolling/main non-free contrib
          deb-src http://mirrors.neusoft.edu.cn/kali kali-rolling/main non-free contrib

          #重庆大学
          deb http://http.kali.org/kali kali-rolling main non-free contrib
          deb-src http://http.kali.org/kali kali-rolling main non-free contrib

          #官方源
          #deb http://http.kali.org/kali kali-rolling main non-free contrib
          #deb-src http://http.kali.org/kali kali-rolling main non-free contrib
      </code></pre>
    </br>
      3.然后执行等待安装完成就可以了
        <pre><code>apt-get update && apt-get dist-upgrade</pre></code>
     #### 如果你发现你还是下载不了,很有可能是网络链接问题,把网络连接改为nat(屏幕右下角的小电脑)
