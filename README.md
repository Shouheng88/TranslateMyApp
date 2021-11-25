# Android 脚本工具合集

汇集了开发过程中会用到的多种脚本工具。

## 1、多语言管理工具

### 1.1 多语言合并脚本工具

用来将一个多语言资源文件合并到另一个多语言资源文件。比如，将别人翻译或者修改的多语言合并到主干。该脚本通过对 key 对比实现合并，不改变之前多语言资源的顺序。

进入 language 目录，执行命令，

```
python merge.py -f 被合并的多语言资源文件位置 -t 合并到的多语言资源文件位置
```

### 1.2 根据 Android 多语言资源生成 iOS 多语言文件

根据 Android 的多语言资源文件和目录，生成 iOS 对应的多语言资源文件或者目录。

```
python generate.py -f 用来生成的资源文件 -o 输出到的位置
```

### 1.3 将多语言文件翻译成其他语言

翻译多语言文件成其他语言，支持指定被翻译多语言文件和输出到的位置，如果已经存在指定的词条，则无需翻译，只对没有翻译结果的进行翻译。

```
python translate.py -f 被翻译的资源文件 -o 输出到的位置
```

也可以直接指定要翻译的多语言的目录，此时根据目录名自动识别语言类型，然后根据默认多语言，补充和翻译不存在的词条，

```
python translate.py -f 被翻译的资源的目录
```

### 1.4 根据 Android 多语言资源生成 Excel

根据 Android 多语言资源文件或者目录生成 Excel，如果传入的参数是文件只生成其自己对应的 Excel；如果传入的是目录，则每个语种对应的文件生成一个 sheet：

```
python genexcel.py -f 用来生成的文件或者目录
```

## 2、日志采集和分析工具

### 2.1 日志采集工具

自动采集 Android 某个应用或者进程的日志并输出到文件中，便于对日志文件进行分析。使用：进入 logcat 目录，执行命令，

```
python collect.py -p 你的包名 -l 输出日志文件位置 -f yes
```

### 2.2 日志分析工具

对上述采集到的日志文件进行分析，从大到小输出打印最多的日志等。使用：进入 logcat 目录，执行命令，

```
python analyse.py -f 日志文件地址 -p 包名
```

## 3、上帝之眼

