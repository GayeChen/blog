AI Code评测

## 选手

Claude Code: 号称最强编程助手

Joycode（ 京东云 JoyCode，新一代智能编码 IDE 产品）： https://joycode.jd.com/

DongX.AI - 京东效能研发部 AI 样板间解决方案

以上选手都 在不同测试场景中使用相同prompt，都选用Claude4-Sonnet模型，


## 场景

##### 一、从祖传代码中封装通用组件


Claude Code: 


Joycode: 封装完组件以后，在组件替换步骤中，替换完模板有语法错误，然后自动撤销重试，进入了无限循环


DongX.AI: 封装完组件以后，在组件替换步骤中，由于模板太长截断了文件，并且自己无法修复，最终人工手动补全被截断的剩余内容，封装的组件无法正常工作，点击单选框卡死

