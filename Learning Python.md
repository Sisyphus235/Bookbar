# Part I. Getting started

## Chapter 1. A Python Q&A Session
* 使用python的核心理由：
1.software quality, readable, reusable and maintainable; 
2.developer productivity, less to type, 1/5 compared to C, C++, JAVA; 
3.program portability, unchanged results on major computer platforms, such as windows and linux; 
4.support libraries, such as matplotlib and numpy; 
5.component integration, invoke C and C++; 
6.enjoyment.
* python的核心问题：
**代码速度**比C或者C++要慢。However, Python’s speed-of-development gain is often far more important than any speed-of-execution loss, especially given modern computer speeds.
* 使用python能做什么：
1.systems programming(shell tools), writing portable, maintainable system-administration tools and utilities; 
2.GUIs, python原生的tkinter以及在它基础上的其他封装工具；
3.internet scripting, 包括sockets, CGI scripts, FTP, XML, JSON, email, URLs, HTML等等的支持；
4.component integration, python很灵活，常作为胶水语言出现，可以整合C, C++, JAVA等；
5.database programming, 对所有常见结构化数据库都有接口，非结构化数据库有内置的pickle模块可以做对象持久化处理；
6.rapid prototyping, components written in Python and C look the same；
7.numeric and scientific programming, NumPy turns Python into a sophisticated yet easy-to-use numeric programming tool that can often replace existing code written in traditional compiled languages such as FORTRAN or C++；
8.其他，包括gaming, images, data mining, robots, excel等
* python的技术优势是什么：
1.It’s Object-Oriented and Functional，python底层是OOP的，支持多态、重载、多重继承，同时python的OOP也是可选的，也可以用procedural的思路编程，它对functional的支持包括generators, comprehensions, closures, maps, decorators, anonymous function lambdas等 ；
2.It’s free, Python development is performed by a community that largely coordinates its efforts over the Internet;
3.It’s portable, The standard implementation of Python is written in portable ANSI C, and it compiles and runs on virtually every major platform currently in use.;
4.It’s powerful, 1. Its toolset places it between traditional scripting languages (such as Tcl, Scheme, and Perl) and systems development languages (such as C, C++, and Java). Dynamic typing + Automatic memory management + Programming-in-the-large support + Built-in object types + Built-in tools + Library utilities + Third-party utilities;
5.It’s mixable;
6.It’s relatively easy to use;
7.It’s relatively easy to learn
Python originated with a mathematician by training, who seems to have natu- rally produced an orthogonal language with a high degree of uniformity and coherence.
programming is not about being clever and obscure—it’s about how clearly your program communicates its purpose.

## Chapter 2. How Python Runs Programs
* Python interpreter解释器：
> 编译器是一种计算机程序，负责把一种编程语言编写的源码转换成另外一种计算机代码，后者往往是以二进制的形式被称为目标代码(object code)。这个转换的过程通常的目的是生成可执行的程序。
在计算机科学中，解释器是一种计算机程序，它直接执行由编程语言或脚本语言编写的代码，并不会把源代码预编译成机器码。一个解释器，通常会用以下的姿势来执行程序代码：1. 分析源代码，并且直接执行。2. 把源代码翻译成相对更加高效率的中间码，然后立即执行它。3. 执行由解释器内部的编译器预编译后保存的代码

