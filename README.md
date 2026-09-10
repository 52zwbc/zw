# zwpy —— 用中文就能学会的 Python

> **zwpy**（中文 Python），简称 **zw**，是一门专为中文母语学习者设计的**中文编程语言**。
> 它不是另一个编程语言，而是 **Python 的"中文外壳"**：同一套解释器、同一套标准库、同一套第三方生态，只是把关键字、内置函数、内置类型的方法换成了中文名。

---

## 为什么选择 zwpy？

如果你刚开始学编程，第一个拦路虎往往不是"逻辑"，而是**背一大堆英文单词**：`if` / `for` / `def` / `print` / `len`……明明想的是"如果""循环""函数""打印"，写出来的却是另一套符号。

zwpy 帮你去掉这层翻译负担：

- 🌟 **母语即代码**：用「如果」「遍历」「函数」「打印」写程序，和你脑子里想的一模一样。
- 🌉 **零成本过渡到 Python**：中文名和英文**一一对应**，`如果` 就是 `if`、`打印` 就是 `print`。学完 zwpy，你也就学会了 Python——把关键字换回英文即可，逻辑、库、生态完全通用。
- 📚 **标准库与第三方库照常使用**：`zw` 文件里调用 `math`、`random`、`requests` 等，和英文 Python 毫无区别；你只需要把"自己写的那部分"用中文。
- 🔤 **中文不再乱码**：内置的「打开文件」默认使用 `utf-8` 编码，告别 Windows 上 `open` 默认 gbk 的中文乱码痛点。
- ❌ **友好的中文报错**：异常用「异常_除零错误」「异常_文件未找到」等中文名，报错信息一眼看懂。

> **一句话总结**：zwpy 让你用母语跨进编程的大门，而门后面，就是完整的 Python 世界。

---

## 两种写法，随你选择

zwpy 的核心是"中英映射"，因此你可以按自己的阶段灵活选择写法：

### 写法一：纯中文 `.zw` 文件（推荐初学者）

全程中文关键字 + 中文内置函数，最适合零基础：

```zw
# 例：问候并统计
名字 = 输入("你叫什么名字？")
打印("你好，" + 名字 + "！")

# 列表与循环
数字们 = 列表([1, 2, 3, 4, 5])
总和 = 0
遍历 数字 在 数字们:
    总和 = 总和 + 数字
打印("总和是：" + 字符串(总和))
```

### 写法二：英文关键字 + 中文内置（平滑过渡）

当你开始熟悉英文关键字时，可以保持 `for`/`if` 等，只把 `print`、`open`、类型名换成中文。
这份代码是**合法的 Python**（因为中文名已在运行时注册），又能享受中文内置的便利：

```python
# 这份 .py 文件可以直接用普通 python 运行
names = ["小明", "小红"]
for n in names:
    print("你好，" + n)          # print 的中文别名

with 打开文件("数据.txt", 模式="写入") as f:   # 默认 utf-8，免编码烦恼
    f.写入("中文内容，不会乱码\n")
```

### 写法三：随时回到纯英文 Python

zwpy 不锁定你。把中文关键字换回英文，就是标准 Python 代码，可以在任何环境运行：

```python
# 上面的 .zw 等价的标准 Python
name = input("你叫什么名字？")
print("你好，" + name + "！")
```

---

## 运行 zw 代码

- **`.zw` 文件**：通过 zw 运行时（自带 Python + 中文映射）直接执行，例如 `zw 你的程序.zw`。
- **`.py` 文件**：使用注册了中文内置名的 zw Python 解释器即可直接 `python 你的程序.py`，无需任何额外 import。

> 中文名（如 `打印`、`打开文件`、`列表`、`字典`）在 zw 的 Python 启动时自动注册为内置名，所以写 `.py` 时**不用 import 就能直接用**。

---

## 完整中英映射表

> 本节供**开发者与 AI 大模型**参考。生成 zw 代码或中文友好 py 代码时，请严格使用下表的中文名。
> 规则：中文标识符后接参数用中文圆括号与中文标点；方法调用用「对象.中文方法()」。

### 1. 关键字映射

