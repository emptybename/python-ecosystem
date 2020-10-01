# Python Interview Questions

### What is Python?
Python is a high-level, interpreted, general-purpose programming language. Being a general-purpose language, 
it can be used to build almost any type of application with the right tools/libraries. Additionally, python supports 
objects, modules, threads, exception-handling and automatic memory management which help in modelling real-world 
problems and building applications to solve these problems.

##### Advantages to use python
- It allows to you write code very quickly.
- High developer throughput(More code in less time)
- Easy to learn.
- Large ecosystem support.
- Python also allows you to quickly experiment with things. That's why python also use in data science. 
- Moreover, the language is capable of scripting, completely open-source and supports third-party packages 
  encouraging modularity and code-reuse.
- Its high-level data structures, combined with dynamic typing and dynamic binding, attract a huge community of 
  developers for Rapid Application Development and deployment.
 

```
Key Points -
- Python is a high level language
- Python is an interpreted language(See below for difference between compiled language and interpreted language)
- Python is dynamically typed language(See Below for more info)
```

### What is a dynamically typed language?
Before we understand what a dynamically typed language, we should learn about what typing is. Typing refers to 
type-checking in programming languages. 

In a strongly-typed  language, such as Python, 
"1" + 2 will result in a type error, 
<br>
since these languages don't allow for "type-coercion" (implicit conversion of data types). 
On the other hand, a weakly-typed  language, such as Javascript, will simply output "12" as result.

Type-checking can be done at two stages -
```
Static - Data Types are checked before execution.
Dynamic - Data Types are checked during execution.
```

Python being an interpreted language, executes each statement line by line and thus type-checking is done on the fly, 
during execution. Hence, Python is a Dynamically Typed language.

**Important**
Since python is a dynamic typed language. This does not mean python doesn't support static type checking
Using Mypy(It is static type checker) you can optionally support static type checking. It checks type error before 
you run your code  
### What is Interpreted Language and what type of language python is?
First we will discuss what is the difference between compiled and interpreted language.

#### Compiled Language:
Like C++, Java. we require to explicitly compile the source code which generate the byte code which we run.

#### Interpreted Language:
In we don't need to compile the source code first. It happens automatically and does not require explicit compilation.
Programs written in an interpreted language runs directly from the source code.

- Compiled Language - Explicit Compilation
- Interpreted Language - Non-explicit compilation

```
Python is an interpreted language.

Steps happens while running python program
lets say we have somefile.py file
using CPython Interpreter we run this file
python somefile.py
compiles -> python bytecode(this happens automatically)
starts executing it from top to bottom
There is no distinction between comiplation phase, runtime in python.
**In python you have only runtime error**.

On the other hand in compiled languages like C++, Java
we explicitly compile program and generate byte code which we run
**In C++ and Java you can have compile time error as well as run time error**  
``` 

### What is the difference between Cpython, Cython, Pypy..?
These are basically different python interpreters or can say variations or sometimes called different styles of python.  

- Python is a language specification.
- Cpython is an interpreter which is written in C. It actually implements python language specifications. 
- Like C++ is a language specification and gcc is a compiler.

Cpython is not the only interpreter. We have many other interpreters of python which are written in different languages.
- IronPython - It uses the .Net framework and allows nice inter portability between python and .Net code. You can 
  easily import .Net code in your python code.
- Jython -  Run over the JVM and allows you to call java code with in python.
- Cpython - Written in C, allows you to call C function from python
-  Pypy - Written in python it self. It has JIT(just in time) compiler. which compile code on the fly. 
   This way it is much faster than Cpython.


### What is the difference between python2 and python3 ?
- Python 3 syntax is simpler and easily understandable whereas Python 2 syntax is comparatively difficult to understand.
- Python 3 default storing of strings is Unicode whereas Python 2 stores need to define Unicode string value with "u."
- Python 3 value of variables never changes whereas in Python 2 value of the global variable will be changed 
  while using it inside for-loop.
- Python 3 exceptions should be enclosed in parenthesis while Python 2 exceptions should be enclosed in notations.
- Python 3 rules of ordering comparisons are simplified whereas Python 2 rules of ordering comparison are complex.
- Python 3 offers Range() function to perform iterations whereas, In Python 2, the xrange() is used for iterations.
- In python 3 print is a function while in python 2 print is an statement
  ( You can use print as a function in python2 by).

  ``` from __future__ import print_function```.

- Not difficult to port python 2 to python 3 but it is never reliable. 
  Python version 3 is not backwardly compatible with Python 2.


### Is self a keyword in python?
- No self is not a keyword in python.
- You can import all keywords in python using 
  ``` 
  import keyword
  print(keyword.kwlist)
  
  class Foo:
    def func(self):
        print(self) # here self is an instance of class Foo
  
  You can also do like
  class Foo:
    def func(some_other):
        print(some_other) # here some_other is an instance of class.
  
  ```
