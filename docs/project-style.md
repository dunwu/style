# project-style

> 软件项目开发规范。

<!-- TOC depthFrom:2 depthTo:3 -->

- [项目结构](#项目结构)
    - [目录](#目录)
    - [文件](#文件)
- [目录名](#目录名)
- [文件名](#文件名)

<!-- /TOC -->

## 项目结构

以下为项目根目录下的文件和目录的组织结构：

### 目录

**codes**：代码目录。

**configurations**：配置目录。一般存放项目相关的配置文件。如 maven 的 settings.xml，nginx 的 nginx.conf 等。

**demos**：示例目录。

**docs**：文档目录。

**libs**：第三方库文件。

**scripts**：脚本目录。一般存放用于启动、构建项目的可执行脚本文件。

**packages**：打包文件目录。Java 项目中可能是 jar、war 等；前端项目中可能是 zip、rar 等；电子书项目中可能是 pdf 等。

### 文件

**.gitignore**：git 忽略规则。

**.gitattributes**：git 属性规则。

**.editorconfig**：编辑器书写规则。

**README.md**：项目说明文件。

**LICENSE**：开源协议。如果项目是开源文件，需要添加。

## 目录名

目录名必须使用半角字符，不得使用全角字符。这也意味着，中文不能用于文件名。

目录名建议只使用小写字母，不使用大写字母。

```
不佳： Test
正确： test
```

目录名可以使用数字，但不应该是首字符。

```
不佳： 1-demo
正确： demo1
```

目录名包含多个单词时，单词之间建议使用半角的连词线（`-`）分隔。

```
不佳： common_demo
正确： common-demo
```

## 文件名

文档的文件名不得含有空格。

文件名必须使用半角字符，不得使用全角字符。这也意味着，中文不能用于文件名。

```
错误： 名词解释.md
正确： glossary.md
```

文件名建议只使用小写字母，不使用大写字母。

```
错误：TroubleShooting.md
正确：troubleshooting.md
```

为了醒目，某些说明文件的文件名，可以使用大写字母，比如`README`、`LICENSE`。

一些约定俗成的习惯可以保持传统写法，如：Java 的文件名一般使用驼峰命名法，且首字母大写；配置文件 `applicationContext.xml` ；React 中的 JSX 组件文件名一般使用驼峰命名法，且首字母大写等。

文件名包含多个单词时，单词之间建议使用半角的连词线（`-`）分隔。

```
不佳：advanced_usage.md
正确：advanced-usage.md
```
