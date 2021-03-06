# EXCEL时间处理函数

> 时间在 Excel 中以数字的形式存在，具体意义是与 1990-01-01 00:00:00 相比的第几天，比如 1990-01-01 00:00:00 就存为1，1990-01-02 00:00:00 就存为2。为方便操作，插件提供了对应辅助方法：dateCodeFormat('存储的数字'， '格式') 、dateFormat('Date对象', '格式')、dateCodeToDate('存储的数字') 方便操作。

#### dateCodeToDate参数配置

> 辅助方法：用于将EXCEL中的时间数字转换为 Date 对象

##### 传入参数

| 参数名称 | 描述                  | 默认值 |
| -------- | --------------------- | ------ |
| code     | EXCEL中存储的时间数字 |        |

##### 返回参数

转换过后的Date对象

##### 使用样例

```javascript
var date = LAY_EXCEL.dateCodeToDate(43737.54167824074)
console.log(date); // Sun Sep 29 2019 13:00:01 GMT+0800 (中国标准时间)
```

#### dateCodeFormat参数配置

> 辅助方法：用于将EXCEL中的时间数字转换为对应格式的时间字符串

##### 传入参数

| 参数名称 | 描述                  | 默认值              |
| -------- | --------------------- | ------------------- |
| code     | EXCEL中存储的时间数字 |                     |
| format   | 日期格式              | YYYY-MM-DD HH:ii:ss |

##### 返回参数

转换后的字符串

##### 支持的替换参数

可以将 format 中的字符串转换为特定含义的数字

| 替换参数 | 含义                  |
| -------- | --------------------- |
| YY       | 二位数的年            |
| YYYY     | 四位数的年            |
| MM       | 二位数的月（补全0）   |
| M        | 自然数的月（不补全0） |
| DD       | 二位数的日（补全0）   |
| D        | 自然数的日            |
| HH       | 二位数的时（补全0）   |
| H        | 自然数的时            |
| ii       | 二位数的分            |
| i        | 自然数的分            |
| ss       | 二位数的秒            |
| s        | 自然数的秒            |

##### 使用样例

```javascript
var date = LAY_EXCEL.dateCodeFormat(43737.54167824074, 'YYYY-MM-DD HH:ii:ss')
console.log(date) // "2019-08-00 13:00:01"
```

#### dateFormat参数配置

> 辅助方法：用于将Date对象转换为对应格式的时间字符串

##### 传入参数

| 参数名称 | 描述     | 默认值              |
| -------- | -------- | ------------------- |
| date     | Date对象 |                     |
| format   | 日期格式 | YYYY-MM-DD HH:ii:ss |

##### 返回参数

转换后的字符串

##### 支持的替换参数

与上文相同

##### 使用样例

```javascript
var date = LAY_EXCEL.dateCodeFormat(new Date(), 'YYYY-MM-DD HH:ii:ss')
console.log(date) // "2019-09-04 22:39:25"
```

## 