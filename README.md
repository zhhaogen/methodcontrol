# 基于api方法的权限访问控制
在讲**基于api方法的权限访问控制**之前,先讲讲**基于角色的访问控制**,也即是rbac.
## 基于角色的访问控制
本质就是权限控制基于角色的身份，角色的身份就是超级管理员、管理员、普通员工等等。
* 这是一种金字塔形式的访问控制,比如超级管理员能做管理员的事，管理员能做普通员工的事，一层一层的分下来.
* 基于路径的控制,菜单控制多属于一种路径控制,比如不能访问某个路径
* 不易变更的权限,比如以管理员身份登录之后就很难将他降级为普通员工
* 难于用于复杂的业务流程,由于缺乏灵活的配置在业务过程中很难更加通用
## 基于api方法的权限访问控制
正如上面所述的rbac很多不足,产生基于api方法的权限访问控制.
### 例子1
项目重构,api方法名称变更,路径变更,或者服务路径变更,由于rbac配置的是路径，所以导致配置失效
### 例子2
普通用户在某个业务流程中，需要使用某个管理员才能用接口
### 例子3
登录用户，需要二次输入支付密码才能进行支付，其他业务则不需要支付密码
### 例子4
权限变更，普通员工平常不能使用会议室，申请后需要将使用会议室权限给他，注销后需要撤销会议室权限