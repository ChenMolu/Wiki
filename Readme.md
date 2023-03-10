# Wiki知识库系统软件需求文档

## 项目介绍

日常学习过程中，我们往往会通过笔记来标注各种知识点。本项目通过JAVA EE技术，实现一个在线编辑和整理笔记电子书的知识库系统。本系统旨在规范化管理笔记，减少由于整理不当导致的时间损失，提高用户的工作学习效率。

项目基于 Spring Boot + Vue3 技术，最终实现一个方便部署、笔记内容可灵活配置的知识库系统。

## 项目背景

在当今社会，线上学习无疑是最高效最便捷的学习方法。它能够让你足不出户却能阅尽大家风采。在学习过程中，为了方便快捷的记录学习笔记，查看电子书籍，一套便捷的知识库系统无疑很有帮助。通过这个网站，用户能够使用到一个专属自己的、内容可灵活配置的知识库系统。

## 项目目的

本项目目的在于实现一个完整的网站，实现富文本框wangEditor，用户管理，用户登录，登录校验，文档阅读数，点赞数，定时任务，知识库，WebSocket网站通知，增加数据统计以及ECharts完成相关报表展示。这个网站能够帮助用户实现便捷高效的电子书笔记管理。

## 用户类别和特征

项目用户包括普通浏览者以及管理员。管理员有最高的权限，能够对项目系统中各个方面进行管理。普通浏览者用户则是只具备浏览，点赞以及评论权限。

## 运行环境

这个项目会在Windows和linux环境中运行，应兼容所有已知的浏览器的较新版本。使用该项目需要能够联网的设备即可。

## 系统功能

该系统的用户有：管理员和普通浏览者。

**管理员**可以进行用户管理、知识库文档管理以及文档标签分类管理。用户管理中直接分配可参与管理知识库的用户，所以在用户管理中也需要实现基本的增删改功能。知识库文档管理主要实现的功能为文档列表展示功能，文档编辑功能，文档新增功能以及文档删除功能。文档标签管理需要实现分类基本的增删改查以及标签如何进行分类，文档多重标签的处理。

**普通浏览者用户**可以在线浏览知识库系统中的文档，并对感兴趣的文档进行点赞和评论。同时，用户的文档浏览、点赞和评论等交互数据将在个人首页演示。

## 功能需求

在本项目中，实现一个网站作为自己的笔记知识库，除了有常规的笔记展示页面之外，还要实现用户模块、知识库文档管理模块，文档标签分类的管理，以及知识库阅读量、点赞量的统计首页。

- ### **知识库文档展示模块**

  除了展示文档的基本内容之外，还需要显示文章的阅读量、点赞量以及文档的目录树结构。在文档编辑功能上主要采用富文本编辑器。

- ### **用户模块**

​	由于知识库与其他系统不同，对于非管理员用户只提供浏览功能，因此也无需实现注册功能。只需要管理员，管理员可以在用户管理中直接分配可参与管理知识库的用户，所以在用户管理中也需要实现基本的增删改功能。

- ### **知识库文档管理模块**

​	该模块主要实现的功能为文档列表展示功能，文档编辑功能，文档新增功能以及文档删除功能。这里主要的难点在于知识库文档目录树的实现以及富文本编辑框的使用。这一模块主要是方便管理员来管理自己的知识库文档内容。

- ### **文档标签分类模块**

​		我们所有保存的文档都有其对应的分类标签，而我们要实现对这些分类功能的管理，因为在知识库首页展示就是基于标签进行的分类，需要实现分类基本的增删改查以及标签如何进行分类，文档多重标签的处理。

- ### **阅读数以及点赞数实现的功能模块**

​		有用户阅读文档是自动更新该篇文档的阅读数，以及实现文档的被点赞的功能。

- ### **首页数据统计模块**

​		通过对数据库中文档的阅读、点赞数据进行查询统计，在前端首页中实现数据的展示。

## 设计实现

- ### 前端（`Vue3` + `Vue CLI` ）

​       ` Vue` 是一款用于构建用户界面的 `JavaScript` 框架。它基于标准 `HTML`、`CSS` 和 `JavaScript` 构建，并提供了一套声明式的、组件化的编程模型，帮助你高效地开发用户界面。无论是简单还是复杂的界面，Vue 都可以胜任。

​         `Vue CLI` 致力于将` Vue` 生态中的工具基础标准化。它确保了各种构建工具能够基于智能的默认配置即可平稳衔接，这样可以专注在撰写应用上，而不必花好几天去纠结配置的问题。与此同时，它也为每个工具提供了调整配置的灵活性。

- ### 后端（`SpringBoot`）

​         `Spring Boot`是开发者和`Spring` 本身框架的中间层，帮助开发者统筹管理应用的配置，提供基于实际开发中常见配置的默认处理，简化应用的开发，简化应用的运维；总的来说，其目的`Spring Boot`就是为了对`Java web` 的开发进行“简化”和加“快”速度，简化开发过程中引入或启动相关Spring 功能的配置。这样带来的好处就是降低开发人员对于框架的关注点，可以把更多的精力放在自己的业务代码上。

- ### 数据库（`MySQL`）

​          `MySQL`是一种关系型数据库管理系统，关系数据库将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。