### Keywords in python

```
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 
'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 
'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

- `False, True` are boolean keywords of class bool
- `or, not, and` are boolean logical operators
- `as` often uses in context manager
    ```
    with open('file.txt', r) as f:
        pass
    Here f is object of the file
    ```
- `assert` tests boolean condition. Something like in unit test.
   ```
    assert 2 == 3, "message"
    This will raise an error with message
   ```
- `from` is used for importing.
- `global` is used to tell python that the current variable i am using belongs to global name space.
    ```
        a = 10
        def foo():
            global a
            a = 1
        print(a) # a = 10
        foo()
        print(a) # a = 1        
    ```
- `pass`- 
    - The pass statement is used as a placeholder for future code.
    - When the pass statement is executed, nothing happens, but you avoid getting an error when empty code is not allowed.
    - Empty code is not allowed in loops, function definitions, class definitions, or in if statements.
  ```
    if a > 10:
        pass # No- operation statement
    print("Done") # You will not get any error
  ```

### What built in types does python support?
Like in c++, Java we have
```
int, bool, float, arrays, long, string, byte...
```
In python built in data-types are - 
```
    values = [
        2, # int
        2.4, # float
        True, # bool
        None, # NoneType
        'python', # String
        (1,2,3), # tuple
        [1,2,'a'], # List
        {1,2,3}, # Set
        range(2,5), # range
        frozenset({1,2,3,4}), # frozen set that is immutable
        1+2j # complex
    ]
    for value in values:
        print(type(value), value)

    <class 'int'> 2
    <class 'float'> 2.4
    <class 'bool'> True
    <class 'NoneType'> None
    <class 'str'> python
    <class 'tuple'> (1, 2, 3)
    <class 'list'> [1, 2, 'a']
    <class 'set'> {1, 2, 3}
    <class 'range'> range(2, 5)
    <class 'frozenset'> frozenset({1, 2, 3, 4})
    <class 'complex'> (1+2j)
```

### What is PEP 8 ?
PEP - Python Enhancement Proposals.

PEP-8 - It is a set of guidelines(not rules) to make sure your code is formatted properly. 

### What is PEP, PIP, PyPI?
- PEP - Python Enhancement Proposals.
- PIP - Package Installer for Python
- PyPI - Python Package Index(Where all the packages are stored)


### Tuple Vs List
- Tuples are immutable. where as List are mutable.
  ```
    a = (1,2,3)
    a[2] = 4 # raise error
    l = [1,2,3]
    l[2] = 4 # success
    
  By Default if you initialize variable without paranthesis then it will be tuple
  e.g
    t = 1,2,3 # it will be tuple
    print(type(t)) # <class 'tuple'>
    
    t = (1,2,3) # It will be tuple
    l = [1,2,3] # it will be List
  
    def foo():
        return 1, 2, 3 # You are returning tuple
    t = foo()
    print(type(t)) # <class 'tuple'>
  ```
  
### If you have to print the elements of dictionary in the order of insertion how would you do that?

- <= 3.5 python version dictionary were not ordered.
- In python 3.6 dictionary was still not ordered.
  However, Cpython interpreter, dictionaries were ordered in the order of insertion.
  In other interpreters, it may not happen
- Python3.7 onwards ->  Dictionaries are ordered in the order of insertion. It is part of python specification.

But to make sure your elements are in the order of their insertion, use

OrderedDict() are always guaranteed to persist the insertion order.

### What is wrong with import *
-  Pollutes of namespace.
   ```
   e.g
   
   def randint():
        return 4
   from random import *
   Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    TypeError: randint() missing 2 required positional arguments: 'a' and 'b'
   
   randint() # Throw an error because random.randint(a, b) takes parameter but our randint defind function does not But
   Since import overrides our randint function it is calling random.randint
   ```

- Difficult to understand where the function is coming from.
  - One piece of code is 
  ```
    import random
    values = [1, 2, 3, 4, 5]
    print(random.choices(values)) # will print one of the value from values   
  ```
  - Other piece of code - 
  ```
    from random import *
    from requests import *
    values = [1, 2, 3, 4, 5]
    print(choices(values)) # will print one of the value from values   
  ```
  - These two pieces of code do the same thing but 1st one is more readable.


### What is the difference B/w list comprehension and tuple comprehension?
- List Comprehension
```
squares = []
for i in range(10):
    squares.append(i*i)

# There is way to do the same in python is called list comprehension
squares = [i*i for i in range(10)]  # List Comprehesion
print(squares) # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

- Dictionary Comprehension
```
cubes = {i: i**3 for i in range(10)}
print(cubes)  # {0: 0, 1: 1, 2: 8, 3: 27, 4: 64, 5: 125, 6: 216, 7: 343, 8: 512, 9: 729}
```

