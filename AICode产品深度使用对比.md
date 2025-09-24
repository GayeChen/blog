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

##### 三、疑难问题解决
需求：希望在codemirro中完整展示大数字，并且看起来格式没变，不能显示引号

Prompt：
如下图所示，有这样的问题，codemirror中显示的number类型和右侧接口响应的数字不一致， "id2": 5.079056950790569e+39, 和 接口响应中："id2": 5079056950790569507905695079056950790569,并不一样，我希望codemirror的显示和接口响应完全一致，给我一个方案

Joycode: 失败：给出了主要方案，但是在codemirror中，展示了字符串，不符合预期，多次追加要求，还是无法完成任务
<img width="716" height="308" alt="image" src="https://github.com/user-attachments/assets/d0071995-9cae-4e4e-b8cd-e7de76ca70d9" />



DongX.AI：失败：表现并且最拉胯，只提供了核心解析函数

Claude Code: 成功：开始也是只提供了核心解析函数，一步步引导下，最终实现所有预期



## 各选手最频繁的问题

##### DongX.AI

经常因为文件太长，导致报错：Diff Edit Mismatch The model used search patterns that don't match anything in the file. Retrying...，而且无法恢复

<img width="1100" height="1518" alt="image" src="https://github.com/user-attachments/assets/ec44d453-c42d-44ae-b9f3-aab92d526432" />

##### JoyCode

在复杂的老页面替换复用一个公共组件时，出现语法报错，然后开始撤销代码，然后重新修改又出现语法报错，反反复复
<img width="1078" height="1316" alt="image" src="https://github.com/user-attachments/assets/851f647a-4650-4f5b-90bc-1cbdc6a5391c" />

