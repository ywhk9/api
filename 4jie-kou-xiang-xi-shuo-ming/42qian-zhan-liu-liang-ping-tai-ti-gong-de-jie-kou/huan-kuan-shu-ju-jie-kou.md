#### 4.2.2.1调用场景及流程

##### 4.2.2.1.1接口说明

合作渠道将用户的还款数据主运推送给钱站流量平台。

##### 4.2.2.1.2调用场景

\(1\)当用户申请的借款在合作渠道方还款成功后\(实时推送\);

\(2\)合作方定期将当天或历史还款数据推送过来\(定时推送\)。

#### 4.2.2.2调用接口要求

\(1\)性能要求:10s,超过10s后判断为超时。超时后不会重试。

\(2\)其它要求详见:3.2节;

#### 4.2.2.3请求数据说明

##### 4.2.2.3.1请求数据说明

**表8: 放款数据接口请求数据\(req\_data\)说明**

| 参数 | 类型 | 是否必传 | 描述 |
| :--- | :--- | :--- | :--- |
| camouflage\_id | String | 是 | 用户ID,在钱站流量平台的用户唯一标识 |
| order\_no | String | 是 | 用户在第三方借款ID |
| mobile | String | 是 | 手机号\(md5\) |
| id\_no | String | 是 | 身份证\(md5\) |
| repay\_all\_amount | double | 是 | 应还总额 |
| paid\_all\_amount | double | 是 | 已还总额 |
| repay\_time | Long | 是 | 应还日期 |
| repay\_amount | double | 是 | 当期还款金额 |
| bill\_status | Int | 是 | 账单状态1未到期;2已还款;3逾期 |
| pay\_type | Int | 是 | 还款方式类型 1=主动还款；2=跳转H5；4=银行代扣；5=同时支持主动还款和银行代扣 |
| repay\_success\_time | Long | 是 | 还款成功时间 |
| can\_repay\_time | Long | 是 | 当期最早可以还款的时间 |
| is\_able\_defer | Int | 否 | 此参数仅在支持展期时传递，0：不支持 1：支持 |

##### 4.2.2.3.2请求数据示例

**{**

```
**“req\_data”:\[**
```

**           {**

**                 "billStatus": 1,  
                 "camouflageId": "jidew4965y",**

**                 "idNo": "371521198526253305",**

**                 "mobile": "13813820202",**

**                 "orderNo": "2017202566360",**

**                  "paidAllAmount": 30000,**

**                  "repayAllAmount": 50000,**

**                  "repayAmount": 20000,**

**                  "repaySuccessTime": 1502939666262,**

**                  "repayTime": 1502939666264**

**          },**

**        { **

**                  "billStatus": 1,**

**                   "camouflageId": "jidew4965y",**

**                  "idNo": "371521198526253305",**

**                  "mobile": "13813820202",**

**                  "orderNo": "2017202566361",**

**                  "paidAllAmount": 30000,**

**                  "repayAllAmount": 50000,**

**                  "repayAmount": 20000,**

**                  "repaySuccessTime": 1502939666265,**

**                  "repayTime": 1502939666265**

**        },**

**       {**

**                  "billStatus": 1, **

**                  "camouflageId": "jidew4965y",**

**                  "idNo": "371521198526253305",**

**                  "mobile": "13813820202",**

**                  "orderNo": "2017202566362",**

**                  "paidAllAmount": 30000,**

**                  "repayAllAmount": 50000,**

**                  "repayAmount": 20000,**

**                  "repaySuccessTime": 1502939666265, **

**                  "repayTime": 1502939666265**

**         }**

**     \]**

**}**

**注意：req\_data为JsonArray格式**

#### 4.2.2.4响应参数说明

此接口的成功响应数据code=“200”，msg=“成功”，data的值为一个JSON格式的数据。

![](/assets/success.png)

##### **4.2.2.4.2异常响应示例**

![](/assets/exception.png)

