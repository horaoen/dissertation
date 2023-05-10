---
marp: true
theme: uncover
footer: '05/10/2023 by 方浩冉'
header: '滁州学院计算机与信息工程学院'
paginate: true
---
<style>
ul {
  font-size: 25px;
}
li {
  margin-top: 10px;
}
</style>
<style scoped>
h1 {
  color: blue;
}
h2 {
  font-size: 30px;
  margin-top: 150px;
}
</style>
# <!-- fit --> 基于SpringBoot的‘亭好住‘房屋租赁系统设计与实现
## 演讲人：方浩冉

---
## 研究现状
---

- 城市化加速，房屋租赁市场不可或缺
- 由于各地区的租房需求和市场情况不同，租房信息的精确度和及时性有待提高
- 平台提供的房源信息质量参差不齐，无法满足租房者和房东对房源信息的准确需求
- 平台的租房流程和服务标准不够统一和规范，导致用户体验不佳
- 随着市场竞争的激烈化，租房平台之间的恶性竞争现象也时有发生，给市场带来一定的不良影响
- 平台的租房流程和服务标准不够统一和规范，导致用户体验不佳

---
## 选题意义
---

- 有利于促进行业的信息化和智能化发展
- 提高租赁服务的质量和效率
- 为租户和房东提供更便捷的服务
- 提升租赁行业的竞争力和市场占有率

---
## 系统设计
---

![width:1000px](../screenshot/houserental_system.png)

---
## 架构设计
---

![width:830px](../screenshot/houserental_arch.png)

---
## 数据库设计
---

![width:800px](../screenshot/houserental_er.png)

---
## 系统实现
- [jenkins server](http://1.15.89.130:8080/)
- [后台管理系统](3.60.78.147)
- 源代码
  - [backend](https://gitee.com/horaoen/hourserental)
  - [frontend_admin](https://github.com/horaoen/thz_house_rental_admin)
  - [weichat_app](www.baidu.com)
  - [论文](https://github.com/horaoen/dissertation)
---
### CI/CD环境搭建
![width:950px](../screenshot/houserental_jenkins_servers.png)

---
![width:950px](../screenshot/houserental_jenkins_records.png)
---

---
![width:950px](../screenshot/houserental_admin_jenkins_records.png)

---
### 文件系统搭建
![width:950px](../screenshot/houserental_cos.png)
---
---
[X Spring File Storage](https://github.com/1171736840/spring-file-storage)
<font size="6">springboot中跨平台地将文件存储到云存储服务中</font>
---
---
## 后台管理系统路由系统搭建
---
<style scoped>
ol {
 font-size: 22px;
}
</style>
react router v6 配合状态管理工具recoil实现前端路由系统
1. 定义一个路由组件对象，对每一个路由和页面进行映射配置
2. 定义一个PrivateRoute组件，对每个需要权限控制的路由所映射组件进行包裹
3. PrivateRoute组件设计
   1. 从状态管理中获取token如果有则通过是私有路由
   2. 若没有尝试冲localStorage中获取token如果有则将token放入到状态管理中并通过私有路由
   3. 如果没有则重定向到登陆页
---
## 后端权限系统
