# pandoc使用说明

```bash
pandoc 可以完成多种格式之前的相互转换，可谓是文件格式转换的瑞士军刀
```

## 使用

### 语法

```bash
pandoc [option] inputfile ...
```

说明:  
如果没有指定输入文件，则从标准输入读取  
若指定多个文件，那么以空格分割。  
默认输出时标准输出，可使用-o指定输出文件

默认情况下，pandoc只产生片段，不是一个包含头尾的完整文件，如果需要产生一个独立文件，使用-s生成  
有时候输入文件可能是个URI，此时pandoc可以通过http获取到内容  
如果输入多个文件，pandoc会合并之后输出一个文件  

* 常用选项  

|选项|含义|
|----|:----|
|-f FORMAT, -r FORMAT,--from=FORMAT, --read=FORMAT|指定输入文件的格式，若不指定，pandoc可以从明显的文件后缀名中推测，若无明显提示，默认的输入文件格式是markdown，默认的输出文件格式是html|
|-t FORMAT, -w FORMAT,--to=FORMAT, --write=FORMAT|指定输出文件的格式|
|-o FILE, --output=FILE|写输出到FILE文件而不是到标准输出|
|--list-input-formats|列出支持的输入文件格式|
|--list-output-formats|--list-output-formats|
|--list-extensions|列出支持的markdown扩展，+代表默认支持，-代表默认不支持|
|-s, --standalone|产生输出文件时附带适当的头注和脚注（比如html）|  

## [Example](http://www.pandoc.org/demos.html)