## 表设置规则

三张表：

- users
- notifications
- topics



表设置如下：

users:

```javascript
// user
const users = [
  {
    id: 1,
    name: '小武',
    identity: 'student',
    isSelected: false,
  },
  {
    id: 2,
    name: '巍哥',
    identity: 'monitor',
    isSelected: false,
  },
  {
    id: 3,
    name: '哲神',
    identity: 'teacher',
    isSelected: false,
  },
  {
    id: 4,
    name: '小武1',
    identity: 'student',
    isSelected: false,
  },
];
```



notifications:

```javascript
// 通知消息
const notifications = [
  {
    id: 1,
    title: '答辩',
    content: '今天下午，我们在817开会',
  },
  {
    id: 2,
    title: '答辩1',
    content: '今天下午，我们在817开会1',
  },
];
```



topics:

```javascript
// 竞赛选题题目
const topics = [
  {
    id: 1,
    title: '电磁学',
    selecteddPerson: ['魏耀武', '黄巍']
  },
  {
    id: 2,
    title: '电磁学2',
    selectedPerson: ['魏耀武', '黄巍']
  },
];
```



### 规则1

notifications 与其他表无关



### 规则2

关于选课发布题目：

- 老师发布题目
- 同学们选择，一个同学选择，就往 topics 加入这个人，同时将这个人 isSelected 标志为 true，这个人不能在选择
- 当选择人数达到三人之后就不允许选择



关于选课删除题目：

- 老师删除题目
- 这个题目下的选择的人相对应的 isSelected 变为 false，那么这个人又可以选择题目



## 关于实现

如何实现：

- 设计表，三张表，以及他们之间的操作关系
- 使用mongodb 数据库，mongoose, 写出相应的 model，将表插入 数据库，存入相应的初始数据。
- 设计相应的 API，用来对数据库里面的数据：增删改查，使用 expressjs，和前后端分离的思想。
- 编写前端页面，展示数据库里面的数据，使用 React，create-react-app
- 完成前后端逻辑的交互。

