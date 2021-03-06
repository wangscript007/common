## Versioning

This project follows the [semantic versioning](http://semver.org/) scheme. The API change and backwards compatibility rules are those indicated by SemVer.

## ChangeLog

### v1.3.0

feat:

1.  AC 多模式匹配算法.
2.  KMP 模式匹配算法.


## 简介

*   公共库.存放着一些库之类的东西

## 组织

*   内部采用模块化设计,每一个模块具有以下属性:

    -   名字;指定了模块的名字.
    -   路径,文件列表;路径为模块路径相对于 common 项目的相对路径;若模块的文件直接放在于 common
        根目录,则文件列表中记录了模块所包括的文件.
    -   依赖;存放着模块依赖的模块列表.

*   如何使用头文件;`#include "PATH"`;`PATH` 是模块文件相对于 common 项目的相对路径.这样有很
    多好处,慢慢体会 T_t.

### 关于参数检查

*   在模块最外层的接口总是执行参数检查;不过可以在接口后追加'_on_trusted'或'OnTrusted'来调用
    不进行检查的版本.

*   在模块内层的接口不执行参数检查;因为这里由外层接口来保障.

## 如何使用

*   确定所使用模块之后,根据模块的路径属性;将模块包括的文件拷贝到自己项目中,再根据模块的依赖属性将递
    归执行上述操作.