| 中文 | 英文 | 类别 |
|---|---|---|
| 如果 | if | 控制流 |
| 否则如果 | elif | 控制流 |
| 否则 | else | 控制流 |
| 遍历 | for | 控制流 |
| 循环条件 | while | 控制流 |
| 跳出 | break | 控制流 |
| 继续 | continue | 控制流 |
| 返回 | return | 控制流 |
| 生成 | yield | 控制流 |
| 函数 | def | 定义 |
| 类 | class | 定义 |
| 匿名 | lambda | 定义 |
| 匹配 | match | 定义 |
| 情形 | case | 定义 |
| 尝试 | try | 异常 |
| 捕获 | except | 异常 |
| 最终 | finally | 异常 |
| 抛出 | raise | 异常 |
| 断言 | assert | 异常 |
| 使用 | with | 上下文 |
| 命名为 | as | 上下文 |
| 导入 | import | 模块 |
| 从 | from | 模块 |
| 删除 | del | 其他 |
| 占位 | pass | 其他 |
| 全局 | global | 作用域 |
| 非局部 | nonlocal | 作用域 |
| 属于 | in | 逻辑运算 |
| 是 | is | 逻辑运算 |
| 并且 | and | 逻辑运算 |
| 或者 | or | 逻辑运算 |
| 不 | not | 逻辑运算 |
| 异步 | async | 异步 |
| 等候 | await | 异步 |
| 真 | True | 常量 |
| 假 | False | 常量 |
| 空 | None | 常量 |
| 初始化 | `__init__` | 类构造方法（写在类里，自动成为构造器）|
| `__主程序保护__` | `if __name__ == "__main__":` | 程序入口惯用法 |

> 约定：类的方法第一个参数用 `自身`（对应英文 `self`），无需映射，是普通参数名。

### 2. 内置函数映射

| 中文 | 英文 | 说明 |
|---|---|---|
| 绝对值 | abs | |
| 商和余 | divmod | |
| 最大值 | max | |
| 最小值 | min | |
| 幂 | pow | |
| 求和 | sum | |
| 舍入 | round | |
| 二进制 | bin | |
| 八进制 | oct | |
| 十六进制 | hex | |
| 编码转字符 | chr | |
| 字符转编码 | ord | |
| 字串表示 | repr | |
| 字节串 | bytes | |
| 可变字节串 | bytearray | |
| 全真 | all | |
| 任意真 | any | |
| 可调用 | callable | |
| 包含属性 | hasattr | |
| 是子类 | issubclass | |
| 是实例 | isinstance | |
| 长度 | len | |
| 枚举 | enumerate | |
| 过滤 | filter | |
| 迭代器 | iter | |
| 映射 | map | |
| 下一个 | next | |
| 反转 | reversed | |
| 排序 | sorted | |
| 打包 | zip | |
| 范围 | range | |
| 切片 | slice | |
| 格式化 | format | |
| 查看成员 | dir | |
| 查看属性 | vars | |
| 获取属性 | getattr | |
| 设置属性 | setattr | |
| 删除属性 | delattr | |
| 哈希值 | hash | |
| 帮助 | help | |
| 类型 | type | |
| 父类 | super | |
| 属性 | property | |
| 静态方法 | staticmethod | |
| 类方法 | classmethod | |
| 唯一标识 | id | |
| 输入 | input | |
| 打印 | print | |
| 打开 | open | |
| 退出 | quit | |
| 编译 | compile | |
| 评估 | eval | |
| 运行代码 | exec | |
| 局部变量 | locals | |
| 全局变量 | globals | |
| 整数 | int | 类型构造器 |
| 浮点数 | float | 类型构造器 |
| 复数 | complex | 类型构造器 |
| 字符串 | str | 类型构造器 |
| 列表 | list | 类型构造器 |
| 字典 | dict | 类型构造器 |
| 元组 | tuple | 类型构造器 |
| 布尔 | bool | 类型构造器 |
| 不可变集合 | frozenset | 类型构造器 |
| 集合 | set | 类型构造器 |
| 基础对象 | object | |
| 省略号 | Ellipsis | |
| 未实现值 | NotImplemented | |
| 内存视图 | memoryview | |
| 字符转ascii | ascii | |
| 断点 | breakpoint | |
| 异步迭代器 | aiter | |
| 异步下一个 | anext | |
| 界面模块 | zwGUI | 中文 GUI 库别名 |
| 界面 | ui | GUI 别名 |

