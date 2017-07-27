# yaml

YAML 是专门用来写配置文件的语言，非常简洁和强大，远比 JSON 格式方便。

1. 可用于前端加载数据，依赖于`js-yaml`
2. 用于自动化测试，撰写测试用例
3. 用于配置文件，安装包`PyYaml`

## yaml语法

**结构**

1. 对象: `animal: pets`
2. 列表

	```yaml
	- Cat
	- Dog
	- Goldfish
	```	
3. 复合结构

**数据类型**

```yaml
# 这个例子输出一个字典，其中value包括所有基本类型
str: "Hello World!"
int: 110
float: 3.141
boolean: true  # or false
None: null  # 也可以用 ~ 号来表示 null
time: 2016-09-22t11:43:30.20+08:00  # ISO8601，写法百度
date: 2016-09-22  # 同样ISO8601
```
* 强制类型转换

	yaml是可以进行强制转换的，用 !! 实现
	
	```yaml
	str: !!str 3.14
	int: !!int "123"
	```
	
**字符串**

* 字符串默认不使用引号表示。
如果字符串之中包含空格或特殊字符，需要放在引号之中。

* 多行字符串可以使用`|`保留换行符，也可以使用`>`折叠换行,`|+`表示保留文字块末尾的换行，`|-`表示删除字符串末尾的换行。

**引用**

* 锚点：`&`

	* 字典锚点

	 	```yaml
	 defaults: &de
	 adapter:  postgres
	 host:     localhost
	 ```
	 	 
	* 列表锚点

	 	```yaml
	 - &showell Steve 
	 - Clark 
	 - Brian 
	 - Oren 
	 - *showell 
	 ```

* 别名：`*`
* 合并到当前数据：`<<`

**分段**

在同一个yaml文件中，可以用 --- 来分段，这样可以将多个文档写在一个文件中

```yaml
---
name: James
age: 20
---
name: Lily
age: 19	
```

## yaml与js

```js
const fs = require("fs");
const yaml = require("js-yaml");

/*装载yaml数据，输出json*/
var data = yaml.load(fs.readFileSync('./data/user.yaml', 'utf-8'));
```

## yaml与Python

```python
import yaml
y = yaml.load(file('test.yaml', 'r'))
```
