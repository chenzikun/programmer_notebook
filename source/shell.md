# Shell

## 内置方法

1. 设置只读变量： `declare -r para=""`
2. 设置`int`变量： `declare -i para=n`
3. 局部变量：`local`
4. 命令执行状态：$?
5. test表达式: `[]`、`[[]]`、`(())`
6. read未指定变量时：`$REPLY`变量代表输入值
7. `case` and `esac`
8. 大于9的位置参数用`${n}`
9. shell中`*`代表当前目录下的所有文件
10. 遍历变量:`shift`

## 变量
1. ${foo:-"deaflut-value"} *w*临时**
2. ${foo:="deaflut-value"} **永久**
3. ${foo:？"deaflut-value"} **抛出错误**
4. ${foo:+"deaflut-value"} **有变量时echo**
5. ${!bash*} **以bash开头的变量**