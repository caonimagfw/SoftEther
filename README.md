
            <p>1、安装依懒软件</p>
<pre class="hljs ruby"><code class="ruby">[root@localhost ~]<span class="hljs-comment"># yum -y install gcc zlib-devel openssl-devel readline-devel ncurses-devel</span>
</code></pre>
<p>2、下载SoftEther VPN安装包</p>
<pre class="hljs cpp"><code class="cpp">[root@localhost ~]<span class="hljs-meta"># wget  http:<span class="hljs-comment">//softether.fishinfo.cn/files/softether/v4.27-9666-beta-2018.04.21-tree/Linux/SoftEther_VPN_Server/64bit_-_Intel_x64_or_AMD64/softether-vpnserver-v4.27-9666-beta-2018.04.21-linux-x64-64bit.tar.gz </span></span>
</code></pre>
<p>3、安装vpn</p>
<pre class="hljs css"><code class="css"><span class="hljs-selector-attr">[root@localhost opt]</span># <span class="hljs-selector-tag">tar</span> <span class="hljs-selector-tag">xf</span> <span class="hljs-selector-tag">softether-vpnserver-v4</span><span class="hljs-selector-class">.27-9666-beta-2018</span><span class="hljs-selector-class">.04</span><span class="hljs-selector-class">.21-linux-x64-64bit</span><span class="hljs-selector-class">.tar_2</span><span class="hljs-selector-class">.gz</span>
<span class="hljs-selector-attr">[root@localhost ~]</span># <span class="hljs-selector-tag">cd</span> <span class="hljs-selector-tag">vpnserver</span>
<span class="hljs-selector-attr">[root@localhost vpnserver]</span># <span class="hljs-selector-tag">make</span>
</code></pre>
<pre class="hljs php"><code class="php"><span class="hljs-keyword">Do</span> you want to read the License Agreement <span class="hljs-keyword">for</span> this software ?

 <span class="hljs-number">1.</span> Yes
 <span class="hljs-number">2.</span> No

Please choose one of above number:
 <span class="hljs-number">1</span>            <span class="hljs-comment">#选择1</span>

Did you read <span class="hljs-keyword">and</span> understand the License Agreement ?
 (<span class="hljs-keyword">If</span> you couldn<span class="hljs-string">'t read above text, Please read '</span>ReadMeFirst_License.txt<span class="hljs-string">'
 file with any text editor.)

 1. Yes
 2. No

Please choose one of above number:
 1           #选择1

Did you agree the License Agreement ?

 1. Agree
 2. Do Not Agree

Please choose one of above number:
 1          #选择1

