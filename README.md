# c0
一个C0编译器，采用Python 3实现
C0编译器的设计与实现（10周）
C0语言的语法结构定义如下：
<程序>->[<变量定义部分>] {<自定义函数定义部分>} <主函数>

<变量定义部分>-> int id {, id};
<自定义函数定义部分>-> ( int id | void id) '(' ')' <分程序>
<主函数>->void main'(' ')' <分程序>

<分程序>->'{' [<变量定义部分>] <语句序列> '}'  

<语句序列>-><语句> {<语句>}

<语句>-> <条件语句>｜<循环语句> | '{'<语句序列>'}' | <自定义函数调用语句> 
| <赋值语句> | <返回语句> | <读语句> | <写语句> | ;

<条件语句>->if '('<表达式>')' | <语句> [else <语句> ]
<循环语句>->while '(' <表达式>')' <语句>
<自定义函数调用语句>-><自定义函数调用>;
<赋值语句>->id = <表达式>;
<返回语句>->return ['(' <表达式> ')'] ;
<读语句>->scanf '(' id ')';
<写语句>->printf '(' [ <表达式>] ')';

<表达式>-> [+｜-] <项> { (+｜-) <项>} 
<项> -> <因子>｛(*｜/) <因子>｝
<因子> -> id｜'(' <表达式>')' | num | <自定义函数调用>

<自定义函数调用>->id '(' ')'
