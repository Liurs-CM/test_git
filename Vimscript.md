#Learn Vimscript the Hard Way
##Table of Contents
1. Preface
2. Acknowledgements
3. Prerequisites
4. Echoing Messages
5. Setting Options
6. Basic Mapping
7. Modal Mapping
8. Strict Mapping
9. Leaders
10. Editing Your Vimrc
11. Abbreviations
12. More Mappings
13. Training Your Fingers
14. Buffer-Local Options and Mappings
15. Autocommands
16. Buffer-Local Abbreviations
17. Autocommand Groups
18. Operator-Pending Mappings
19. More Operator-Pending Mappings
20. Status Lines
21. Responsible Coding
22. Variables
23. Variable Scoping
24. Conditionals
25. Comparisons
26. Functions
27. Function Arguments
28. Numbers
29. Strings
30. String Functions
31. Execute
32. Normal
33. Execute Normal!
34. Basic Regular Expressions
35. Case Study: Grep Operator, Part One
36. Case Study: Grep Operator, Part Two
37. Case Study: Grep Operator, Part Three
38. Lists
39. Looping
40. Dictionaries
41. Toggling
42. Functional Programming
43. Paths
44. Creating a Full Plugin
45. Plugin Layout in the Dark Ages
46. A New Hope: Plugin Layout with Pathogen
47. Detecting Filetypes
48. Basic Syntax Highlighting
49. Advanced Syntax Highlighting
50. Even More Advanced Syntax Highlighting
51. Basic Folding
52. Advanced Folding
53. Section Movement Theory
54. Potion Section Movement
55. External Commands
56. Autoloading
57. Documentation
58. Distribution
59. What Now?

##6. Basic Mapping
- 基本映射
:map - x
- 特殊字符映射`<keyname>`
:map <space> viw
- 映射时不能用"注释
##7. Model Mapping
- 应用于正常`nmap`、可视`vmap`或插入`imap`模式下的映射
:nmap \ dd
- 选中字体大写
:vmap \ U
- 尝试在插入模式删除一行
    :imap <c-d> dd
    :imap <c-d> <esc>dd
    :imap <c-d> <esc>ddi
- 删除相应模式映射
    :unmap - x
    :nunmap - x
    :vunmap - x
    :iunmap - x
##8. Strict Mapping尽量默认使用
- 出现递归的例子
    :nmap dd O<esc>jddk
- 创建非递归例子`*noremap`
:nmap x dd
:nnoremap \ x
##9. Leader前导符
- Vim使用中通常不需要的键`-`,`H`,`L`,`<space>`,`<cr>`,`<bs>`
- 按键映射序列，采用`-`作为前导符
:nnoremap -d dd
:nnoremap -c ddO
- 前导符
:let mapleader = "-"
- 使用前导符的理由
    1. 可能需要前导符的正常功能，便于更改
    2. 便于他人查看~/.vimrc时更改自己习惯的前导符
    3. 便于使用vim插件
- 局部前导符，映射特定格式文件
:let maplocalleader = "\\"

##10. Editing Your Vimrc
###编辑映射
:nnoremap <leader>ev :vsplit $MYVIMRC<cr>
- 其中`$MYVIMRC`是指向`~/.vimrc`文件的Vim变量
- `:vsplit`打开新的垂直分割
###使映射生效
:nnoremap <leader>sv :source $MYVIMRC<cr>

##11. Abbreviations
###插入模式下缩写
:iabbrev adn and
:iabbrev waht what
:iabbrev tehn then
###关键字符
设置好缩写后，键入任何`非关键字符`，缩写替换生效
- 查看`关键字符`
:set iskeyword?
- `iskeyword=@,48-57,_,128-167,224-235`中数字表示ASCII码对应的字符
###比较缩写和映射的使用场景
:inoremap liursing --<cr>liurs wq<cr>liurs@njust.edu.cn
- 插入模式下输入`liursing`
- 插入模式下输入`liursing's`
- 改为缩写
```
:iunmap liursing
:iabbrev liursing --<cr>liurs wq<cr>liurs@njust.edu.cn
```

##12. More Mappings
###更复杂的映射
:nnoremap <leader>" viw<esc>a"<esc>bi"<esc>lel
- 上述映射功能为给光标处的单词添加双引号
- `viw`可视模式下选择当前单词
- `<esc>`退出可是模式，将光标留在最后一个字符
- `a`当前字符后进入插入模式
- `"`在文本中插入一个双引号
- `<esc>`返回正常模式
- `b`至单词开头
- `i`在当前字符前进入插入
- `"`文本中再次插入一个双引号
- `<esc>`返回正常模式
- `l`右移使光标置于单词首字母
- `e`光标置于单词尾字母
- `l`光标置于结尾引号
