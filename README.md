# Zalv_generate
Dynamic ALv generation
Alv程序生成器

ABAP版本：由于新语法的使用需要 740或更高的版本

设计目标：动态的划分屏幕，并动态绑定Alv与内表

包含对象：

ZCL_ALV_DATA( 用于取数的类)

ZCL_ALV_DISPLAY（Alv展示类）

ZCL_EVENT_RECEIVER（Alv事件处理类）

ZGIT_ALV_GENERATE（ALV生成程序）TCODE:ZALV_GENERATE

ZGIT_ALV（作为程序的copy源程序存在）

ZSGIT_ALV（作为内表标准处理结构）

使用前提：

1：如需要启用标准日志功能，需要导入https://github.com/epeterson320/ABAP-Logger ，未防止出错程序里已在单击事件里注释

2：如需启用程序监控功能，需要导入https://github.com/Limiter-hao/zreport_monitor

3：因为单击事件中增加了icon按钮的单击弹窗功能，因为需导入falv  https://github.com/fidley/falv

使用说明：

1：运行ZGIT_ALV_GENERATE程序，输入要生成的程序名，标题，选择要生成的alv模式，并勾选相关的要启用的功能

2：生成的程序中，内表中会添加ZSGIT_ALV结构，用户单据处理的记录信息字段包括：

ICON 处理状态

MSG 处理消息

BALOGNR 日志号

SEL 选择标记

BAPIRETTAB bapi消息返回表

3：程序默认已开启icon按钮单击功能，点击该按钮，如果程序已开启日志功能，会弹窗显示该条的处理日志，如果没有，会弹窗消息bapirettab的bapi消息

4：大部分的alv事件处理方法在父类zcl_event_receiver中有示例，功能运行健全，已经在正式系统中得到了完美的实践.

5：更多的功能期待你的发现