- Tuple Comprehension/ Generator expression
```
whole = (i for i in range(10))
print(whole) # <generator object <genexpr> at 0x10b1edf20>
It creates an object or can say generator not the entire list

# It also called lazy computation
# It is memory optimised.
next(whole) # 0
next(whole) # 1
```

### How python Garbage collector works?

First we discuss one case where some thing strange happens : -
```
    for i in range(10000000000):
        print(i)
    when this loop runs

    consumer process
    queue can overflow
    1
    2
    3
    ...... print smoothly 
    1000
    pause(for some time)
    1001
    .....print smoothly
    5000
    pause(for some time)
    again print smoothly
    So, what is going here is for some time pause happens and then start printing and same thing happens..
    So if same thing happens in producer consumer problem where producer is putting in the queue and consumer is taking 
    pause in that case Queue can be overflow.
    So to avoid this situation. we use garbage collector.
```
In C/C++, we have manual memory management

```
int ar[10];
int *ar;
ar = malloc(...)
// It will allocate the space on the heap
// C++ is not going to free that memory automatically. you have to do it manually.
// If you forget to free the memory ->  It is called memory leak.
// Or if you free the memory and then try to use
So manual memory management is a teadeous task.  
```
So language like Python, Java, Javascript all these provide something called garbage collector.
What GC do? It handles the task of freeing memory for you.

Take an example of Python

```
l = list(range(100))
del l  # This does not free memory. It only unbind the local variable.
So what does that mean is memory leaking? 
Here GC comes into picture which free the memory automatically.
```

##### How python GC works-
```
import sys
dir(sys)
['__breakpointhook__', '__displayhook__', '__doc__', '__excepthook__', '__interactivehook__', '__loader__', '__name__', 
'__package__', '__spec__', '__stderr__', '__stdin__', '__stdout__', '__unraisablehook__', '_base_executable', 
'_clear_type_cache', '_current_frames', '_debugmallocstats', '_framework', '_getframe', '_git', '_home', '_xoptions', 
'abiflags', 'addaudithook', 'api_version', 'argv', 'audit', 'base_exec_prefix', 'base_prefix', 'breakpointhook', 
'builtin_module_names', 'byteorder', 'call_tracing', 'callstats', 'copyright', 'displayhook', 'dont_write_bytecode', 
'exc_info', 'excepthook', 'exec_prefix', 'executable', 'exit', 'flags', 'float_info', 'float_repr_style', 
'get_asyncgen_hooks', 'get_coroutine_origin_tracking_depth', 'getallocatedblocks', 'getcheckinterval', 
'getdefaultencoding', 'getdlopenflags', 'getfilesystemencodeerrors', 'getfilesystemencoding', 'getprofile', 
'getrecursionlimit', 'getrefcount', 'getsizeof', 'getswitchinterval', 'gettrace', 'hash_info', 'hexversion', 
'implementation', 'int_info', 'intern', 'is_finalizing', 'last_traceback', 'last_type', 'last_value', 'maxsize', 
'maxunicode', 'meta_path', 'modules', 'path', 'path_hooks', 'path_importer_cache', 'platform', 'prefix', 'ps1', 'ps2', 
'pycache_prefix', 'set_asyncgen_hooks', 'set_coroutine_origin_tracking_depth', 'setcheckinterval', 'setdlopenflags', 
'setprofile', 'setrecursionlimit', 'setswitchinterval', 'settrace', 'stderr', 'stdin', 'stdout', 'thread_info', 
'unraisablehook', 'version', 'version_info', 'warnoptions']
``` 

You can see there are lot of modules one of them is `getrefcount`.
```
Let say
import sys 
x = 10
sys.getrefcount(x) # int
```

`getrefcount`:- Store the count of number of variables referring to same memory location.

So what python basically does is -

`For every object ->  keep the count of how many varibales are point to it`

So when ever the count decrease to zero. GC free up the memory.

** This is not the only picture of GC **
- In many cases where count of references will never decrease to zero.
    - e.g. where self reference happens 
        - l = [1,2,3]
        - l.append(l)
- So do other things as well.
    - After every some time. they will go over all variables and see which variable is reachable.
        <br>
        variables -> memory location
        <br>
        memory location -> other memory location
        <br>
        like M -> N -> M (self reference or cyclic reference) # also called connected component in memory graph
    
    - So GC free those memory which are not referenced from the out side of connected components. 
      Means free memory for cyclic references.
    
_So in the first example of GC where pause was happening while printing numbers it was happening due to periodically checking of GC._ 


### How is memory managed in python?
- Memory management in Python is handled by the Python Memory Manager.
- The memory allocated by the manager is in form of a private heap space dedicated for Python.
- All Python objects are stored in this heap and being private, it is inaccessible to the programmer.
- Though, python does provide some core API functions to work upon the private heap space.
- Additionally, Python has an in-built garbage collection to recycle the unused memory for the private heap space.

### What are Python namespaces? Why are they used?
coming soon