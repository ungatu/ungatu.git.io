# A Easy way to undersantand Git!

## 创建一个新仓库

要么git init，要么git clone远程服务器，
连接方式多种多样，http，https，ssh

## Record update to your Git
当新建了个文件，并且开始跟踪（git add），提醒
warning: LF will be replaced by CRLF in README.

However, when use winhex to see the file, the LF stll be LF,not CRLF!
但是假如这时候删除原文件

git add命令在很多时候都能用的到
但是更好的理解应该是“**精确地将内容添加到下一次提交中**”
而不是“将一个文件添加到项目中”。

CONTRIBUTING.md 文件同时出现在暂存区和非暂存区。 这怎么可能呢？ 好吧，实际上 Git 只不过暂存了你运行 git add 命令时的版本

git status -s, 
## Ignoring Files
文件 .gitignore 的格式规范如下：

1. 所有空行或者以 # 开头的行都会被 Git 忽略。

1. 可以使用标准的 glob 模式匹配，它会递归地应用在整个工作区中。

1. 匹配模式可以以（/）开头防止递归。

1. 匹配模式可以以（/）结尾指定目录。

要忽略指定模式以外的文件或目录，可以在模式前加上叹号（!）取反。

所谓的 glob 模式是指 shell 所使用的简化了的正则表达式。 星号（*）匹配零个或多个任意字符；[abc] 匹配任何一个列在方括号中的字符 （这个例子要么匹配一个 a，要么匹配一个 b，要么匹配一个 c）； 问号（?）只匹配一个任意字符；如果在方括号中使用短划线分隔两个字符， 表示所有在这两个字符范围内的都可以匹配（比如 [0-9] 表示匹配所有 0 到 9 的数字）。 使用两个星号（**）表示匹配任意中间目录，比如 a/**/z 可以匹配 a/z 、 a/b/z 或 a/b/c/z 等。
```
# ignore all .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in any directory named build
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf

```