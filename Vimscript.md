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



