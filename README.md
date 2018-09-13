# alipay_webpay_with_laravel
Laravel框架下集成支付宝电脑网站支付

说明
=====
因本人最近学习了Lavavel框架，所以打算将支付宝的电脑网址支付功能进行集成。当然其他功能也可以集成，这边先以电脑网址支付为例。因之前编写的类不适合Laravel框架，特做以下修改

>修改说明：

1.修改文件名"alipay.trade.page.pay-PHP-UTF-8" 为 "alipay_webpay_with_laravel"

2.删除readme.txt、idnex.php、notify_url.php、return_url.php

3.新增dataHandle.php文件，该文件为自定义文件用于调用支付宝下单及回调验签功能

4.修改aop/AopEncrypt.php、aop/AopClient.php、lotusphp_runtime/Cookie/Cookie.php三个文件下的“encrypt”、“decrypt”方法，分别替换为“alipayEncrypt”、“alipayDecrypt”。当然具体修改名称也可以自定义，只需要不给系统方法冲突就行。具体可参考该链接：http://www.itinfor.cn/archives/1762

5.修改aop\AopClient.php 文件下第 413 行 each方法，将其修改为“foreach ($para_temp as $key => $val) {”即可，具体可参考该链接：http://www.itinfor.cn/archives/1753



>使用说明：
1. 请先前配置根目录下config.php文件

2. 使用composer进行安装，具体命令如下 composer require paopao7/alipay_webpay_with_laravel

3. 在需要使用的文件顶部，先use一下，具体代码如下：use paopao7\alipay_webpay_with_laravel;

4. 在需要调用获取支付参数的地方，先实例化 alipay_webpay_with_laravel 类
   然后再调用 go_pay 方法，传入需要支付的金额和订单号 即可
   具体代码如下：
   $alipay_webpay_with_laravel = new composer_test\alipay_webpay_with_laravel();
   $result = $alipay_webpay_with_laravel->test(0.01,"20180913094216");

   return $result;



>使用说明：

具体使用请参考该链接：

>联系方式：(添加请注明技术咨询)

本人QQ：980569038
TP集成支付宝群：594955172
