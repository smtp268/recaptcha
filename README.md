# reCAPTCHA
RECAPTCHA
####################

国外很多网站都使用了 Google reCaptcha 验证码。reCaptcha 对于国外用户非常的友好，但是…对于国内用户就不怎么友好了。
究其原因，原因是国内网络全线屏蔽Google 服务，导致 reCaptcha 完全加载不出来。
这样，国内玩家就无法在对应的网站进行下一步操作了。本方案可以解决 reCaptcha 无法加载的问题。

适用平台: Chrome 电脑版，Firefox 电脑版，Firefox 手机版(Android)

适用范围: 大部分的 Google 人机验证的国内加载都可以用这个方案解决，包括多数网站的 reCaptcha 验证码。
本方案无法修改部分网站的 Content-Security-Policy。所以这个方案对于这部分网站是无效的。至于对哪部分网站无效请参见 FAQ。

请注意，由于方案的特殊性，少数网络情况下不一定成功。但是，大部分网络情况下都是可以成功的。

第一步 安装插件
本方案基于 Header Editor 插件。因此，您需要先在您的浏览器中安装这个插件。

下面是不同的浏览器对应的方法(请事先确定好你用的浏览器)。

提醒: 目前已重新上传可以用于 Chrome 最新版的离线插件。如果 Chrome 方案无法使用请使用 Firefox 方案。

第二步 配置插件
打开 Header Editor 插件的配置页面，选择“导入和导出”选项。

此处需要导入我写好的配置。这里提供两种方法。
方法1: 手动下载配置文件
方法2: 导入在线配置
接下来你应该会在“导入”看到相关规则(如果之前导入过，“操作”中的“添加”会显示为“覆盖已有”)。选择“保存”即可。

好了，关闭这个页面。然后就可以了，现在 reCaptcha 应该可以正常显示了。

原理
这个插件将 reCaptcha 的调用 (www.google.com/recaptcha) 直接跳转到了 reCaptcha 国内镜像上面 (recaptcha.net/recaptcha)。
由于 reCaptcha 国内镜像是可以直接连接的，而且还是 Google 官方的镜像，所以就能正常加载了。(这个和 xmdhs 的解决方法原理是一样的)

另外，这个方案还会修改页面的 Content-Security-Policy(内容安全政策) 设置，使得有 Content-Security-Policy 的页面的 reCaptcha 能正常加载。
