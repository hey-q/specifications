## API文档编写规则

#### API文档格式

1. 接口文档组织形式，与代码组织形式一致。
2. 每一接口需提供至少以下信息
 * 接口名称
 * 接口地址
 * 访问方式(post/get)
 * 接口简介
 * 接收参数说明
 * 请求数据示例
 * 返回参数说明
 * 返回数据示例


 #### 全局错误返回

 接口返回值常量化，每一常量有常量名、int类型的返回值、返回值说明

 常量名 | 返回值 | 返回值说明
 -- | -- | --
 SUCCESS | 10000 | 接口访问成功
 USER_NOT_FOUND | 10001 | 找不到该用户

 #### 接口安全校验

 一般的做法，是通过ticket完成校验，具体方案由架构师设计。接口一定要做安全校验。