#### 中文便捷函数（运行时额外提供）

| 中文 | 等价 / 说明 |
|---|---|
| **打开文件**(路径, 模式="读取", 编码="utf-8", **选项) | 在 `open` 之上封装：默认 `utf-8` 编码；模式用中文「读取」(r)/「写入」(w)/「追加」(a)；相对路径自动按"脚本所在目录"解析；二进制模式（`rb`/`wb`）自动跳过 encoding。文件对象支持下文"文件对象"的中文方法。 |

### 3. 异常类映射

| 中文 | 英文 | 中文 | 英文 |
|---|---|---|---|
| 异常 | Exception | 异常_文件已存在 | FileExistsError |
| 异常_基础异常 | BaseException | 异常_是目录错误 | IsADirectoryError |
| 异常_系统退出 | SystemExit | 异常_非目录错误 | NotADirectoryError |
| 异常_算术错误 | ArithmeticError | 异常_超时错误 | TimeoutError |
| 异常_断言错误 | AssertionError | 异常_连接错误 | ConnectionError |
| 异常_属性错误 | AttributeError | 异常_连接中止错误 | ConnectionAbortedError |
| 异常_文件末尾错误 | EOFError | 异常_连接被拒错误 | ConnectionRefusedError |
| 异常_导入错误 | ImportError | 异常_连接重置错误 | ConnectionResetError |
| 异常_查找错误 | LookupError | 异常_中断错误 | InterruptedError |
| 异常_内存错误 | MemoryError | 异常_用户警告 | UserWarning |
| 异常_名称错误 | NameError | 异常_弃用警告 | DeprecationWarning |
| 异常_系统错误 | OSError | 异常_未来警告 | FutureWarning |
| 异常_运行时错误 | RuntimeError | 异常_语法警告 | SyntaxWarning |
| 异常_语法错误 | SyntaxError | 异常_运行时警告 | RuntimeWarning |
| 异常_类型错误 | TypeError | 异常_待弃用警告 | PendingDeprecationWarning |
| 异常_值错误 | ValueError | 异常_字节警告 | BytesWarning |
| 异常_警告 | Warning | 异常_资源警告 | ResourceWarning |
| 异常_除零错误 | ZeroDivisionError | 异常_编码警告 | UnicodeWarning |
| 异常_溢出错误 | OverflowError | 异常_编码错误 | UnicodeError |
| 异常_索引错误 | IndexError | 异常_编码解码错误 | UnicodeDecodeError |
| 异常_键错误 | KeyError | 异常_编码编码错误 | UnicodeEncodeError |
| 异常_局部未绑定 | UnboundLocalError | 异常_文件未找到 | FileNotFoundError |
| 异常_模块未找到 | ModuleNotFoundError | 异常_权限错误 | PermissionError |
| 异常_未实现 | NotImplementedError | | |
| 异常_递归错误 | RecursionError | | |
| 异常_缩进错误 | IndentationError | | |
| 异常_制表符错误 | TabError | | |

### 4. 内置类型方法映射

> 格式：`对象.中文方法()`，括号内参数与英文方法一致。

#### 字符串 `字符串` / `字节串` / `可变字节串`

| 中文方法 | 英文方法 | 中文方法 | 英文方法 |
|---|---|---|---|
| 首字大写 | capitalize | 删前缀 | removeprefix |
| 全转小写 | casefold | 删后缀 | removesuffix |
| 加宽 | center | 替换 | replace |
| 统计 | count | 右查找 | rfind |
| 编码 | encode | 左加宽 | ljust |
| 以此结尾 | endswith | 右加宽 | rjust |
| 缩进 | expandtabs | 右三分 | rpartition |
| 查找 | find | 右分割 | rsplit |
| 格式化 | format | 删右 | rstrip |
| 格式化映射 | format_map | 分割 | split |
| 仅ascii | isascii | 分割为行 | splitlines |
| 仅字母或数 | isalnum | 以此开头 | startswith |
| 仅字母 | isalpha | 删两侧 | strip |
| 仅正整数 | isdigit | 大小写切换 | swapcase |
| 是标识符 | isidentifier | 标题化 | title |
| 仅小写 | islower | 转换 | translate |
| 仅数字 | isnumeric | 大写 | upper |
| 仅可打印 | isprintable | 用零填充 | zfill |
| 仅空白 | isspace | 索引 | index |
| 仅大写 | isupper | 仅十进制数 | isdecimal |
| 连接 | join | 含标题单词 | istitle |
| 小写 | lower | 右索引 | rindex |
| 映射转换表 | maketrans | 三分 | partition |

