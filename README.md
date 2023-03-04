
### 更新

<div align="center">
   <img src="https://github.com/kemomi/daimai/blob/main/O1CN01QtSzD62GdSE1msrJp_!!2251059038.jpg" alt="logo"></br>
</div>
   

### 提前准备
* Python 3.6.3
* Chromedriver.exe
* Chrome 浏览器安装好后需将chromedriver.exe放置于Chrome浏览器目录下
* `pip install selenium requests lxml`

### 参数设置

在`config.json`中输入相应配置信息，具体说明如下：

* `date`: 日期选择
* `sess`: 场次优先级列表
* `price`: 票价优先级，如本例中共有三档票价，根据下表，则优先选择1，再选择3；也可以仅设置1个。
* `real_name`: [1,2], 实名者序号，根据序号共选择两位实名者，根据序号，也可仅选择一位  
*     #选择一位或是多位根据购票需知要求:若无需实名制信息则不需要填写;若一个订单仅需提供一位购票人信息则选择一位;若一张门票对应一位购票人信息则选择多位。
* `driver_path`:浏览器驱动地址
* `nick_name`: 用户在大麦网的昵称，用于验证登录是否成功
* `ticket_num`: 购买票数
* `damai_url`: https://www.damai.cn, 大麦网官网网址
* `target_url`: https://detail.damai.cn/item.htm?id=607865020360 目标，例如：[周杰伦2023嘉年华世界巡回演唱会--海口站](https://detail.damai.cn/item.htm?id=607865020360)


* 部分门票需要选择城市，只需选择相应城市后将其网址复制到config.json文件的`target_url`参数。

* 根据需要选择的场次和票价分别修改config.json文件中的`sess`和`price`参数。

* 查看购票须知中实名制一栏，若无需实名制则config.json文件中的`real_name`参数不需要填写（即为[]）；若每笔订单只需一个证件号则`real_name`参数只需选择一个；若每张门票需要一个证件号，则real_name参数根据需购票数量进行相应添加。


* 若是首次登录，根据终端输出的提示，依次点击登录、扫码登录，代码将自动保存cookie文件（cookie.pkl）

* 使用前请将待抢票者的姓名、手机、地址设为默认。

* 配置完成后执行`python damai_ticket.py`即可,注意观察控制台输出。

* 本代码为保证抢票顺利，设置循环直到抢票成功才退出循环，若中途需要退出程序请直接终止程序。






### 热门演唱会信息
* [周杰伦演唱会-天津](https://detail.damai.cn/item.htm?spm=a2oeg.search_category.searchtxt.ditem_0.f4294d15c5tGAZ&id=611160757855)
* [周杰伦演唱会-海口](https://detail.damai.cn/item.htm?id=607865020360)
* [周杰伦演唱会-呼和浩特](https://detail.damai.cn/item.htm?id=704967827554)
* [周杰伦演唱会-太原](https://detail.damai.cn/item.htm?id=704762591363)
