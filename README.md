# specifications
The ability to create functional and technical design specifications for development efforts is an essential skill for software engineers

# 用户账号管理规范

#### ID管理
* 将用户登录名影射为内部唯一ID，所有逻辑均基于该唯一ID。

#### 信息管理
* 将用户身份、个人信息区分开来。用户身份仅用于验证和登录，其他信息归入个人资料信息。
* 用户身份信息由本人管理。避免非用户本人获取或修改用户密码。
* 用户个人资料信息保留拓展字段，新增字段保存在副表中，以外键关联到拓展字段中。
* 每个账号都需要有状态字段，标识该账号正常使用、停用或删除等。
* 所有对于账号的“删除”操作，应该以修改用户状态字段来实现，避免在数据库中进行delete操作

#### 权限管理
* 按照级别进行用户增删查改四种操作。避免越级操作用户信息，避免越级指派任务。

#### 密码管理
* 用户密码进行单向加密之后保存在数据库中，避免以明文、可逆加密等形式保存用户密码。（参考[密码加密](http://blog.coderzh.com/2016/01/03/security-design/)）
* 考虑到彩虹表暴力解密的威胁，建议对密码加盐之后进行再加密。（参考[加盐加密](http://blog.coderzh.com/2016/01/10/a-password-security-design-example/)）
