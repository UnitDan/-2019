# 课程模块——实验课界面与技术文档

## 需求&界面&核对接口

### 实验列表
进入实验课管理模块后，首页可见该教师所发布的所有实验.
![image.png](https://cdn.nlark.com/yuque/0/2019/png/156348/1554392159968-e4c7f86c-8572-47a3-aac7-d4c0fcb91b04.png#align=left&display=inline&height=581&name=image.png&originHeight=581&originWidth=1363&size=53798&status=done&width=1363)

每个实验有如下相应信息：
a. id
b. 实验名称
c. 开始时间
d. 结束时间
每个实验都对应如下操作：
a. 编辑：即编辑实验相关信息，如实验名称，实验描述，开始结束时间等。
b. 完成情况：每次实验学生完成情况相关的统计信息。
c. 查看某个实验详情，点击实验名称或者点击 `更多操作->详情 `  【添加删除实验接口】
d. 删除某个实验，点击  `更多操作->删除`

在实验列表界面有新建实验的按钮，点击可以新建并发布新实验。

#### API

- [ ] 获取我的某个课程的所有实验
**/teacher/lab/get-my-labs GET**


- [ ] 删除实验（新增）
**/teacher/lab/delete-lab POST**

### 新建实验
本页面可用于新建实验并发布。需要输入以下信息以新建一次实验：
a. 实验名称
b. 实验描述
c. 附件（点击上传文件后，出现上传文件弹窗，从本地选择文件上传即可。支持rar，zip，doc，docx，pdf，jpg等形式的文件。）【上传文件方式：先上传文件，再存数据库】
d. 练习题：点击选择题目，可从题库中选择数道题目作为练习题。【支持按id、名称、tag 搜索】 【添加获取所有题目列表】
e. 开始时间
f. 结束时间 
g. 选择该实验是否需要提交实验报告，方便在统计实验完成情况时显示必要的统计信息
【实验报告权重和作业权重问题未确定】
![image.png](https://cdn.nlark.com/yuque/0/2019/png/156348/1554392190111-cb8dbe57-bc1f-40dd-89eb-7d44f09babe5.png#align=left&display=inline&height=570&name=image.png&originHeight=570&originWidth=1360&size=41810&status=done&width=1360)<br />![image.png](https://cdn.nlark.com/yuque/0/2019/png/156348/1554392216137-3c3581c1-15af-4a33-bdf9-1e15cff6143e.png#align=left&display=inline&height=504&name=image.png&originHeight=504&originWidth=1359&size=30129&status=done&width=1359)

#### API

- [ ] 新建实验
**/teacher/lab/create-lab POST** <br />


- [ ] 添加某个实验的课件
**/teacher/lab/add-file POST(FILE)** 


- [ ] 删除某个实验的课件（更正参数类型 course_resource_id）
**/teacher/lab/delete-file POST** <br />

 

- [ ] 搜索题目（模糊查询%匹配） （替代原接口 get-problems）
**/teacher/lab/filter-problems POST**


【无需单独的预览界面，与实验详情页面合并在一起即可】

### 编辑实验
本页面用于修改已有实验的信息：
a. 实验名称
b. 实验描述
c. 附件：可追加新文件，或删除已有的文件 【删除实验课件接口参数 -> course_source_id (级联删除) 】
d. 练习题：可追加新题目，或删除已有题目
e. 开始时间
f. 截止时间
g. 是否需要提交实验报告
![image.png](https://cdn.nlark.com/yuque/0/2019/png/156348/1554392456315-7018093a-6de6-43ad-80ba-3c2286e49bf6.png#align=left&display=inline&height=572&name=image.png&originHeight=572&originWidth=1359&size=45571&status=done&width=1359)<br />![image.png](https://cdn.nlark.com/yuque/0/2019/png/156348/1554392436505-3b6ccd21-3080-4b82-be3e-c6f3fd199b24.png#align=left&display=inline&height=568&name=image.png&originHeight=568&originWidth=1362&size=40731&status=done&width=1362)

#### API

- [ ] 编辑实验
**/teacher/lab/edit-lab POST** <br />


**其他 API 和新建实验中的相同** 


### 实验详情
发布实验后，在实验列表中每个实验后提供查看详情的选项，点击实验名称或者 更多操作->详情 可显示某次实验的详细信息：
a. 实验名称
b. 开始时间
c. 结束时间
d. 当前时间
e. 实验描述
f. 附件：点击某特定文件即可下载
g. 练习题：点击题目名称进入题目详细信息页面
f. 实验是否需要提交实验报告
![image.png](https://cdn.nlark.com/yuque/0/2019/png/156348/1554395385012-7f258d67-5b4a-4a11-b940-13f2309e5f12.png#align=left&display=inline&height=566&name=image.png&originHeight=566&originWidth=1359&size=58236&status=done&width=1359)<br />![image.png](https://cdn.nlark.com/yuque/0/2019/png/156348/1554395395446-ceaebecf-5242-4364-8ec9-2a9d69b76873.png#align=left&display=inline&height=256&name=image.png&originHeight=256&originWidth=1361&size=24481&status=done&width=1361)

【添加一个编辑按钮可以进入编辑】 【language 用掩码表示】

#### API

- [ ] 获取某个实验的信息
**/teacher/lab/get-lab GET** <br />


- [ ] 下载某个实验的某个课件
**/teacher/lab/get-submission-file GET** 


- [x] 获取一个题目的详细信息** (题目组实现)**
**/teacher/problem/get-problem GET** 



# 分工

按照页面分工，韩凌昊组（韩凌昊、刘元浩、郭巍、何博）负责 **实验列表** 和 **实验详情** 页面，宋春颖组（宋春颖，潘忠杰、罗婕溪）负责 **新建实验** 和 **编辑实验** 页面。
