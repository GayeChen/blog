AI Code评测

## 选手

Claude Code: 号称最强编程助手

Joycode（ 京东云 JoyCode，新一代智能编码 IDE 产品）： https://joycode.jd.com/

DongX.AI - 京东效能研发部基于cline插件开发的AI样板间解决方案

以上选手 在不同测试场景中都使用相同prompt，选用相同模型：Claude4-Sonnet！！！


## 场景

##### 一、从祖传代码中封装通用组件

需求：从一个复杂的弹窗表单（校验、提交）中，抽取一部分单独封装组件

Claude Code: 表现最好，封装完组件以后，能完成组件替换，但是封装的组件无法正常工作，点击单选框卡死；继续追加对话，能够完成修复
<img width="1160" height="426" alt="image" src="https://github.com/user-attachments/assets/592e3680-9ad1-4c42-8cac-5d88507a9186" />



Joycode: 封装完组件以后，在组件替换步骤中，替换完模板有语法错误，然后自动撤销重试，进入了无限循环
<img width="876" height="672" alt="image" src="https://github.com/user-attachments/assets/617f405f-e030-4dc1-8760-a01aed610abb" />



DongX.AI: 封装完组件以后，在组件替换步骤中，由于模板太长截断了文件，并且自己无法修复，最终人工手动补全被截断的剩余内容，封装的组件无法正常工作，点击单选框卡死


##### 二、修复棘手bug
需求：一个弹窗表单中的NTreeSelect，选中值不能正常回显的bug


Claude Code: 修复，多次追问下，找到了问题在于NTreeSelect内部实现上，casader属性配置问题


DongX.AI： 未修复，追问了多次，反反复复，在字段类型上修改了半天，没有发现根本问题，最终没修复



## 各选手最频繁的问题

##### DongX.AI

经常因为文件太长，导致报错：Diff Edit Mismatch The model used search patterns that don't match anything in the file. Retrying...，而且无法恢复

<img width="1100" height="1518" alt="image" src="https://github.com/user-attachments/assets/ec44d453-c42d-44ae-b9f3-aab92d526432" />


