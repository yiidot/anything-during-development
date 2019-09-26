1. 创建模板文件
```yaml
# Tools-Packages-Package Development-New Syntax Definition
%YAML 1.2
---
# See http://www.sublimetext.com/docs/3/syntax.html
file_extensions:
  - log
scope: source.log

contexts:

  main:
    # The main context is the initial starting point of our syntax.
    # Include other contexts from here (or specify them directly).
    - include: verbose
    - include: debug
    - include: info
    - include: warn
    - include: error
    - include: assert
    - include: exception


  verbose:
    - match: '^(.*)V/(.*)\n|^(.*)(?i)verbose[/\]](.*)\n'
      scope: comment.log
  debug:
    - match: '^(.*)D/(.*)\n|^(.*)(?i)debug[/\]](.*)\n'
      scope: string.log
  info:
    - match: '^(.*)I/(.*)\n|^(.*)(?i)info[/\]](.*)\n'
  warn:
    - match: '^(.*)W/(.*)\n|^(.*)(?i)warn[/\]](.*)\n'
      scope: constant.numeric.integer.log
  error:
    - match: '^(.*)E/(.*)\n|^(.*)(?i)error[/\]](.*)\n'
      scope: storage.log
  assert:
    - match: '^(.*)A/(.*)\n|^(.*)(?i)assert[/\]](.*)\n'
      scope: storage.log
  exception:
    - match: '^(.*)(?i)Exception|fatal|error|anr(.*)\n'
      scope: storage.log
```
2. 保存
默认保存在/Users/yourname/Library/Application\ Support/Sublime Text 3/Packages/User
命名为log.sublime-syntax