> `字节串`/`可变字节串` 另含：解码→decode、十六进制解码→fromhex、转十六进制→hex。
> `可变字节串` 另含可变方法：追加→append、清空→clear、复制→copy、扩展→extend、插入→insert、弹出→pop、删除→remove、反转→reverse。

#### 列表 `列表`

追加→append、清空→clear、统计→count、复制→copy、扩展→extend、索引→index、插入→insert、弹出→pop、删除→remove、反转→reverse、排序→sort

#### 字典 `字典`

清空→clear、复制→copy、获取键→fromkeys、取值→get（别名：获取→get）、键值对→items、所有键→keys、弹出→pop、删除末尾→popitem、取或添加→setdefault、更新→update、所有值→values

#### 集合 `集合` / `不可变集合`

添加→add、清空→clear、复制→copy、差集→difference、更新差集→difference_update、静默删除→discard、交集→intersection、更新交集→intersection_update、不相交→isdisjoint、被包含→issubset、包含→issuperset、弹出→pop、删除→remove、对称差集→symmetric_difference、更新对称差集→symmetric_difference_update、并集→union、更新→update

> `不可变集合` 支持上述除"添加/更新类可变方法"外的全部查询与集合运算。

#### 元组 `元组`

统计→count、索引→index

#### 整数 `整数` / 浮点数 `浮点数` / 复数 `复数`

| 中文方法 | 英文方法 | 适用 |
|---|---|---|
| 位长度 | bit_length | int |
| 位计数 | bit_count | int |
| 转字节 | to_bytes | int |
| 从字节 | from_bytes | int |
| 整数比 | as_integer_ratio | int/float |
| 是整数 | is_integer | int/float |
| 转十六进制 | hex | int/float(bytes) |
| 从十六进制 | fromhex | int/float(bytes) |
| 共轭 | conjugate | int/float/complex |

#### 文件对象（由「打开文件」/「打开」返回）

**文本文件**（`读取`/`写入`/`关闭` 等）：

读取→read、写入→write、关闭→close、读取一行→readline、读取所有行→readlines、刷新→flush、写多行→writelines

**二进制文件**（读 `rb` / 写 `wb` / 读写 `r+b`）：

| 中文方法 | 英文方法 | 适用 |
|---|---|---|
| 读取 | read | 读 / 读写 |
| 写入 | write | 写 / 读写 |
| 关闭 | close | 全部 |
| 刷新 | flush | 全部 |
| 定位 | seek | 全部 |
| 当前位置 | tell | 全部 |
| 可读 | readable | 全部 |
| 可写 | writable | 全部 |
| 可定位 | seekable | 全部 |

---

## 给 AI 大模型的生成约定

当你被要求生成 **zw 语言** 代码时，请遵循：

1. **`.zw` 文件**：全程使用上表的中文关键字与中文内置名（如 `如果`/`遍历`/`函数`/`打印`/`列表`/`字典`/`捕获 异常_除零错误`），方法调用用 `对象.中文方法()`。
2. **中文友好的 `.py` 文件**：可使用中文内置名（`打印`、`打开文件`、`列表`、`字典`、`字符串` 等），它们已在 zw 的 Python 运行时注册，无需 import，是合法 Python。关键字仍可用英文（如 `for`/`if`），也可全中文，二选一保持一致即可。
3. **中英文混用是允许的**，但同一文件内建议风格统一。
4. **示例（同一逻辑的中 / 英对照）**：

```zw
函数 求平方根(x):
    如果 x < 0:
        抛出 异常_值错误("不能为负")
    返回 x ** 0.5

数字 = 求平方根(9)
打印(数字)
```

```python
# 等价的、可直接运行的 zw 风格 py（中文内置 + 英文关键字）
def 求平方根(x):
    if x < 0:
        raise 异常_值错误("不能为负")
    return x ** 0.5

数字 = 求平方根(9)
print(数字)
```

> 掌握 zwpy，你就掌握了 Python。中文只是入口，世界是通用的。