python文件以.py结尾并不是强制的，只对所有需要import的文件强制要求，但一般都以.py结尾保持一致性。
* python执行过程
先做byte code compilation，再交由virtual machine执行。
1.source code
一般以.py结尾
2.byte code
一般以.pyc结尾，是.py的扩展，compiled .py，3.2之前放在文件相同目录下，3.2之后放在__pycache__子路径下。如果运行文件时发现了对应的.pyc则跳过compilation step。如果用户没有写的权限，依然能运行python，只不过文件放在内存中，运行后则删除.pyc对应的byte code。byte code is saved in files only for files that are imported, not for the top-level files of a program that are only run as scripts .
Python byte code is not binary machine code
3.python virtual machines
the PVM is just a big code loop that iterates through your byte code instructions, one by one, to carry out their operations.
the last step of what is called the “Python interpreter.”
![](http://p27x0f47q.bkt.clouddn.com/20181002215950.png)
Python code can be changed on the fly, users can modify the Python parts of a system onsite without needing to have or compile the entire system’s code.
Python implementation alternatives:
1.Cpython
是标准的， coded in portable ANSI C language code
2.Jpython(for java)
targeted for integration with the Java programming language
3.IronPython(for .net)
designed to allow Python programs to integrate with applications coded to work with Microsoft’s .NET Framework for Windows, as well as the Mono open source equivalent for Linux.
4.Stackless(for concurrency)
an enhanced version and reimplementation of the stan- dard CPython language oriented toward concurrency.
5.Pypy(for speed)
another standard CPython reimplementation, focused on performance.
Python frozen binaries
it is possible to turn your Python programs into true executables, known as frozen binaries in the Python world. These programs can be run without requiring a Python installation.
py2exe for Windows, py2app for creating Mac OS X applications, cx_freeze offers both Python 3.X and cross-platform support.

## Chapter 3. How You Run Programs
Besides running programs in interactive way, one can save programs in files, which are usually called modules.
Module files that are run directly are also sometimes called scripts.
Running ways:
Interactive interpreter, system command lines, file icon clicks, module imports, exec calls, IDLE, Frozen Binary Executables
Python imports (loads) a module only once per process, by default, so if you’ve changed its source code and want to run the new version without stopping and restarting Python, you’ll have to reload it.
A namespace is just a package of variables (i.e., names). It takes the form of an object with attributes in Python.

# Part II. Types and Operations

## Chapter 4.Introducing Python Object Types
in Python, data takes the form of objects
Python programs can be decomposed into modules, statements, expressions, and objects, as follows:
1. Programs are composed of modules. 
2. Modules contain statements.
3. Statements contain expressions.
4. Expressions create and process objects.
Three pillars of programming:
1.Do this, then that;
2.Do this if that is true;
3.Do this many times
lists and diction- aries alone are powerful data representation tools, built-in objects preview is as follows:
Numbers, Strings, Lists, Dictionaries, Tuples, Files, Sets, other core types(Booleans, types, None), program unit types(Functions, modules, classes), implementation-related types(Compiled code, stack tracebacks)
there are two ways to print every object in Python—with full precision (as in the first result shown here) “repr", and in a user-friendly form (as in the second) “str”
math, random module
sequence
a positionally ordered collection of other objects: string, list, tuple
len(), index(for negative indexing, it is simply added to the length, i.e., S[-1] = S[len(S)-1]), 
immutability
numbers, strings, and tuples are immutable; lists, dictionaries, and sets are not
Python’s toolset is layered: generic operations that span multiple types show up as built-in functions or expressions (e.g., len(X), X[0]), but type-specific operations are method calls (e.g., aString.upper()).
python普遍适用的方法一般在左侧，比如len(s)，而特殊方法在右侧，比如S.upper()
leading and trailing double underscores is the naming pattern Python uses for implementation details.例如: 
```python
>>> a = 'cat'
>>> a.__add__('fish’)
catfish
```
In Python 3.X, the normal str string handles Unicode text (including ASCII, which is just a simple kind of Unicode); a distinct bytes string type represents raw byte values (including media and encoded text).
list comprehension expression: 
```python
>>> col2 = [row[1] for row in M]
```
Python’s flexibility:
```python
>>> test = { ‘name’: {‘first’: ‘Bob', ‘last’: ‘Smith’},
            ‘jobs’: [‘dev’, ‘mgr’],
            ‘age’: 40.5}
>>> test[‘jobs’].append(‘janitor')
```
nesting allows us to build up complex infor- mation structures directly and easily. Building a similar structure in a low-level language like C would be tedious and require much more code: we would have to lay out and declare structures and arrays, fill out values, link everything together, and so on. 
Just as importantly, in a lower-level language we would have to be careful to clean up all of the object’s space when we no longer need it. In Python, when we lose the last reference to the object—by assigning its variable to something else, for example—all of the memory space occupied by that object’s structure is automatically cleaned up for us.
Iteration:
an object is iterable if it is either a physically stored sequence in memory, or an object that generates one item at a time in the context of an iteration operation.
every Python tool that scans an object from left to right uses the iteration protocol.
File:
Python 3.X draws a sharp distinction between text and binary data in files: text files represent content as normal str strings and per- form Unicode encoding and decoding automatically when writing and reading data, while binary files represent content as a special bytes string and allow you to access file content unaltered. 
Set
sets are neither mappings nor sequences; rather, they are unordered collections of unique and immutable objects.
We tend not to check the type of specific types in one’s code, we care what an object does, not what it is.

## Chapter 5. Numeric Types
Python’s numeric toolbox: 
* Integer and floating-point objects
* Complex number objects
* Decimal: fixed-precision objects
* Fraction: rational number objects
* Sets: collections with numeric operations
* Booleans: true and false
* Built-in functions and modules: round, math, random, etc.
* Expressions; unlimited integer precision; bitwise operations; hex, octal, and binary formats
* Third-party extensions: vectors, libraries, visualization, plotting, etc.
![](http://p27x0f47q.bkt.clouddn.com/20181002220302.png)
Integers are written as strings of decimal digits.
Expression operators
+, -, *, /, >>, **, &, etc. 
Built-in mathematical functions
pow, abs, round, int, hex, bin, etc. 
Utility modules
random, math, etc.
![](http://p27x0f47q.bkt.clouddn.com/20181002220335.png)
Table 5-2 is ordered by operator precedence: 
* Operators lower in the table have higher precedence, and so bind more tightly in mixed expressions. 
* Operators in the same row in Table 5-2 generally group from left to right when combined (except for exponentiation, which groups right to left, and comparisons, which chain left to right).
```python
>>> (2.5).as_integer_ratio()   # float object method
(5, 2)
```
sets can only contain immutable (a.k.a. “hashable”) object types.
the names True and False are instances of bool, which is in turn just a subclass (in the object- oriented sense) of the built-in integer type int.

## Chapter 6. The Dynamic Typing Interlude
dynamic typing model:
In Python, types are determined automatically at runtime, not in response to declarations in your code.
A variable (i.e., name), like a, is created when your code first assigns it a value. A variable never has any type information or constraints associated with it. When a variable appears in an expression, it is immediately replaced with the object that it currently refers to, whatever that may be.
In sum, variables are created when assigned, can reference any type of object, and must be assigned before they are referenced. 
![](http://p27x0f47q.bkt.clouddn.com/20181002220434.png)
* Variables are entries in a system table, with spaces for links to objects.
* Objects are pieces of allocated memory, with enough space to represent the values for which they stand.
* References are automatically followed pointers from variables to objects.
Each object also has two standard header fields: a type designator used to mark the type of the object, and a reference counter used to determine when it’s OK to reclaim the object.
shared reference:
This scenario in Python—with multiple names referencing the same object—is usually called a shared reference.
查看引用次数
```python
>>> import sys
>>> sys.getrefcount(<object>)
```

## Chapter 7. String Fundamentals
string—an ordered collection of characters used to store and represent text- and bytes-based information.
In Python 3.X there are three string types: str is used for Unicode text (including ASCII), bytes is used for binary data (including encoded text), and bytearray is a mutable variant of bytes. 
Strictly speaking, Python strings are categorized as immutable sequences, meaning that the characters they contain have a left-to-right positional order and that they cannot be changed in place. 
![](http://p27x0f47q.bkt.clouddn.com/20181002220528.png)
![](http://p27x0f47q.bkt.clouddn.com/20181002220616.png)
backslashes are used to introduce special character codings known as escape sequences.
![](http://p27x0f47q.bkt.clouddn.com/20181002220643.png)
![](http://p27x0f47q.bkt.clouddn.com/20181002220708.png)
string format:
![](http://p27x0f47q.bkt.clouddn.com/20181002220730.png)
```python
%[(keyname)][flags][width][.precision]typecode

>>> template = '{0}, {1} and {2}'
>>> template.format('spam', 'ham', 'eggs’) 
'spam, ham and eggs’

>>> template = '{motto}, {pork} and {food}'
>>> template.format(motto='spam', pork='ham', food='eggs’) 
'spam, ham and eggs’

>>> import sys
>>> 'My {1[kind]} runs {0.platform}'.format(sys, {'kind': 'laptop'}) 
'My laptop runs win32'
```
Square brackets in format strings can name list (and other sequence) offsets to perform indexing, too, but only single positive offsets work syntactically within format strings, so this feature is not as general as you might think.
```python
>>> somelist = list('SPAM’) 
>>> somelist
['S', 'P', 'A', 'M’]

>>> 'first={0[0]}, third={0[2]}'.format(somelist) 
'first=S, third=A’

>>> 'first={0}, last={1}'.format(somelist[0], somelist[-1]) 
'first=S, last=M’

>>> parts = somelist[0], somelist[-1], somelist[1:3] 
>>> 'first={0}, last={1}, middle={2}'.format(*parts) 
"first=S, last=M, middle=['P', 'A']"
```
the format built-in runs the subject object’s __format__ method

## chapter 8. Lists and Dictionaries
Lists:
Ordered collections of arbitrary objects; Accessed by offset; Variable-length, heterogeneous, and arbitrarily nestable; Of the category “mutable sequence”
lists really are arrays inside the standard Python interpreter, not linked structures
![](http://p27x0f47q.bkt.clouddn.com/20181002220856.png)
![](http://p27x0f47q.bkt.clouddn.com/20181002220910.png)
append and sort change the associated list object in place, but don’t return the list as a result
Dictionaries:
the chief distinction between lists and dictionaries is that in dictionaries, items are stored and fetched by key, instead of by positional offset.
Accessed by key, not offset position; Unordered collections of arbitrary objects; Variable-length, heterogeneous, and arbitrarily nestable; Of the category “mutable mapping”; Tables of object references (hash tables)
![](http://p27x0f47q.bkt.clouddn.com/20181002220938.png)
* Dictionaries are mappings, not sequences
Avoiding missing-key errors：
```python
if (2, 3, 6) in Matrix: 
   print(Matrix[(2, 3, 6)])
else: 
   print(0)

try:
   print(Matrix[(2, 3, 6)])
except KeyError: 
   print(0)

Matrix.get((2, 3, 4), 0) 
```
create dictionaries:
```python
{'name': 'Bob', 'age': 40}  # Traditional literal expression

D = {}   # Assign by keys dynamically
D['name'] = 'Bob’ 
D['age'] = 40

dict(name='Bob', age=40)  # dict keyword argument form

dict([('name', 'Bob'), ('age', 40)])  # dict key/value tuples form
```
* The first is handy if you can spell out the entire dictionary ahead of time.
* The second is of use if you need to create the dictionary one field at a time on the fly.
* The third involves less typing than the first, but it requires all keys to be strings.
* The last is useful if you need to build up keys and values as sequences at runtime.

## Chapter 9.Tuples, Files, and Everything Else
tuple, a collection of other objects that cannot be changed
the file, an interface to external files on your computer.
named tuples are a tuple/class/dictionary hybrid.
pickle:
```python
>>> import pickle
>>> x = {‘a’: 1, ‘b’: 2}
>>> with open(‘test.pkl’, ‘wb’) as f:
       pickle.dump(x, f)
# 生成了一个pickle的文档储存x这个object
>>> with open(‘test.pkl’, ‘wr’) as f:
       y = pickle.load(x)
       print(y)
# y就是加载后的x object
```
![](http://p27x0f47q.bkt.clouddn.com/20181002221123.png)
* Lists, dictionaries, and tuples can hold any kind of object.
* Sets can contain any type of immutable object.
* Lists, dictionaries, and tuples can be arbitrarily nested.
* Lists, dictionaries, and sets can dynamically grow and shrink.
![](http://p27x0f47q.bkt.clouddn.com/20181002221139.png)
if a collection object contains a reference to itself, it’s called a cyclic object.

# Part III. Statements and Syntax

## Chapter 10. Introducing Python Statements
![](http://p27x0f47q.bkt.clouddn.com/20181002221216.png)
![](http://p27x0f47q.bkt.clouddn.com/20181002221230.png)

## Chapter 11. Assignments, Expressions, and Prints
assignment statements:
Assignments create object references; Names are created when first assigned; Names must be assigned before being referenced; Some operations perform assignments implicitly.
![](http://p27x0f47q.bkt.clouddn.com/20181002221312.png)
![](http://p27x0f47q.bkt.clouddn.com/20181002221326.png)
![](http://p27x0f47q.bkt.clouddn.com/20181002221336.png)

## Chapter 12. if Tests and Syntax Rules

## Chapter 13. while and for Loops
Loop format
```python
while test: 
   statements
   if test: break        # Exit loop now, skip else if present
   if test: continue     # Go to top of loop now, to test1
else:
   statements            # Run if we didn't hit a 'break'
   
for target in object:     # Assign object items to target
   statements
   if test: break        # Exit loop now, skip else
   if test: continue     # Go to top of loop now
else:
   statements            # If we didn't hit a 'break'
```

## Chapter 14. Iterations and Comprehensions
iterators run at C language speed inside Python, whereas the while loop version runs Python byte code through the Python virtual machine
![](http://p27x0f47q.bkt.clouddn.com/20181002221449.png)
User-defined classes are made iterable with __iter__ or __getitem__ operator over- loading.

## Chapter 15. The Documentation Interlude
__doc__, dir(), help() to get documentations

# Part IV. Functions and Generators

## Chapter 16.Function Basics
functions serve two primary development roles:
Maximizing code reuse and minimizing redundancy; Procedural decomposition
A function returns the None object by default if the control flow falls off the end of the function body without running into a return statement.

## Chapter 17.Scopes
* Names assigned inside a def can only be seen by the code within that def. You cannot even refer to such names from outside the function.
* If a variable is assigned inside a def, it is local to that function.
* If a variable is assigned in an enclosing def, it is nonlocal to nested functions.
* If a variable is assigned outside all defs, it is global to the entire file.
Name Resolution: LEGB Rule
* Name assignments create or change local names by default.
* Name references search at most four scopes: local, then enclosing functions (if any),
then global, then built-in.
* Names declared in global and nonlocal statements map assigned names to en- closing module and function scopes, respectively.
![](http://p27x0f47q.bkt.clouddn.com/20181002221552.png)
The LEGB scope lookup rule. When a variable is referenced, Python searches for it in this order: in the local scope, in any enclosing functions’ local scopes, in the global scope, and finally in the built-in scope. The first occurrence wins. The place in your code where a variable is assigned usually determines its scope. In Python 3.X, nonlocal declarations can also force names to be mapped to enclosing function scopes, whether assigned or not.

3 more scopes: temporary loop variables in some comprehensions, exception reference vari- ables in some try handlers, and local scopes in class statements.
Functions are self-contained units of software.
python3.X的builtins是在builtins module下面的，直接使用相当于在LEGB检索最后的B中发现，本质上和引入builtins的module是一样的，如下：
```python
import builtins
zip is builtins.zip

>>> True
```
the nonlocal statement is almost identical but applies to names in the enclosing def’s local scope
Program Design: Minimize Global Variables

* A reference firstly looks for the name in the current scope, then in the local scopes of any lexically enclosing functions in your source code, from inner to outer; then in the current global scope (the module file); and finally in the built-in scope (the module builtins). global declarations make the search begin in the global (module file) scope instead.
* An assignment (X = value) creates or changes the name X in the current local scope, by default. If X is declared global within the function, the assignment creates or changes the name X in the enclosing module’s scope instead. If, on the other hand, X is declared nonlocal within the function in 3.X (only), the assignment changes the name X in the closest enclosing function’s local scope.
factory functions: closures
factory functions describe a functional programming technique and closures denote a design pattern. 
enclosure的高级用法，用来记录state，往往和lambda联用
```python
def maker(N):
    return lambda X: X ** N

h = maker(3)
h(4)

outputs: 4 ** 3 = 64
```
closures vs class
class may be better at implementing more complete objects, like customization by inheritance and operator overloading.  
values can be retained from call to call in global variables: class inheritance attributes; enclosing scope; argument defaults; function attributes.  
in the Pythonic view, flat is generally better than nested.  

global vs nonlocal
nonlocal also means “skip my local scope entirely."  
• global makes scope lookup begin in the enclosing module’s scope and allows names there to be assigned. Scope lookup continues on to the built-in scope if the name does not exist in the module, but assignments to global names always create or change them in the module’s scope.
• nonlocal restricts scope lookup to just enclosing defs, requires that the names al- ready exist there, and allows them to be assigned. Scope lookup does not continue on to the global or built-in scopes.

function attributes: user-defined names attached to functions directly.  
```python
def tester(start):
    def nested(label):
        print(label, nested.state)
        nested.state += 1
    nested.state = start
    return nested

F = tester(0)
F(‘spam’)
output: spam 0
F(‘ham’)
output: ham 1
F.state
output: 2
```

## Chapter 18.Arguments
> 学习programming language中最重要的两个理解要点是：1.type checking, 2. value binding

python中的传参默认是指针传输（pointer），不会自动copy传输的对象。且参数名在local层面。
这里要注意python虽然传参都是通过pointer，但python的object分为mutable和immutable，二者不同。对于mutable的参数来说，例如list和dict，参数在local层面修改会影响原参数；但对immutable参数来说，例如int和str，参数在local层面修改不影响原参数。
```python
# immutable
a = 1
def my(x):     
    x += 1
    print(x)
my(a)
>>> 2
print(a)
>>> 1

## immutable
a = [1]
def my(x):
    x[0] += 1
    print(x)
my(a)
>>> [2]
print(a)
>>> [2]
```
* function

![](http://p27x0f47q.bkt.clouddn.com/python_function.jpeg)
函数传参时要遵循的规则：1.首先是按位置检索的参数positional argument，然后是按名字检索的参数keyword argument，再者是*iterable，最后是**dict
*可以用来pack和unpack
```python
def my(x, y, z, t):
    print(x, y, z, t)
my(*(1, 2), **{'t': 3, 'z': 4})
>>> 1 2 4 3
```
key-word only传参能同时满足传递多个参数和固定参数的双重选择，在python3.x可用
```python
def kwonly(a, *b, c):  # c必须以keyword方式传入
    print(a, b, c)

kwonly(1, 2, c=3)
>>> 1 (2, ) 3
kwonly(a=1, c=3)
>>> 1 () 3
kwonly(1, 2, 3)
>>> kwonly() missing 1 required keyword-only argument: 'c'
```
这种模式能够省去多余参数校检和处理的工作
```python
# 这样的设计无法避免notify被错误赋值，例如process(1, 2, 3)，notify会被assign为3
def process(X, Y notify=True):
    pass

# 这样的设计可以避免notify被positional argument错误赋值
def process(*args, notify=True):
    pass
```
设计一个函数，传入任意类型任意数量的变量，返回最小值
```python
def mymin(*args):
    tmp = list(args)
    tmp.sort()
    return tmp[0]
使用sort()方法效率高，是用C语言编写的，比for循环在python中比较每个元素的速度要更快

mymin('ca', 'd', 'ba')
>>> 'ba'
```
exercises
```python
>>> def func(a, b=4, c=5): 
        print(a, b, c)
>>> func(1, 2)
1, 2, 5

>>> def func(a, b, c=5): 
        print(a, b, c)
>>> func(1, c=3, b=2)
1, 2, 3

>>> def func(a, *pargs): 
        print(a, pargs)
>>> func(1, 2, 3)
1, (2, 3)

>>> def func(a, **kargs): 
         print(a, kargs)
>>> func(a=1, c=3, b=2)
1, {'c': 3, 'b': 2}

>>> def func(a, b, c=3, d=4): 
        print(a, b, c, d)
>>> func(1, *(5, 6))
1, 5, 6, 4

>>> def func(a, b, c): 
        a = 2; b[0] = 'x'; c['a'] = 'y' 
>>> l=1; m=[1]; n={'a':0}
>>> func(l, m, n)
>>> l, m, n
1, ['x'], {'a':'y'}
```

## Chapter 19. Advanced Function Topics
这章主要包括recursive functions, function attributes and annotations, the lambda expression, functional programming tools like **map and filter**.
实现一个功能往往需要将任务进行拆分function cohesion，function间通讯function coupling。
基于Python，建议用input和output来保证function的independency，尽量少用global variables，如果输入有mutable argument，尽量减少对其的赋值。
mutable variables的赋值通常是通过class进行的，如果不使用class，往往要依靠global variables。
![](http://p27x0f47q.bkt.clouddn.com/20181002215924.png)
* recursion

python的recursion限制是1000层
```python
>>> import sys
>>> sys.getrecursionlimit()
1000
```
修改深度
```python
sys.setrecursionlimit(2000)
```
recursion很强大，但一定要完全理解的情况下使用，有些情况会误触发recursion，要警惕，传输class中的\_\_setattr\_\_, \_\_getattribute\_\_, \_\_repr\_\_。
* attributes and annotations

python function是objects，能够非常灵活的调用。
```python
def echo(m):
    print(m)
    
x = echo
x('hello')
>>> 'hello'

def indirect(func, arg):
    func(arg)
    
indirect(x, 'again')
>>> 'again'

for (func, arg) in [(x, 'one'), (x, 'two')]:
    func(arg)
>>> one
>>> two
```
上面的程序用一个变量x指向了函数echo的对象，然后另一个函数的参数是x，甚至可以在表达式中使用函数对象。python的这种特性往往被称作**first-class object model**
function introspection在了解程序功能上很重要
```python
func.__name__
dir(func)
func.__code__
```
同时function object还可以附加用户自定义的属性
```python
func.count = 0
```
function annotation可以写在def中
```python
def func(a: 'spam', b: (1, 10), c: float) -> int:
    return a + b + c
>>> func(1, 2, 3)
6
>>> func.__annotations__
{'a': 'spam', 'b': (1, 10), 'c': <class 'float'>, 'return': <class 'int'>}
```
* lambda expression


从Lisp语言的symbolic logic演变而来，在python中是anonymous function。
```python
lambda arg1, arg2 ... : expression using arguments
```
lambda和def最大的区别在于lambda是expression，而def是statement，所以lambda可以在很多def无法使用的地方出现。因此，def用name来做reference，lambda可以选择是否使用name做reference。lambda的body是single expression，def是a block of statments。
```python
f = lambda x, y, z: x + y + z
f(2, 3, 4)

# 上面的lambda等价于下面的def
def func(x, y, z):
    return x + y + z
func(2, 3, 4)
```
def和lambda的嵌套
```python
>>> def knights():
        titile = 'Sir'
        action = (lambda x: title + ' ' + x)
        return action
>>> act = knights()
>>> msg = act('robin')
>>> msg
'Sir robin'
```
lambda的嵌套（nesting）
```python
>>> action = (lambda x: (lambda y: x + y))
>>> act = action(99)
>>> act(3)
102
```
建议妥善使用lambda expression，因为它容易引起代码不可读的问题。
* Functional programming tools


**map function applies a passed-in function to each item in an iterable object and returns a list containing all the function call resutls.**
例如：
```python
>>> def inc(x):
        return x + 10
>>> counters = [1, 2, 3, 4]
>>> list(map(inc, counters))
[11, 12, 13, 14]
```
map call类似于list comprehension expressions
```python
>>> list(map(inc, [1, 2, 3, 4]))
[11, 12, 13, 14]
>>> [inc(x) for x in [1, 2, 3, 4]]
[11, 12, 13, 14]
```
**filter and reduce, select an iterable's items based on a test function and apply functions to item pair, respectively.**
```python
>>> list(filter((lambda x: x > 0), range(-5, 5))
[1, 2, 3, 4]

# 等价于
>>> [x for x in range(-5, 5) if x > 0]
[1, 2, 3, 4]

# 等价于
>>> res = []
>>> for x in range(-5, 5):
        if x > 0:
            res.append(x)
>>> res
[1, 2, 3, 4]
```
reduce要复杂一些，它逐步迭代完成任务：
```python
>>> def myreduce(function, sequence):
        tally = sequence[0]
        for next in sequence[1: ]:
            tally = function(tally, next)
        return tally
>>> myreduce((lambda x, y: x + y), [1, 2, 3, 4, 5])
15
>>> myreduce(lambda x, y: x * y), [1, 2, 3, 4,5])
120
```
map passes each item to the function and collects all results, filter collects items for which the function returns a True value, and reduce computes a single value by applying the function to an accumulator and successive items. 
Functions can send back results with return statements, by changing passed-in mutable arguments, and by setting global variables.

## Chapter 20. Comprehensions and Generations
* Comprehensions 
 
list comprehensions apply an arbitrary expression to items in an iterable, rather than applying a function. 未来comprehension还会作用于sets, dictionaries, value generator expressions。
 基本语法
 ```python
 [ expression for target in iterable]
 可以扩展为
 [expression for target1 in iterable1 if condition1
             for target2 in iterable2 if condition2 ...
             for targetN in iterableN if conditionN]
 ```
 ```python
 >>> [x ** 2 for x in range(10) if x % 2 == 0]
 [0, 4, 16, 36, 64]
 
 # 等价于
 >>> list(map((lambda x: x ** 2), filter((lambda x: x % 2 == 0), range(10))))
  [0, 4, 16, 36, 64]
 ```
 上面的例子对比发现，map, filter和reduce的功能虽然和list comprehension类似，但lsit comprehension处理复杂问题上的可读性更好。
 当list comprehension被nest的时候，换容易变得难以阅读，永远记得：
 > simple is better than complex
* Generations
 
*Generator functions* are coded as normal **def** statements, but use **yield** statements to return results one at a time, suspending and resuming their state between each.
*Generator expressions* are similar to the list comprehensions, but they return an object that produces results on demand instead of building a result list.
iterator objects定义了__next__，或者返回next item，或者返回StopIteration。
generator的最大价值在于节省memory use，同时在大型项目中有更好的performance。
with a generator and no send, it's a one way street
```
==========       yield      ========
Generator |   ------------> | User |
==========                  ========
```
But with send, it becomes a two way street
```
==========       yield       ========
Generator |   ------------>  | User |
==========    <------------  ========
                  send
```
```python
>>> def f():
...     while True:
...         val = yield
...         yield val*10
... 
>>> g = f()
>>> g.next()
>>> g.send(1)
10
>>> g.next()
>>> g.send(10)
100
>>> g.next()
>>> g.send(0.5)
5.0
>>> 
```
generator expressions example:
```python
>>> G = [x ** 2 for x in range(4)]
>>> iter(G) is G
False
>>> next(G)
0
>>> next(G)
1
>>> next(G)
4
>>> next(G)
9

>>> G = (x ** 2 for x in range(4))
>>> iter(G) is G
True
```
A function def statement that contains a yield statment is turned into a generator function.
A comprehension expressio enclosed in parenthesses is known as generator expression.
python3.3 syntax更加concise和explicit
```python
>>> def both(N):
        yield from range(N)
        yield from (x ** 2 for x in range(N))
>>> list(both(5))
[0, 1, 2, 3, 4, 0, 1, 4, 9, 16]
```
four forms of comprehension in Python: list, generator, set, and dictionary
List comprehensions in square brackets produce the result list all at once in mem- ory. When they are enclosed in parentheses instead, they are actually generator expressions—they have a similar meaning but do not produce the result list all at once. Instead, generator expressions return a generator object, which yields one item in the result at a time when used in an iteration context.

## Chapter 21. The Benchmarking Interlude
**list comprehensions** sometimes have a speed advantage over **for loop** statements, and that **map calls** can be faster or slower than both depending on call patterns.
The **generator functions and expressions** of the preceding chapter tend to be slightly slower than **list comprehensions**, though they minimize memory space requirements and don’t delay result generation.
* time module
```python
import time
def timer(func, *args):
    start = time.clock()
    for i in range(1000):
        func(*args)
    return time.clock() - start
    
>>> timer(pow, 2, 1000)
0.00296260674205626
>>> timer(str.upper, 'spam') # Time to call 'spam'.upper() 1000 times 0.0005165746166859719
```
clock随着platform的不同变化很大，相对而言perf_counter和process_time更加可靠。
**time.perf_counter()** returns the value in fractional seconds of a performance counter, defined as a clock with the highest available resolution to measure a short duration.
**time.process_time()** returns the value in fractional seconds of the sum of the sys- tem and user CPU time of the current process. 
* timing module alternatives

```python
"""
total(spam, 1, 2, a=3, b=4, _reps=1000) calls and times spam(1, 2, a=3, b=4) _reps times, and returns total time for all runs, with final result.
bestof(spam, 1, 2, a=3, b=4, _reps=5) runs best-of-N timer to attempt to filter out system load variation, and returns best time among _reps tests.
bestoftotal(spam 1, 2, a=3, b=4, _rep1=5, reps=1000) runs best-of-totals test, which takes the best among _reps1 runs of (the total of _reps runs); 
"""

import time, sys
timer = time.clock if sys.platform[:3] == 'win' else time.time

def total(func, *pargs, **kargs): 
    _reps = kargs.pop('_reps', 1000)   # Passed-in or default reps
    repslist = list(range(_reps))   # Hoist range out for 2.X lists
    start = timer()
    for i in repslist:
        ret = func(*pargs, **kargs)
    elapsed = timer() - start 
    return (elapsed, ret)
    
def bestof(func, *pargs, **kargs): 
    _reps = kargs.pop('_reps', 5) 
    best = 2 ** 32
    for i in range(_reps):
        start = timer()
        ret = func(*pargs, **kargs) 
        elapsed = timer() - start
        if elapsed < best: 
            best = elapsed
    return (best, ret)
    
def bestoftotal(func, *pargs, **kargs):
    _reps1 = kargs.pop('_reps1', 5)
    return min(total(func, *pargs, **kargs) for i in range(_reps1))
```
第三方库检测运行速度，可以使用pystone.py
list comprehensions are usually the quickest of the bunch; map beats list comprehensions in Python only when all tools must call functions; for loops tend to be slower than comprehensions; and generator functions and expressions are slower than comprehensions by a constant factor.

# Part V.Modules and Packages

## Chapter 22.Modules: The Big Picture
module是python中highest level program organization unit，它会打包program code and data，提供封装的命名空间。
modules主要功能：1.code reuse, 2.system namespace partitioning, 3.implementing shared services or data.
Python structure: 包含python statements的text files，其中有一个top-level file，其余是supplemental files，通常也叫modules。top-level file包含main flow of control。
A file imports a module to gain access to the tools it defines, which are known as its attributes—variable names attached to objects such as functions. 
![](http://p27x0f47q.bkt.clouddn.com/20181010121747.png)

modules是最高级的organizational structure，也是highest level of code reuse。
import与C中的#include不同，不仅仅是一段代码的插入，更是runtime operations，包括：1.找到module's file; 2.compile it to byte code; 3.Run the module's code to build the objects it defines.
一般运行时会去__pycache__路径下寻找对象，如果找到则不再编译，否则寻找到module后编译为二进制存储在.pyc中。寻找路径包括program home directory, PYTHONPATH directory, standard library dierectory, .pth files, site-packages home of third-party extensions.

## Chapter 23.Module Coding Basics
所有.py的文件都可以成为python module，top level指定的变量都是attributes。原则上python的文件不必须以.py结尾，但如果要被import，则必须以.py结尾。
使用modules通常用from和import，from会fetch specific names在modules中，import将module看成一个整体引入。
from statement has the potential to corrupt namespaces, the from statement has more serious issues when used in conjunc- tion with the reload call, as imported names might reference prior versions of objects.通常相比于使用from而言，import更加好。
```python
# A.py
def func():
    pass
    
# B.py
def func():
    pass
    
# Incorrect.py
from A import func
from B import func
func()  # 这里调用的是B的func，namespace被干扰

# Correct.py
import A
import B
A.func()
B.func()  # namespace不互相影响
```

## Chapter 24.Module Packages
import不仅引入了另一个路径的方法，而且为另一个路径创建了一个namespace。
python package在3.3之后如果被其他文件import，在package中要有__init__.py文件。
```shell
dir0\
    dir1\
        __init__.py
        dir2\
            __init__.py
            mod.py
```
```python
import dir1.dir2.mod
```
\_\_init__.py的作用：1.declare a directory as python package; 2.generate a module namespace. 
同时可以在\_\_init__.py中定义\_\_all__的lists来说明所有可以被from * statement导出的内容。

PEP8 推荐使用绝对路径引用，因为这样可读性强更便携，而不是使用相对路径引用。
> Relative imports for intra-package imports are highly discouraged. Always use the absolute package path for all imports. Even now that PEP 328 [7] is fully implemented in Python 2.5, its style of explicit relative imports is actively discouraged; absolute imports are more portable and usually more readable.

module的搜索规则：
* Basic modules with simple names (e.g., A) are located by searching each directory on the sys.path list, from left to right. 
* Packages are simply directories of Python modules with a special __init__.py file, which enables A.B.C directory path syntax in imports. In an import of A.B.C, for example, the directory named A is located relative to the normal module import search of sys.path, B is another package subdirectory within A, and C is a module or other importable item within B.
* Within a package’s files, normal import and from statements use the same sys.path search rule as imports elsewhere. 