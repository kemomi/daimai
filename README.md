### 提前准备
* Python 3.6.3
* Chromedriver.exe
* Chrome 浏览器安装好后需将chromedriver.exe放置于Chrome浏览器目录下
* pip install selenium requests lxml

### 参数设置

在`config.json`中输入相应配置信息，具体说明如下：

* `date`: 日期选择
* `sess`: 场次优先级列表，如本例中共有三个场次，根据下表，则优先选择1，再选择2，最后选择3；也可以仅设置1个。
* `price`: 票价优先级，如本例中共有三档票价，根据下表，则优先选择1，再选择3；也可以仅设置1个。
* `real_name`: [1,2], 实名者序号，如本例中根据序号共选择两位实名者，根据序号，也可仅选择一位
  * 选择一位或是多位根据购票需知要求，
  * 若无需实名制信息则不需要填写，
  * 若一个订单仅需提供一位购票人信息则选择一位，
 * 若一张门票对应一位购票人信息则选择多位）。
 
* `nick_name`: 用户在大麦网的昵称，用于验证登录是否成功
* `ticket_num`: 购买票数
* `damai_url`: https://www.damai.cn, 大麦网官网网址
* `target_url`: https://detail.damai.cn/item.htm?id=599834886497  目标购票网址

* 部分门票需要选择城市，只需选择相应城市后将其网址复制到config.json文件的target_url参数即可。

* 根据需要选择的场次和票价分别修改config.json文件中的sess和price参数。

* 查看购票须知中实名制一栏，若无需实名制则config.json文件中的real_name参数不需要填写（即为[]）；若每笔订单只需一个证件号则real_name参数只需选择一个；若每张门票需要一个证件号，则real_name参数根据需购票数量进行相应添加。


* 若是首次登录，根据终端输出的提示，依次点击登录、扫码登录，代码将自动保存cookie文件（cookie.pkl）

* 使用前请将待抢票者的姓名、手机、地址设为默认。

* 配置完成后执行python damai_ticket.py即可,注意观察控制台输出。

* 本代码为保证抢票顺利，设置循环直到抢票成功才退出循环，若中途需要退出程序请直接终止程序。





### 更新
以下内容在博客：https://blog.csdn.net/weixin_35770067/category_10688081.html  付费专栏进行更新
* 2023.02.27：秀动解决本地时间和服务器时间不同步的bug
* 2023.02.26：针对观演人选择与否进行代码优化
* 2023.02.13: 大麦网支持捡漏
* 2022.09.13：微店bug完善,大麦抢票采用接口重新开发中
* 2022.08.30: 微店增加定时抢购和多账号抢购
* 2022.08.09: 微店增加request接口写法，高成功率
* 2022.08.04: 秀动、大麦增加QQ邮箱通知并修复已知bug
* 2022.08.02: 微店支持选购多张票，增加方糖通知
* 2022.07.27: 更新大麦滑块验证，自动识别
* 2022.07.20：增加微店下单模块
* 2022.07.17：增加微店抢票模块
* 2022.07.10：增加下单页面验证码自动识别模块
* 2022.04.20 更新正在现场抢票
* 2022.03.13：修复抢票选座功能
* 2022.01.28：更新秀动抢票
* 2022.01.22：增加支持自动选座功能

订阅CSDN文章后有问题，可以添加我的联系方式


感谢[Fly1nDutchman](https://github.com/ouyangjunfei?tab=repositories)在其他购票页面发现的问题，经过验证，我已经合并代码，特再次进行说明，表示感谢。

修复1：支持关闭实名制遮罩
* 测试地址：https://detail.damai.cn/item.htm?&id=662062693636
<p align="center">
<img width="500" src="https://user-images.githubusercontent.com/37463338/145715661-56e0a495-2809-461e-beb2-7030fbe8e748.png">
</p>

修复2：特惠场次有票但无法被选中的问题
* 测试地址： https://detail.damai.cn/item.htm?id=659519464426

修复3：支持日期选择
<p align="center">
<img width="500" src="https://user-images.githubusercontent.com/37463338/145716541-e74a3624-7ebf-45c0-ae64-c30e2211af9e.png">
</p>


### 热门演唱会信息
* [薛之谦演唱会](https://detail.damai.cn/item.htm?spm=a2oeg.search_category.0.0.57344206jb38CA&id=658630460380&clicktitle=%E8%96%9B%E4%B9%8B%E8%B0%A6%E2%80%9C%E5%A4%A9%E5%A4%96%E6%9D%A5%E7%89%A9%E2%80%9D%E5%B7%A1%E5%9B%9E%E6%BC%94%E5%94%B1%E4%BC%9A-%E5%B9%BF%E5%B7%9E%E7%AB%99)
* [李荣浩广州演唱会](https://detail.damai.cn/item.htm?spm=a2oeg.search_category.0.0.7e141ffaOOsGL3&id=660857675535&clicktitle=%E6%9D%8E%E8%8D%A3%E6%B5%A9%E2%80%9C%E9%BA%BB%E9%9B%80%E2%80%9D%E5%B7%A1%E5%9B%9E%E6%BC%94%E5%94%B1%E4%BC%9A%20%E5%B9%BF%E5%B7%9E%E7%AB%99)
* [北京保利·央华“神州九城，共享明天”2021演出行动 央华版 如梦之梦](https://detail.damai.cn/item.htm?spm=a2oeg.search_category.0.0.310919488fszNB&id=662432820667&clicktitle=%E4%BF%9D%E5%88%A9%C2%B7%E5%A4%AE%E5%8D%8E%E2%80%9C%E7%A5%9E%E5%B7%9E%E4%B9%9D%E5%9F%8E%EF%BC%8C%E5%85%B1%E4%BA%AB%E6%98%8E%E5%A4%A9%E2%80%9D2021%E6%BC%94%E5%87%BA%E8%A1%8C%E5%8A%A8%20%E5%A4%AE%E5%8D%8E%E7%89%88%E3%80%8A%E5%A6%82%E6%A2%A6%E4%B9%8B%E6%A2%A6%E3%80%8B)
* [周杰伦演唱会](https://m.damai.cn/damai/detail/item.html?itemId=607865020360&sqm=dianying.h5.unknown.value&spm=a2o71.project.0.i1)
