# 京西商城

## 练习要求
现有一京西商城线下零售店王老板，发现随着互联网的普及，越来越多的人喜欢在在线上购买物品，直接配送到家，足不出户就可以获取日常用品。
反观自己的线下零售店，周内店里客人寥寥无几，为了顺应时代的潮流，提高业绩，于是想委托你帮他开发一款名为"京西商城"的在线网站。
方便顾客的购买，为用户提供优质的服务，使得自己商城的业绩能够提升。

### 业务需求

**买家**
- 作为一个买家，我想便捷地查询商品，以便快速找到我想购买的商品。
- 作为一个买家，我想轻松创建订单，以便购买我想要的商品。
- 作为一个买家，我想支付我的订单，以便为我购买的商品付款。
- 作为一个买家，当决定放弃购物时，我想快速撤销订单，以避免产生不必要的花销。
- 作为一个买家，我想随时查询我的订单，以便获得订单的详细信息，包括订单详情和物流状态。
- 作为一个买家，我想查询我的全部订单，以便回顾过往订单信息。
- 作为一个买家，我想直接根据快递单号查询快递单，以便及时掌握物流状态。
- 作为一个买家，当购买的货物到达时，我想方便地签收，以便开始使用买到的商品。

**仓库管理员**
- 作为一个仓库管理员，我想添加商品，以便上新更多的商品。
- 作为一个仓库管理员，我想修改商品，以便更新商品信息。
- 作为一个仓库管理员，我想创建商品的库存信息，以便记录已有商品的库存信息。
- 作为一个仓库管理员，我想修改商品的库存数量，以便锁定或解锁库存数量，保证一个商品不会被多个人同时下单。

**快递员**
- 作为一个快递员，我想修改快递单，以便更新物流状态。

### 功能要求

**商品**
- 当添加商品时，输入商品的`名称`，`描述`，`价格`，系统应该创建商品，同时创建对应的库存数量为0。
- 当修改商品时，输入商品的`名称`，`描述`，`价格`，系统应该对商品信息进行修改。
- 当查询商品时，输入查询文本，系统应该对商品的`名称`和`描述`进行模糊查询，并返回包含查询文本的商品。

**库存信息**
- 当锁定商品的库存数量时，输入锁定的数量，系统应该保证该商品的锁定库存数量不会被多个订单重复购买。
- 当修改商品的库存数量时，输入修改的数量，系统应该更新该商品的实际库存数量。
 
**订单**
- 当创建订单时，输入要购买的商品ID，和购买数量，系统应该创建订单，同时创建对应商品的货物信息，并锁定对应商品的库存数量，计算总价。
- 当支付订单时，系统应该修改订单状态，同时记录时间，并为支付成功的订单创建快递单，同时设置快递单状态。
- 当撤销订单时，系统应该修改订单状态，同时记录时间、解锁库存数量。
- 当查询订单时，系统应该根据订单ID一次查询出订单信息、订单中所有货物的信息、物流信息。
- 当用户查询自己所拥有的全部订单时，系统应该根据用户ID查看该用户的所有订单信息。

**快递单**  
- 当发货时，系统应该修改快递单的状态，同时记录时间。
- 当查询快递单时，系统应该查看快递单的详细信息。
- 当签收时，系统应该修改快递单的状态，同时修改订单状态并记录时间，减少库存信息的真实数量。

Note：
- 以上角色的登陆和权限验证等安全机制，不在本题要求内
- 货物信息即商品的快照，该信息生成后不允许修改，用于记录订单创建时该商品的信息
- 不考虑退换货

### 题目要求
- 使用Jenkins持续集成，基于Docker中的Jenkins镜像
- 使用MySQL作为数据存储，基于Docker中的MySQL镜像
- 使用Postman对API进行测试
- 使用Newman对Postman中的API进行集成测试
- 将Jenkins job的运行日志截图，并命名为`result.png`

## 环境要求
- java8
- Intellij-IDEA

## 如何开始
- 使用[Spring Initializr](https://start.spring.io/)搭建基础Spring Boot项目
- 将`collection.json`拷贝到Spring Boot项目的根目录下
- 将项目提交到Github
- 在Jenkins中创建一个Freestyle类型的job，设置trigger使得Github仓库一提交代码就会build，对项目进行持续集成
- 在Jenkins中配置使用Newman对项目中的API进行测试
- 此时构建Jenkins job会失败，可以开始根据题目需求完成API

## 输出规范
- 项目应包含京西商城的功能实现代码
- 项目根目录下应包含`result.png`
