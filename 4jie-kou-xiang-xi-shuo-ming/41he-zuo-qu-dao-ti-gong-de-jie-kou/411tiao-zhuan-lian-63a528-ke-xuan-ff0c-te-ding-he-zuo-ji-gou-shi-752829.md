## 4.1.1.1调用场景及流程

### 4.1.1.1.1接口说明

        用户登录钱站后在贷款产品列表页面点击“申请贷款”时钱站平台会重定向到合作机构提供的跳转链接。

        跳转时会将参数拼接至url上跳转至合作机构。 

        参数:

| 参数名称 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| channel\_key | String | 是 | 钱站流量平台唯一标识,固定 值:”qzllpt” |
| camouflage\_id | String | 是 | 钱站流量平台用 户唯一标识,合作机构需要存储下来,作为以后接口交互的唯一用户标识 |

         示例:

         https://xxx.xxx/xx?channel\_key=xxxxxxxxxxxx&camouflage\_id=xxxxxxxxxxxxxxxxxx