make[1]: Leaving directory `/opt/vpnserver'</span>
</code></pre>
<p>4、启动服务</p>
<pre class="hljs ruby"><code class="ruby">[root@localhost vpnserver]<span class="hljs-comment"># ./vpnserver start</span>
[root@localhost vpnserver]<span class="hljs-comment"># echo "/opt/vpnserver start" &gt;&gt; /etc/rc.local</span>
</code></pre>
<p>5、配置vpn server</p>
<p>进入管理</p>
<pre class="hljs ruby"><code class="ruby">[root@localhost vpnserver]<span class="hljs-comment"># ./vpncmd</span>
</code></pre>
<pre class="hljs bash"><code class="bash">通过使用 vpncmd 程序，可以取得以下成果。

 1. VPN Server 或 VPN Bridge 的管理。
 2. VPN Client 的管理。
 3. 使用 VPN 工具 (证书创建和网络传输速度测试工具)

选择 1, 2 或 3: 1        <span class="hljs-comment">#选择1</span>

指定的主机名或目标 VPN Server 或 VPN Bridge 正在 运行的计算机 IP 地址。
 通过以 <span class="hljs-string">"主机名:端口号"</span> 格式指定，您还可以指定端口号。
 (当没有指定端口号时，使用 443。)
 如果不输入任何内容并按下回车键，将连接到端口号为 443 的本地主机 (这台电脑)。
 目标 IP 地址的主机名:        回车键

如果通过虚拟 HUB 管理模式连接到服务器，请输入虚拟 HUB 的名称。
 如果通过服务器管理模式连接，无须输入任何内容请按回车键。
 指定虚拟 HUB 名称:           回车键
</code></pre>
<p>设置VPN管理员密码</p>
<pre class="hljs undefined"><code>VPN Server&gt;serverpasswordse
</code></pre>
<pre class="hljs undefined"><code>ServerPasswordSet 命令 - 设置 VPN Server 管理员密码
 请输入密码。要取消，请按下 Ctrl + D 键。

密码 : ******
 确认输入: ******
</code></pre>
<p>创建虚拟HUB</p>
<pre class="hljs bash"><code class="bash">VPN Server&gt;hubcreate jiti       <span class="hljs-comment">#名称自定义</span>
VPN Server&gt;<span class="hljs-built_in">exit</span>
</code></pre>
<p>6、在windows下使用vpnsmgr管理vpn服务器</p>
<p></p>
<p></p>
点击新设置<div class="image-package">
<div class="image-container" style="max-width: 480px; max-height: 560px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 116.67%;"></div>
<div class="image-view" data-width="480" data-height="560"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-2a0a12e35d95198c.png" data-original-width="480" data-original-height="560" data-original-format="image/png" data-original-filesize="58628" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-2a0a12e35d95198c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/480/format/webp"></div>
</div>
<div class="image-caption"></div>
</div>
<p></p>
<p></p>
设置名可以随意填写，主机名为VPN服务器地址，端口号默认443端口，选择“虚拟HUB管理模式”，选择一个虚拟HUB 名jiti，管理的密码，点击确定即可。<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 484px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 64.28%;"></div>
<div class="image-view" data-width="753" data-height="484"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-09d1329412b81706.png" data-original-width="753" data-original-height="484" data-original-format="image/png" data-original-filesize="61210" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-09d1329412b81706.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/753/format/webp"></div>
</div>
<div class="image-caption"></div>
</div><p>管理界面点击连接</p>
<br>
<div class="image-package">
<div class="image-container" style="max-width: 477px; max-height: 437px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 91.61%;"></div>
<div class="image-view" data-width="477" data-height="437"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-60b270791013e3d2.png" data-original-width="477" data-original-height="437" data-original-format="image/png" data-original-filesize="43648" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-60b270791013e3d2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/477/format/webp"></div>
</div>
<div class="image-caption"></div>
</div>管理虚拟HUB<br>
<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 335px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 43.62%;"></div>
<div class="image-view" data-width="768" data-height="335"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-4951336fa926292c.png" data-original-width="768" data-original-height="335" data-original-format="image/png" data-original-filesize="34805" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-4951336fa926292c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/768/format/webp"></div>
</div>
<div class="image-caption"></div>
</div><br>
<p>在管理虚拟HUB 中选择“管理用户”，“新建”—创建新用户，输入用户名，密码，确定</p>
<br>
<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 546px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 68.94%;"></div>
<div class="image-view" data-width="792" data-height="546"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-cbb5f0b7791c2a83.png" data-original-width="792" data-original-height="546" data-original-format="image/png" data-original-filesize="62336" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-cbb5f0b7791c2a83.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/792/format/webp"></div>
</div>
<div class="image-caption"></div>
</div>开启NAT地址转换和DHCP服务<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 387px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 37.79%;"></div>
<div class="image-view" data-width="1024" data-height="387"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-59288fe51f0a9a90.png" data-original-width="1024" data-original-height="387" data-original-format="image/png" data-original-filesize="250250" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-59288fe51f0a9a90.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp"></div>
</div>
<div class="image-caption"></div>
</div><br>
7、使用VPN client 连接
<p></p>
<p></p>
新建vpn连接和虚拟网卡<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 450px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 57.4%;"></div>
<div class="image-view" data-width="784" data-height="450"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-428b246ec2d773f3.png" data-original-width="784" data-original-height="450" data-original-format="image/png" data-original-filesize="73962" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-428b246ec2d773f3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/784/format/webp"></div>
</div>
<div class="image-caption"></div>
</div><p></p>
设置名称，主机名，HUB，用户名，密码<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 584px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 74.68%;"></div>
<div class="image-view" data-width="782" data-height="584"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-883e6f109e1f907e.png" data-original-width="782" data-original-height="584" data-original-format="image/png" data-original-filesize="65092" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-883e6f109e1f907e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/782/format/webp"></div>
</div>
<div class="image-caption"></div>
</div>双击连接vpn<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 256px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 32.57%;"></div>
<div class="image-view" data-width="786" data-height="256"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-ed8ae6f929f91143.png" data-original-width="786" data-original-height="256" data-original-format="image/png" data-original-filesize="41524" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-ed8ae6f929f91143.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/786/format/webp"></div>
</div>
<div class="image-caption"></div>
</div><br>
查看、测试<div class="image-package">
<div class="image-container" style="max-width: 576px; max-height: 145px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 25.169999999999998%;"></div>
<div class="image-view" data-width="576" data-height="145"><img data-original-src="//upload-images.jianshu.io/upload_images/12035125-b535998fa3f9877c.png" data-original-width="576" data-original-height="145" data-original-format="image/png" data-original-filesize="6929" class="" style="cursor: zoom-in;" src="//upload-images.jianshu.io/upload_images/12035125-b535998fa3f9877c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/576/format/webp"></div>
</div>
<div class="image-caption"></div>
</div>

 
