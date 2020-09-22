# 字典管理接口文档

## 1.版本说明

| 版本   | 修改内容 | 修改人 | 修改日期   |
| ------ | -------- | ------ | ---------- |
| v1.0.0 | 初始版本 | 秦源   | 2020/09/04 |

## 2. 接口设计

### 2.1 Monitor-controller
- 服务名称：
- 功能描述：监控接口
- 接口地址：/ops/monitor
- 请求方式: GET 
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无



##### 返回示例：

```
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "status" : "string",
    "version" : "string"
  },
  "traceId" : "string"
}
```




##### 

##### 返回参数：


| 名称                    | 说明                  | 类型                                    |
| ----------------------- | --------------------- | --------------------------------------- |
| **code**  <br>*必填*    | 返回状态码            | integer (int32)                         |
| **data**  <br>*可选*    | 返回对象              | [MonitorResultInfo](#monitorresultinfo) |
| **message**  <br>*可选* | 返回信息              | string                                  |
| **traceId**             | 请求唯一标识          | string                                  |
| **status**  <br>*可选*  | **样例** : `"string"` | string                                  |
| **version**  <br>*可选* | **样例** : `"string"` | string                                  |

### 2.2 号段API
#### 2.2.1 保存号段

- 服务名称：
- 功能描述：监控接口
- 接口地址：/api/number/range/v1/applyNumberRange
- 请求方式: POST 
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无



##### 请求示例：

```
{
  "childNumberRange" : [ {
    "childNumberRange" : [ "..." ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  } ],
  "code" : 0,
  "createTime" : "string",
  "expCode" : 0,
  "length" : 0,
  "name" : "string",
  "numEnd" : 0,
  "numStart" : 0,
  "parentCode" : 0,
  "rule" : "string",
  "status" : 0,
  "type" : 0
}
```



##### 请求参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |


##### 

##### 返回示例：
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```



##### 返回参数：


| 名称                    | 说明         | 类型            |
| ----------------------- | ------------ | --------------- |
| **code**  <br>*必填*    | 返回状态码   | integer (int32) |
| **data**  <br>*可选*    | 返回对象     | Object          |
| **message**  <br>*可选* | 返回信息     | string          |
| **traceId**             | 请求唯一标识 | string          |

#### 2.2.2 更新状态

- 服务名称：
- 功能描述：更新状态
- 接口地址：/api/number/range/v1/changeStatusNumberRange
- 请求方式: POST 
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无



##### 请求示例：

```
{
  "childNumberRange" : [ {
    "childNumberRange" : [ "..." ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  } ],
  "code" : 0,
  "createTime" : "string",
  "expCode" : 0,
  "length" : 0,
  "name" : "string",
  "numEnd" : 0,
  "numStart" : 0,
  "parentCode" : 0,
  "rule" : "string",
  "status" : 0,
  "type" : 0
}
```



##### 请求参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |


##### 

##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```



##### 返回参数：


| 名称                    | 说明         | 类型            |
| ----------------------- | ------------ | --------------- |
| **code**  <br>*必填*    | 返回状态码   | integer (int32) |
| **data**  <br>*可选*    | 返回对象     | Object          |
| **message**  <br>*可选* | 返回信息     | string          |
| **traceId**             | 请求唯一标识 | string          |



#### 2.2.3 查询空闲的号段

- 服务名称：
- 功能描述： 查询空闲的号段
- 接口地址：/api/number/range/v1/free
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Query**|**code**  <br>*必填*|号段code|integer (int64)||



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : "object",
  "traceId" : "string"
}
```



##### 返回参数：


| 名称                    | 说明         | 类型            |
| ----------------------- | ------------ | --------------- |
| **code**  <br>*必填*    | 返回状态码   | integer (int32) |
| **data**  <br>*可选*    | 返回对象     | Object          |
| **message**  <br>*可选* | 返回信息     | string          |
| **traceId**             | 请求唯一标识 | string          |



#### 2.2.4 根据号段名称获取号段

- 服务名称：
- 功能描述： 根据号段名称获取号段
- 接口地址：/api/number/range/v1/getByName
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Query**|**name**  <br>*必填*|号段名称|string||


##### 


##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |



#### 2.2.5 根据号段名称获取下级号段

- 服务名称：
- 功能描述： 根据号段名称获取下级号段
- 接口地址：/api/number/range/v1/getByNameForDown
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Query**|**name**  <br>*必填*|号段名称|string||



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |

#### 2.2.6 根据号段code获取号段

- 服务名称：
- 功能描述： 根据号段code获取号段
- 接口地址：/api/number/range/v1/queryNumberRangeByCode
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Query**|**code**  <br>*必填*|号段code|integer (int64)||


##### 

##### 返回示例：
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |



#### 2.2.7 根据code查询扩充号段

- 服务名称：
- 功能描述： 根据code查询扩充号段
- 接口地址：/api/number/range/v1/queryNumberRangeForExp
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Query**|**code**  <br>*必填*|号段code|integer (int64)||



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |



#### 2.2.7 根据name或父code查询号段,返回树

- 服务名称：
- 功能描述：根据name或父code查询号段,返回树
- 接口地址：/api/number/range/v1/queryNumberRangeForTree
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Query**|**name**  <br>*可选*|号段名称|string||
|**Query**|**parentCode**  <br>*可选*|父code|integer (int64)|`0`|



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |



### 2.3 号段管理

#### 2.3.1 更新状态

- 服务名称：
- 功能描述：更新状态
- 接口地址：/number/range/v1/changeStatusNumberRange
- 请求方式: POST
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无



##### 请求示例：

```
{
  "childNumberRange" : [ {
    "childNumberRange" : [ "..." ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  } ],
  "code" : 0,
  "createTime" : "string",
  "expCode" : 0,
  "length" : 0,
  "name" : "string",
  "numEnd" : 0,
  "numStart" : 0,
  "parentCode" : 0,
  "rule" : "string",
  "status" : 0,
  "type" : 0
}
```



##### 请求参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |


##### 

##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```



##### 返回参数：


| 名称                    | 说明         | 类型            |
| ----------------------- | ------------ | --------------- |
| **code**  <br>*必填*    | 返回状态码   | integer (int32) |
| **data**  <br>*可选*    | 返回对象     | Object          |
| **message**  <br>*可选* | 返回信息     | string          |
| **traceId**             | 请求唯一标识 | string          |

#### 2.3.2 查询空闲的号段

- 服务名称：
- 功能描述：查询空闲的号段
- 接口地址：/number/range/v1/free
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无



##### 请求参数：

| 类型      | 名称                 | 说明     | 类型            | 默认值 |
| --------- | -------------------- | -------- | --------------- | ------ |
| **Query** | **code**  <br>*必填* | 号段code | integer (int64) |        |



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : "object",
  "traceId" : "string"
}
```



##### 返回参数：


| 名称                    | 说明         | 类型            |
| ----------------------- | ------------ | --------------- |
| **code**  <br>*必填*    | 返回状态码   | integer (int32) |
| **data**  <br>*可选*    | 返回对象     | Object          |
| **message**  <br>*可选* | 返回信息     | string          |
| **traceId**             | 请求唯一标识 | string          |



#### 2.3.3 根据name或父code查询号段



- 服务名称：
- 功能描述：根据name或父code查询号段
- 接口地址：/number/range/v1/queryNumberRange
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

| 类型      | 名称                       | 说明     | 类型            | 默认值 |
| --------- | -------------------------- | -------- | --------------- | ------ |
| **Query** | **name**  <br>*可选*       | 号段名称 | string          |        |
| **Query** | **parentCode**  <br>*可选* | 父code   | integer (int64) | `0`    |



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |

#### 2.3.4 根据号段code获取号段
- 服务名称：
- 功能描述： 根据号段code获取号段
- 接口地址：/number/range/v1/queryNumberRangeByCode
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

| 类型      | 名称                 | 说明     | 类型            | 默认值 |
| --------- | -------------------- | -------- | --------------- | ------ |
| **Query** | **code**  <br>*必填* | 号段code | integer (int64) |        |


##### 

##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |

#### 2.3.5 根据code查询扩充号段
- 服务名称：
- 功能描述： 根据code查询扩充号段
- 接口地址：/number/range/v1/queryNumberRangeForExp
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

| 类型      | 名称                 | 说明     | 类型            | 默认值 |
| --------- | -------------------- | -------- | --------------- | ------ |
| **Query** | **code**  <br>*必填* | 号段code | integer (int64) |        |



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |



#### 2.3.6 根据name或父code查询号段,返回树



- 服务名称：
- 功能描述：根据name或父code查询号段,返回树
- 接口地址：/number/range/v1/queryNumberRangeForTree
- 请求方式: GET
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无




##### 请求参数：

| 类型      | 名称                       | 说明     | 类型            | 默认值 |
| --------- | -------------------------- | -------- | --------------- | ------ |
| **Query** | **name**  <br>*可选*       | 号段名称 | string          |        |
| **Query** | **parentCode**  <br>*可选* | 父code   | integer (int64) | `0`    |



##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "childNumberRange" : [ {
      "childNumberRange" : [ "..." ],
      "code" : 0,
      "createTime" : "string",
      "expCode" : 0,
      "length" : 0,
      "name" : "string",
      "numEnd" : 0,
      "numStart" : 0,
      "parentCode" : 0,
      "rule" : "string",
      "status" : 0,
      "type" : 0
    } ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  },
  "traceId" : "string"
}
```



##### 返回参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |

#### 2.3.7 保存号段
- 服务名称：
- 功能描述：保存号段
- 接口地址：/number/range/v1/applyNumberRange
- 请求方式: POST 
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无



##### 请求示例：

```
{
  "childNumberRange" : [ {
    "childNumberRange" : [ "..." ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  } ],
  "code" : 0,
  "createTime" : "string",
  "expCode" : 0,
  "length" : 0,
  "name" : "string",
  "numEnd" : 0,
  "numStart" : 0,
  "parentCode" : 0,
  "rule" : "string",
  "status" : 0,
  "type" : 0
}
```



##### 请求参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |


##### 

##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```



##### 返回参数：


| 名称                    | 说明         | 类型            |
| ----------------------- | ------------ | --------------- |
| **code**  <br>*必填*    | 返回状态码   | integer (int32) |
| **data**  <br>*可选*    | 返回对象     | Object          |
| **message**  <br>*可选* | 返回信息     | string          |
| **traceId**             | 请求唯一标识 | string          |

#### 2.3.8 更新号段

- 服务名称：
- 功能描述：更新号段
- 接口地址：/number/range/v1/updateNumberRange
- 请求方式: POST 
- 数据提交方式：application/json
- 注意事项：权限校验
- 依赖描述：无



##### 请求示例：

```
{
  "childNumberRange" : [ {
    "childNumberRange" : [ "..." ],
    "code" : 0,
    "createTime" : "string",
    "expCode" : 0,
    "length" : 0,
    "name" : "string",
    "numEnd" : 0,
    "numStart" : 0,
    "parentCode" : 0,
    "rule" : "string",
    "status" : 0,
    "type" : 0
  } ],
  "code" : 0,
  "createTime" : "string",
  "expCode" : 0,
  "length" : 0,
  "name" : "string",
  "numEnd" : 0,
  "numStart" : 0,
  "parentCode" : 0,
  "rule" : "string",
  "status" : 0,
  "type" : 0
}
```



##### 请求参数：

| 名称                             | 说明                                                         | 类型                                  |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------- |
| **childNumberRange**  <br>*可选* | 存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]` | < [NumberRange](#numberrange) > array |
| **code**  <br>*可选*             | 号段code  <br>**样例** : `0`                                 | integer (int64)                       |
| **createTime**  <br>*可选*       | 创建时间  <br>**样例** : `"string"`                          | string                                |
| **expCode**  <br>*可选*          | 扩展code  <br>**样例** : `0`                                 | integer (int64)                       |
| **length**  <br>*可选*           | 号段长度  <br>**样例** : `0`                                 | integer (int64)                       |
| **name**  <br>*可选*             | 号段名称  <br>**样例** : `"string"`                          | string                                |
| **numEnd**  <br>*可选*           | 号段结束号  <br>**样例** : `0`                               | integer (int64)                       |
| **numStart**  <br>*可选*         | 号段起始号  <br>**样例** : `0`                               | integer (int64)                       |
| **parentCode**  <br>*可选*       | 号段上级code  <br>**样例** : `0`                             | integer (int64)                       |
| **rule**  <br>*可选*             | 号号段规则描述  <br>**样例** : `"string"`                    | string                                |
| **status**  <br>*可选*           | 号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`         | integer (int32)                       |
| **type**  <br>*可选*             | 号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0` | integer (int32)                       |


##### 

##### 返回示例：

```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```



##### 返回参数：


| 名称                    | 说明         | 类型            |
| ----------------------- | ------------ | --------------- |
| **code**  <br>*必填*    | 返回状态码   | integer (int32) |
| **data**  <br>*可选*    | 返回对象     | Object          |
| **message**  <br>*可选* | 返回信息     | string          |
| **traceId**             | 请求唯一标识 | string          |

### 2.3 

### 字典映射管理

Dictionary Map Controller


<a name="deletedictionarymapusingdelete"></a>
#### 删除映射组
```
DELETE /dictionary/map/v1/deleteDictionaryMap/{code}/{extCode}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**code**  <br>*必填*|需要删除的字典code|string||
|**Path**|**extCode**  <br>*必填*|需要删除的映射组code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«int»](#26ef25ee01b21e621d9886c47b8b6fed)|
|**204**|No Content|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/map/v1/deleteDictionaryMap/string/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```


<a name="savedictionarymapusingpost"></a>
#### 新增映射组
```
POST /dictionary/map/v1/saveDictionaryMap
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**dictionaryMap**  <br>*必填*|dictionaryMap|[DictionaryMap](#dictionarymap)||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«int»](#26ef25ee01b21e621d9886c47b8b6fed)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/map/v1/saveDictionaryMap
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
{
  "code" : 0,
  "extCode" : 0,
  "mapCode" : 0
}
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```


<a name="savedictionarymaplistusingpost"></a>
#### 批量增加映射组
```
POST /dictionary/map/v1/saveDictionaryMapList
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**dictionaryMapList**  <br>*必填*|dictionaryMapList|< [DictionaryMap](#dictionarymap) > array||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«DictionaryMap»»](#073be25547d743821db8a8c77fc8fe13)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/map/v1/saveDictionaryMapList
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
[ {
  "code" : 0,
  "extCode" : 0,
  "mapCode" : 0
} ]
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "extCode" : 0,
    "mapCode" : 0
  } ],
  "traceId" : "string"
}
```


<a name="updatedictionarymapusingput"></a>
#### 修改映射组信息
```
PUT /dictionary/map/v1/updateDictionaryMap
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**dictionaryMap**  <br>*必填*|dictionaryMap|[DictionaryMap](#dictionarymap)||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«int»](#26ef25ee01b21e621d9886c47b8b6fed)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/map/v1/updateDictionaryMap
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
{
  "code" : 0,
  "extCode" : 0,
  "mapCode" : 0
}
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```


<a name="76e9a50ab93291cc180a83401e3df3f2"></a>
### 字典查询
Dictionary Query Controller


<a name="querybymapnameusingget"></a>
#### 根据映射组名查询该映射组下的所有映射关系
```
GET /dictionary/management/v1/queryByMapName/{mapName}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**mapName**  <br>*必填*|映射名称|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«DictionaryMapParam»»](#94eb8c0ff6c5c3b89c93b28d0951abdd)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryByMapName/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "extCode" : 0,
    "mapCode" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querybyparentcodeusingget"></a>
#### 根据字典ID获取下级字典
```
GET /dictionary/management/v1/queryByParentCode/{parentCode}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**parentCode**  <br>*必填*|父类code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryByParentCode/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querydictionarybycodeusingget"></a>
#### 查询字典信息
```
GET /dictionary/management/v1/queryDictionaryByCode/{code}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**code**  <br>*必填*|字典code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«SystemDictionary»](#38a2423e7b52a1a2a10a8c6ed54f4007)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryDictionaryByCode/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  },
  "traceId" : "string"
}
```


<a name="querydictionarybyconditionusingpost"></a>
#### 按条件查询字典列表
```
POST /dictionary/management/v1/queryDictionaryByCondition
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**dictionaryConditionParam**  <br>*必填*|dictionaryConditionParam|[DictionaryConditionParam](#dictionaryconditionparam)||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryDictionaryByCondition
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
{
  "code" : 0,
  "ranId" : 0,
  "status" : 0,
  "value" : "string"
}
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querydictionarybyextcodeusingget"></a>
#### 根据映射外部id查询对应字典
```
GET /dictionary/management/v1/queryDictionaryByExtCode/{extCode}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**extCode**  <br>*必填*|映射外部code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«SystemDictionary»](#38a2423e7b52a1a2a10a8c6ed54f4007)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryDictionaryByExtCode/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  },
  "traceId" : "string"
}
```


<a name="querydictionarybygroupcodeandranidusingpost"></a>
#### 根据所属号段和分组查询分配或者未分配的字典列表信息
```
POST /dictionary/management/v1/queryDictionaryByGroupCodeAndRanId
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**queryDictionaryParam**  <br>*必填*|queryDictionaryParam|[QueryDictionaryParam](#querydictionaryparam)||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«DictionaryResult»»](#845c1de5ce0902d97b6158098ee9f196)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryDictionaryByGroupCodeAndRanId
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
{
  "groupCode" : "string",
  "isAllocate" : 0,
  "ranId" : "string"
}
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "ranId" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querydictionarybygrouptypeusingget"></a>
#### 根据分组类型查询字典列表信息
```
GET /dictionary/management/v1/queryDictionaryByGroupType/{groupType}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**groupType**  <br>*必填*|分组类型（1-分组 2-映射组 0-字典）|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryDictionaryByGroupType/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querydictionarybymapnameusingget"></a>
#### 根据映射组名该映射组下所有查询字典
```
GET /dictionary/management/v1/queryDictionaryByMapName/{mapName}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**mapName**  <br>*必填*|映射组名|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryDictionaryByMapName/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querydictionarylistbyextcodeusingpost"></a>
#### 根据映射外部id查询对应字典(批量查询)
```
POST /dictionary/management/v1/queryDictionaryListByExtCode
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**extCodeList**  <br>*必填*|映射外部code集合|< string > array||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryDictionaryListByExtCode
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
[ "string" ]
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querymutexcodebycodeusingget"></a>
#### 根据字典ID获取互斥字典
```
GET /dictionary/management/v1/queryMutexCodeByCode/{mutexCode}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**mutexCode**  <br>*必填*|互斥code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryMutexCodeByCode/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querymutexcodebyranidusingget"></a>
#### 根据号段ID获取互斥字典
```
GET /dictionary/management/v1/queryMutexCodeByRanId/{ranId}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**ranId**  <br>*必填*|号段id|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryMutexCodeByRanId/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querymutexdictionarybyextcodeusingget"></a>
#### 根据映射外部id查询互斥字典
```
GET /dictionary/management/v1/queryMutexDictionaryByExtCode/{extCode}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**extCode**  <br>*必填*|映射外部code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/queryMutexDictionaryByExtCode/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="querysubordinatedictionarybyextcodeusingget"></a>
#### 根据映射外部ID查询对应的下级映射字典
```
GET /dictionary/management/v1/querySubordinateDictionaryByExtCode/{extCode}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**extCode**  <br>*必填*|映射外部code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionary»»](#3667205b9659ead7454bb64b785be6a1)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/querySubordinateDictionaryByExtCode/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : [ 0 ],
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : [ 0 ],
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="selectalldictionarymapusingget"></a>
#### 查询所有映射列表
```
GET /dictionary/management/v1/selectAllDictionaryMap
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«DictionaryMapParam»»](#94eb8c0ff6c5c3b89c93b28d0951abdd)|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/selectAllDictionaryMap
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "extCode" : 0,
    "mapCode" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="e25214dff54e5a01626dc8977334b4e2"></a>
### 字典管理
Dictionary Controller


<a name="deletedictionaryusingdelete"></a>
#### 删除字典信息
```
DELETE /dictionary/management/v1/deleteDictionary/{code}
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Path**|**code**  <br>*必填*|需要删除的字典code|string||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«int»](#26ef25ee01b21e621d9886c47b8b6fed)|
|**204**|No Content|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/deleteDictionary/string
```


###### 请求 header
```json
"string"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```


<a name="distributiongroupcodeusingpost"></a>
#### 分配字典分组
```
POST /dictionary/management/v1/distributionGroupCode
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**distributionGroupCodeParam**  <br>*必填*|distributionGroupCodeParam|[DistributionGroupCodeParam](#distributiongroupcodeparam)||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«int»](#26ef25ee01b21e621d9886c47b8b6fed)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/distributionGroupCode
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
{
  "code" : "string",
  "groupCode" : "string"
}
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```


<a name="savedictionaryusingpost"></a>
#### 新增字典信息
```
POST /dictionary/management/v1/saveDictionary
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**systemDictionaryParam**  <br>*必填*|systemDictionaryParam|[SystemDictionaryParam](#systemdictionaryparam)||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«int»](#26ef25ee01b21e621d9886c47b8b6fed)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/saveDictionary
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
{
  "code" : 0,
  "createSrc" : "string",
  "createTime" : "string",
  "describe" : "string",
  "groupCode" : "string",
  "groupType" : 0,
  "mutexCode" : 0,
  "parentCode" : "string",
  "ranId" : 0,
  "status" : 0,
  "value" : "string"
}
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```


<a name="savedictionarylistusingpost"></a>
#### 批量增加字典信息
```
POST /dictionary/management/v1/saveDictionaryList
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**systemDictionaryParamList**  <br>*必填*|systemDictionaryParamList|< [SystemDictionaryParam](#systemdictionaryparam) > array||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionaryParam»»](#9f2a462aef023a610e06cb72bd599d44)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/saveDictionaryList
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
[ {
  "code" : 0,
  "createSrc" : "string",
  "createTime" : "string",
  "describe" : "string",
  "groupCode" : "string",
  "groupType" : 0,
  "mutexCode" : 0,
  "parentCode" : "string",
  "ranId" : 0,
  "status" : 0,
  "value" : "string"
} ]
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : "string",
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : "string",
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```


<a name="updatedictionaryusingput"></a>
#### 修改字典信息
```
PUT /dictionary/management/v1/updateDictionary
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**Body**|**systemDictionaryParam**  <br>*必填*|systemDictionaryParam|[SystemDictionaryParam](#systemdictionaryparam)||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«int»](#26ef25ee01b21e621d9886c47b8b6fed)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `application/json`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/management/v1/updateDictionary
```


###### 请求 header
```json
"string"
```


###### 请求 body
```json
{
  "code" : 0,
  "createSrc" : "string",
  "createTime" : "string",
  "describe" : "string",
  "groupCode" : "string",
  "groupType" : 0,
  "mutexCode" : 0,
  "parentCode" : "string",
  "ranId" : 0,
  "status" : 0,
  "value" : "string"
}
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : 0,
  "traceId" : "string"
}
```


<a name="7e3337ec371ad83dd26d92a0caec099c"></a>
### 导入excel
Excel Import Controller


<a name="exceldictionarymapsaveusingpost"></a>
#### excel导入字典映射信息
```
POST /dictionary/excel/v1/excelDictionaryMapSave
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**FormData**|**file**  <br>*必填*|file|file||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«DictionaryMap»»](#073be25547d743821db8a8c77fc8fe13)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `multipart/form-data`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/excel/v1/excelDictionaryMapSave
```


###### 请求 header
```json
"string"
```


###### 请求 formData
```json
"file"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "extCode" : 0,
    "mapCode" : 0
  } ],
  "traceId" : "string"
}
```


<a name="exceldictionarysaveusingpost"></a>
#### excel导入字典信息
```
POST /dictionary/excel/v1/excelDictionarySave
```


##### 参数

|类型|名称|说明|类型|默认值|
|---|---|---|---|---|
|**Header**|**Authorization**  <br>*可选*|令牌|string|`"9527"`|
|**FormData**|**file**  <br>*必填*|file|file||


##### 响应

|HTTP代码|说明|类型|
|---|---|---|
|**200**|OK|[返回对象«List«SystemDictionaryParam»»](#9f2a462aef023a610e06cb72bd599d44)|
|**201**|Created|无内容|
|**401**|Unauthorized|无内容|
|**403**|Forbidden|无内容|
|**404**|Not Found|无内容|


##### 消耗

* `multipart/form-data`


##### 生成

* `\*/*`


##### HTTP请求示例

###### 请求 path
```
/dictionary/excel/v1/excelDictionarySave
```


###### 请求 header
```json
"string"
```


###### 请求 formData
```json
"file"
```


##### HTTP响应示例

###### 响应 200
```json
{
  "code" : 0,
  "message" : "ok",
  "data" : [ {
    "code" : 0,
    "createSrc" : "string",
    "createTime" : "string",
    "describe" : "string",
    "groupCode" : "string",
    "groupType" : 0,
    "mutexCode" : 0,
    "parentCode" : "string",
    "ranId" : 0,
    "status" : 0,
    "value" : "string"
  } ],
  "traceId" : "string"
}
```




<a name="definitions"></a>
## 定义

<a name="dictionaryconditionparam"></a>
### DictionaryConditionParam

|名称|说明|类型|
|---|---|---|
|**code**  <br>*可选*|字典code  <br>**样例** : `0`|integer (int64)|
|**ranId**  <br>*可选*|所属号段  <br>**样例** : `0`|integer (int64)|
|**status**  <br>*可选*|状态  0-正常  1-禁用  2-删除  <br>**样例** : `0`|integer (int32)|
|**value**  <br>*可选*|字典值  <br>**样例** : `"string"`|string|


<a name="dictionarymap"></a>
### DictionaryMap

|名称|说明|类型|
|---|---|---|
|**code**  <br>*可选*|字典code  <br>**样例** : `0`|integer (int64)|
|**extCode**  <br>*可选*|外部code  <br>**样例** : `0`|integer (int64)|
|**mapCode**  <br>*可选*|映射组id  <br>**样例** : `0`|integer (int64)|


<a name="dictionarymapparam"></a>
### DictionaryMapParam

|名称|说明|类型|
|---|---|---|
|**code**  <br>*可选*|**样例** : `0`|integer (int64)|
|**extCode**  <br>*可选*|**样例** : `0`|integer (int64)|
|**mapCode**  <br>*可选*|**样例** : `0`|integer (int64)|
|**value**  <br>*可选*|**样例** : `"string"`|string|


<a name="dictionaryresult"></a>
### DictionaryResult

|名称|说明|类型|
|---|---|---|
|**code**  <br>*可选*|**样例** : `0`|integer (int64)|
|**ranId**  <br>*可选*|**样例** : `0`|integer (int64)|
|**value**  <br>*可选*|**样例** : `"string"`|string|


<a name="distributiongroupcodeparam"></a>
### DistributionGroupCodeParam

|名称|说明|类型|
|---|---|---|
|**code**  <br>*可选*|字典code  <br>**样例** : `"string"`|string|
|**groupCode**  <br>*可选*|字典分组code  <br>**样例** : `"string"`|string|


<a name="monitorresultinfo"></a>
### MonitorResultInfo

|名称|说明|类型|
|---|---|---|
|**status**  <br>*可选*|**样例** : `"string"`|string|
|**version**  <br>*可选*|**样例** : `"string"`|string|

<a name="numberrange"></a>

### NumberRange

|名称|说明|类型|
|---|---|---|
|**childNumberRange**  <br>*可选*|存放子号段  <br>**样例** : `[ "[numberrange](#numberrange)" ]`|< [NumberRange](#numberrange) > array|
|**code**  <br>*可选*|号段code  <br>**样例** : `0`|integer (int64)|
|**createTime**  <br>*可选*|创建时间  <br>**样例** : `"string"`|string|
|**expCode**  <br>*可选*|扩展code  <br>**样例** : `0`|integer (int64)|
|**length**  <br>*可选*|号段长度  <br>**样例** : `0`|integer (int64)|
|**name**  <br>*可选*|号段名称  <br>**样例** : `"string"`|string|
|**numEnd**  <br>*可选*|号段结束号  <br>**样例** : `0`|integer (int64)|
|**numStart**  <br>*可选*|号段起始号  <br>**样例** : `0`|integer (int64)|
|**parentCode**  <br>*可选*|号段上级code  <br>**样例** : `0`|integer (int64)|
|**rule**  <br>*可选*|号号段规则描述  <br>**样例** : `"string"`|string|
|**status**  <br>*可选*|号段状态 0-启用，1-禁用，-1-删除  <br>**样例** : `0`|integer (int32)|
|**type**  <br>*可选*|号段类型： 0-已占用号段，1-D类，2-C类，3-B类，4-扩充号段  <br>**样例** : `0`|integer (int32)|


<a name="querydictionaryparam"></a>
### QueryDictionaryParam

|名称|说明|类型|
|---|---|---|
|**groupCode**  <br>*可选*|分组code  <br>**样例** : `"string"`|string|
|**isAllocate**  <br>*可选*|是否分配    1-已分配       0-未分配  <br>**样例** : `0`|integer (int32)|
|**ranId**  <br>*可选*|所属段号id  <br>**样例** : `"string"`|string|


<a name="systemdictionary"></a>
### SystemDictionary

|名称|说明|类型|
|---|---|---|
|**code**  <br>*可选*|**样例** : `0`|integer (int64)|
|**createSrc**  <br>*可选*|**样例** : `"string"`|string|
|**createTime**  <br>*可选*|**样例** : `"string"`|string (date-time)|
|**describe**  <br>*可选*|**样例** : `"string"`|string|
|**groupCode**  <br>*可选*|**样例** : `[ 0 ]`|< integer (int64) > array|
|**groupType**  <br>*可选*|**样例** : `0`|integer (int32)|
|**mutexCode**  <br>*可选*|**样例** : `0`|integer (int64)|
|**parentCode**  <br>*可选*|**样例** : `[ 0 ]`|< integer (int64) > array|
|**ranId**  <br>*可选*|**样例** : `0`|integer (int64)|
|**status**  <br>*可选*|**样例** : `0`|integer (int32)|
|**value**  <br>*可选*|**样例** : `"string"`|string|


<a name="systemdictionaryparam"></a>
### SystemDictionaryParam

|名称|说明|类型|
|---|---|---|
|**code**  <br>*可选*|字典code  <br>**样例** : `0`|integer (int64)|
|**createSrc**  <br>*可选*|创建来源  <br>**样例** : `"string"`|string|
|**createTime**  <br>*可选*|创建时间  <br>**样例** : `"string"`|string (date-time)|
|**describe**  <br>*可选*|字典描述  <br>**样例** : `"string"`|string|
|**groupCode**  <br>*可选*|分组  <br>**样例** : `"string"`|string|
|**groupType**  <br>*可选*|分组类型  1-分组  2-映射组  0-字典  <br>**样例** : `0`|integer (int32)|
|**mutexCode**  <br>*可选*|互斥code  <br>**样例** : `0`|integer (int64)|
|**parentCode**  <br>*可选*|父类code  <br>**样例** : `"string"`|string|
|**ranId**  <br>*可选*|所属号段  <br>**样例** : `0`|integer (int64)|
|**status**  <br>*可选*|状态  0-正常 1-禁用  2 -删除  <br>**样例** : `0`|integer (int32)|
|**value**  <br>*可选*|字典值  <br>**样例** : `"string"`|string|


<a name="deacd4f89d7131fe4495441e70b5a5b2"></a>
### 返回对象
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `"object"`|object|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="94eb8c0ff6c5c3b89c93b28d0951abdd"></a>
### 返回对象«List«DictionaryMapParam»»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `[ "[dictionarymapparam](#dictionarymapparam)" ]`|< [DictionaryMapParam](#dictionarymapparam) > array|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="073be25547d743821db8a8c77fc8fe13"></a>
### 返回对象«List«DictionaryMap»»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `[ "[dictionarymap](#dictionarymap)" ]`|< [DictionaryMap](#dictionarymap) > array|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="845c1de5ce0902d97b6158098ee9f196"></a>
### 返回对象«List«DictionaryResult»»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `[ "[dictionaryresult](#dictionaryresult)" ]`|< [DictionaryResult](#dictionaryresult) > array|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="9f2a462aef023a610e06cb72bd599d44"></a>
### 返回对象«List«SystemDictionaryParam»»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `[ "[systemdictionaryparam](#systemdictionaryparam)" ]`|< [SystemDictionaryParam](#systemdictionaryparam) > array|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="3667205b9659ead7454bb64b785be6a1"></a>
### 返回对象«List«SystemDictionary»»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `[ "[systemdictionary](#systemdictionary)" ]`|< [SystemDictionary](#systemdictionary) > array|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="4cf9441e45f37a8ee0d580b90566c978"></a>
### 返回对象«MonitorResultInfo»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `"[monitorresultinfo](#monitorresultinfo)"`|[MonitorResultInfo](#monitorresultinfo)|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="031ae7aa4d9fd5e95e19fb04515730a7"></a>
### 返回对象«NumberRange»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `"[numberrange](#numberrange)"`|[NumberRange](#numberrange)|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="38a2423e7b52a1a2a10a8c6ed54f4007"></a>
### 返回对象«SystemDictionary»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `"[systemdictionary](#systemdictionary)"`|[SystemDictionary](#systemdictionary)|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|


<a name="26ef25ee01b21e621d9886c47b8b6fed"></a>
### 返回对象«int»
Api接口统一返回对象


|名称|说明|类型|
|---|---|---|
|**code**  <br>*必填*|返回状态码  <br>**样例** : `0`|integer (int32)|
|**data**  <br>*可选*|返回对象  <br>**样例** : `0`|integer (int32)|
|**message**  <br>*可选*|返回信息  <br>**样例** : `"ok"`|string|
|**traceId**  <br>*可选*|请求唯一标识  <br>**样例** : `"string"`|string|





