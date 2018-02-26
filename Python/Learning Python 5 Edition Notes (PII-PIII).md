# Learning Python 5 Edition (Notes)
------------------------------------------------------------------------------------------------------------------------

## Part II

### Chapter 4. Introducing Python Object Types

#### The Python Conceptual Hierarchy
1. Programs are composed of modules.
2. Modules contain statements.
3. Statements contain expressions.
4. Expressions create and process objects.

#### Python's Core Data Types
| Object type                  | Example literals/creation                |
| ---------------------------- | ---------------------------------------- |
| Numbers                      | 1234, 3.1415, 3+4j, 0b111, Decimal(), Fraction() |
| Strings                      | 'spam', "Bob's", b'a\x01c', u'sp\xc4m'   |
| Lists                        | [1, [2, 'three'], 4.5], list(range(10))  |
| Dictionaries                 | {'food': 'spam', 'taste': 'yum'}, dict(hours=10) |
| Tuples                       | (1, 'spam', 4, 'U'), tuple('spam'), namedtuple |
| Files                        | open('eggs.txt'), open(r'C:\ham.bin', 'wb') |
| Sets                         | set('abc'), {'a', 'b', 'c'}              |
| Other core types             | Booleans, types, None                    |
| Program unit types           | Functions, modules, classes (Part IV, Part V, Part VI) |
| Implementation-related types | Compiled code, stack tracebacks (Part IV, Part VII) |

### Chapter 5. Numeric Types

#### Python expression operators and precedence
| Operators                    | Description                              |
| ---------------------------- | ---------------------------------------- |
| yield x                      | Generator function send protocol         |
| lambda args: expression      | Anonymous function generation            |
| x if y else z                | Ternary selection (x is evaluated only if y is true) |
| x or y                       | Logical OR (y is evaluated only if x is false) |
| x and y                      | Logical AND (y is evaluated only if x is true) |
| not x                        | Logical negation                         |
| x in y, x not in y           | Membership (iterables, sets)             |
| x is y, x is not y           | Object identity tests                    |
| x < y, x <= y, x > y, x >= y | Magnitude comparison, set subset and superset; |
| x == y, x != y               | Value equality operators                 |
| x                            | y                                        |
| x ^ y                        | Bitwise XOR, set symmetric difference    |
| x & y                        | Bitwise AND, set intersection            |
| x << y, x >> y               | Shift x left or right by y bits          |
| x + y                        | Addition, concatenation;                 |
| x – y                        | Subtraction, set difference              |
| x * y                        | Multiplication, repetition;              |
| x % y                        | Remainder, format;                       |
| x / y, x // y                | Division: true and floor                 |
| −x, +x                       | Negation, identity                       |
| ˜x                           | Bitwise NOT (inversion)                  |
| x ** y                       | Power (exponentiation)                   |
| x[i]                         | Indexing (sequence, mapping, others)     |
| x[i:j:k]                     | Slicing                                  |
| x(...)                       | Call (function, method, class, other callable) |
| x.attr                       | Attribute reference                      |
| (...)                        | Tuple, expression, generator expression  |
| [...]                        | List, list comprehension                 |
| {...}                        | Dictionary, set, set and dictionary comprehensions |

#### Variables and Basic Expressions
* Variables are created when they are first assigned values.
* Variables are replaced with their values when used in expressions.
* Variables must be assigned before they can be used in expressions.
* Variables refer to objects and are never declared ahead of time.

#### Chapter Summary
>This chapter has taken a tour of Python’s numeric object types and the operations we
>can apply to them. Along the way, we met the standard integer and floating-point types,
>as well as some more exotic and less commonly used types such as complex numbers,
>decimals, fractions, and sets. We also explored Python’s expression syntax, type conversions,
>bitwise operations, and various literal forms for coding numbers in scripts.




### Chapter 7. String Fundamentals

#### Common string literals and operations
| Operation                   | Interpretation                           |
| --------------------------- | ---------------------------------------- |
| S = ''                      | Empty string                             |
| S = "spam's"                | Double quotes, same as single            |
| S = 's\np\ta\x00m'          | Escape sequences                         |
| S = """...multiline..."""   | Triple-quoted block strings              |
| S = r'\temp\spam'           | Raw strings (no escapes)                 |
| B = b'sp\xc4m'              | Byte strings in 2.6, 2.7, and 3.X (Chapter 4, Chapter 37) |
| U = u'sp\u00c4m'            | Unicode strings in 2.X and 3.3+ (Chapter 4, Chapter 37) |
| S1 + S2                     | Concatenate                              |
| S * 3                       | Repeat                                   |
| S[i]                        | Index                                    |
| S[i:j]                      | Slice                                    |
| len(S)                      | length                                   |
| "a %s parrot" % kind        | String formatting expression             |
| "a {0} parrot".format(kind) | String formatting method in 2.6, 2.7, and 3.X |
| S.find('pa')                | String methods (see ahead for all 43): search, |
| S.rstrip()                  | remove whitespace,                       |
| S.replace('pa', 'xx')       | replacement,                             |
| S.split(',')                | split on delimiter,                      |
| S.isdigit()                 | content test,                            |
| S.lower()                   | case conversion                          |
| S.endswith('spam')          | end test,                                |
| 'spam'.join(strlist)        | delimiter join,                          |
| S.encode('latin-1')         | Unicode encoding,                        |
| B.decode('utf8')            | Unicode decoding, etc. (see Table 7-3)   |
| for x in S: print(x)        | Iteration, membership                    |
| 'spam' in S                 |                                          |
| [c * 2 for c in S]          |                                          |
| map(ord, S)                 |                                          |
| re.match('sp(.*)am', line)  | Pattern matching: library module         |


#### String backslash characters
| Escape     | Meaning                                  |
| ---------- | ---------------------------------------- |
| \newline   | Ignored (continuation line)              |
| \\         | Backslash (stores one \)                 |
| \'         | Single quote (stores ')                  |
| \"         | Double quote (stores ")                  |
| \a         | Bell                                     |
| \b         | Backspace                                |
| \f         | Formfeed                                 |
| \n         | Newline (linefeed)                       |
| \r         | Carriage return                          |
| \t         | Horizontal tab                           |
| \v         | Vertical tab                             |
| \xhh       | Character with hex value hh (exactly 2 digits) |
| \ooo       | Character with octal value ooo (up to 3 digits) |
| \0         | Null: binary 0 character (doesn’t end string) |
| \N{ id }   | Unicode database ID                      |
| \uhhhh     | Unicode character with 16-bit hex value  |
| \Uhhhhhhhh | Unicode character with 32-bit hex valuea |
| \other     | Not an escape (keeps both \ and other)   |

#### String method calls in Python 3.3
| S.capitalize()                       | S.ljust(width [, fill])                |
| ------------------------------------ | -------------------------------------- |
| S.casefold()                         | S.lower()                              |
| S.center(width [, fill])             | S.lstrip([chars])                      |
| S.count(sub [, start [, end]])       | S.maketrans(x[, y[, z]])               |
| S.encode([encoding [,errors]])       | S.partition(sep)                       |
| S.endswith(suffix [, start [, end]]) | S.replace(old, new [, count])          |
| S.expandtabs([tabsize])              | S.rfind(sub [,start [,end]])           |
| S.find(sub [, start [, end]])        | S.rindex(sub [, start [, end]])        |
| S.format(fmtstr, *args, **kwargs)    | S.rjust(width [, fill])                |
| S.index(sub [, start [, end]])       | S.rpartition(sep)                      |
| S.isalnum()                          | S.rsplit([sep[, maxsplit]])            |
| S.isalpha()                          | S.rstrip([chars])                      |
| S.isdecimal()                        | S.split([sep [,maxsplit]])             |
| S.isdigit()                          | S.splitlines([keepends])               |
| S.isidentifier()                     | S.startswith(prefix [, start [, end]]) |
| S.islower()                          | S.strip([chars])                       |
| S.isnumeric()                        | S.swapcase()                           |
| S.isprintable()                      | S.title()                              |
| S.isspace()                          | S.translate(map)                       |
| S.istitle()                          | S.upper()                              |
| S.isupper()                          | S.zfill(width)                         |
| S.join(iterable)                     |                                        |

#### String Formatting Expressions
* String formatting expressions: '...%s...' % (values)
* String formatting method calls: '...{}...'.format(values)

```python
>>> 'That is %d %s bird!' % (1, 'dead') # Format expression
That is 1 dead bird!

>>> exclamation = 'Ni'
>>> 'The knights who say %s!' % exclamation # String substitution
The knights who say Ni!

>>> '%d %s %g you' % (1, 'spam', 4.0) # Type-specific substitutions
1 spam 4 you

>>> '%s -- %s -- %s' % (42, 3.14159, [1, 2, 3]) # All types match a %s target
42 -- 3.14159 -- [1, 2, 3]
```

#### String formatting type codes
| Code | Meaning                                  |
| ---- | ---------------------------------------- |
| s    | String (or any object’s str(X) string)   |
| r    | Same as s, but uses repr, not str        |
| c    | Character (int or str)                   |
| d    | Decimal (base-10 integer)                |
| i    | Integer                                  |
| u    | Same as d (obsolete: no longer unsigned) |
| o    | Octal integer (base 8)                   |
| x    | Hex integer (base 16)                    |
| X    | Same as x, but with uppercase letters    |
| e    | Floating point with exponent, lowercase  |
| E    | Same as e, but uses uppercase letters    |
| f    | Floating-point decimal                   |
| F    | Same as f, but uses uppercase letters    |
| g    | Floating-point e or f                    |
| G    | Floating-point E or F                    |
| %    | Literal % (coded as %%)                  |

#### Chapter Summary
>In this chapter, we took an in-depth tour of the string object type. We learned about
>coding string literals, and we explored string operations, including sequence expressions,
>string method calls, and string formatting with both expressions and method
>calls. Along the way, we studied a variety of concepts in depth, such as slicing, method
>call syntax, and triple-quoted block strings. We also defined some core ideas common
>to a variety of types: sequences, for example, share an entire set of operations.
>In the next chapter, we’ll continue our types tour with a look at the most general object
>collections in Python—lists and dictionaries. As you’ll find, much of what you’ve
>learned here will apply to those types as well. And as mentioned earlier, in the final part
>of this book we’ll return to Python’s string model to flesh out the details of Unicode
>text and binary data, which are of interest to some, but not all, Python programmers.
>Before moving on, though, here’s another chapter quiz to review the material covered
>here.


### Chapter 8. Lists and Dictionaries

####  Common list literals & operation
| Operation                         | Interpretation                           |
| --------------------------------- | ---------------------------------------- |
| L = []                            | An empty list                            |
| L = [123, 'abc', 1.23, {}]        | Four items: indexes 0..3                 |
| L = ['Bob', 40.0, ['dev', 'mgr']] | Nested sublists                          |
| L = list('spam')                  | List of an iterable's items              |
| L = list(range(-4, 4))            | List of successive intergers             |
| L[i]                              | Index                                    |
| L[i][j]                           | Index of index                           |
| L[i:j]                            | slice                                    |
| len(L)                            | length                                   |
| L1 + L2                           | Concatenate                              |
| L * 3                             | repeat                                   |
| for x in L: print(x)              | iteration                                |
| 3 in L                            | membership                               |
| L.append(4)                       | Methord:growing                          |
| L.extend([5,6,7])                 |                                          |
| L.insert(i, X)                    |                                          |
| L.index(X)                        | Methods: searching                       |
| L.count(X)                        |                                          |
| L.sort()                          | Methods: sorting                         |
| L.reverse()                       | Methods: reversing                       |
| L.copy()                          | copying (3.3+)                           |
| L.clear()                         | clearing (3.3+)                          |
| L.pop(i)                          | Methods, statements: shrinking           |
| L.remove(X)                       |                                          |
| del L[i]                          |                                          |
| del L[i:j]                        |                                          |
| L[i:j] = []                       |                                          |
| L[i] = 3                          | Index assignment                         |
| L[i:j] = [4,5,6]                  | slice assignment                         |
| L = [x**2 for x in range(5)]      | List comprehensions and maps (Chapter 4, Chapter 14, Chapter 20) |
| list(map(ord, 'spam'))            |                                          |

#### Dictionaries
| Operation                                | Interpretation                           |
| ---------------------------------------- | ---------------------------------------- |
| D = {}                                   | Empty dictionary                         |
| D = {'name': 'Bob', 'age': 40}           | Two-item dictionary                      |
| E = {'cto': {'name': 'Bob', 'age': 40}}  | Nesting                                  |
| D = dict(name='Bob', age=40)             | Alternative construction techniques:     |
| D = dict([('name', 'Bob'), ('age', 40)]) | keywords, key/value pairs, zipped key/value pairs, key lists |
| D = dict(zip(keyslist, valueslist))      |                                          |
| D = dict.fromkeys(['name', 'age'])       |                                          |
| D['name']                                | Indexing by key                          |
| E['cto']['age']                          |                                          |
| 'age' in D                               | Membership: key present test             |
| D.keys()                                 | Methods: all keys,                       |
| D.values()                               | all values,                              |
| D.items()                                | all key+value tuples,                    |
| D.copy()                                 | copy (top-level),                        |
| D.clear()                                | clear (remove all items),                |
| D.update(D2)                             | merge by keys,                           |
| D.get(key, default?)                     | fetch by key, if absent default (or None), |
| D.pop(key, default?)                     | remove by key, if absent default (or error) |
| D.setdefault(key, default?)              | fetch by key, if absent set default (or None), |
| D.popitem()                              | remove/return any (key, value) pair; etc. |
| len(D)                                   | Length: number of stored entries         |
| D[key] = 42                              | Adding/changing keys                     |
| del D[key]                               | Deleting entries by key                  |
| list(D.keys())                           | Dictionary views (Python 3.X)            |
| D1.keys() & D2.keys()                    |                                          |
| D.viewkeys(), D.viewvalues()             | Dictionary views (Python 2.7)            |
| D = {x: x*2 for x in range(10)}          | Dictionary comprehensions (Python 3.X, 2.7) |


#### Chapter Summary
>In this chapter, we explored the list and dictionary types—probably the two most
>common, flexible, and powerful collection types you will see and use in Python code.
>We learned that the list type supports positionally ordered collections of arbitrary objects, and that it may be freely nested and grown and shrunk on demand. The dictionary
>type is similar, but it stores items by key instead of by position and does not maintain
>any reliable left-to-right order among its items. Both lists and dictionaries are mutable,
>and so support a variety of in-place change operations not available for strings: for
>example, lists can be grown by **append** calls, and dictionaries by assignment to new keys.
>In the next chapter, we will wrap up our in-depth core object type tour by looking at
>tuples and files. After that, we’ll move on to statements that code the logic that processes
>our objects, taking us another step toward writing complete programs. Before we tackle
>those topics, though, here are some chapter quiz questions to review.




### Chapter 9. Tuples, Files, and Everything Else

#### Tuples
The last collection type in our survey is the Python tuple. Tuples construct simple
groups of objects. They work exactly like lists, except that tuples can’t be changed in
place (they’re immutable) and are usually written as a series of items in parentheses,
not square brackets. Although they don’t support as many methods, tuples share most
of their properties with lists. Here’s a quick look at the basics. Tuples are:
* Ordered collections of arbitrary objects
>Like strings and lists, tuples are positionally ordered collections of objects (i.e.,
>they maintain a left-to-right order among their contents); like lists, they can embed
>any kind of object.
* Accessed by offset
>Like strings and lists, items in a tuple are accessed by offset (not by key); they
>support all the offset-based access operations, such as indexing and slicing.
* Of the category “immutable sequence”
>Like strings and lists, tuples are sequences; they support many of the same operations.
>However, like strings, tuples are immutable; they don’t support any of the
>in-place change operations applied to lists.
* Fixed-length, heterogeneous, and arbitrarily nestable
>Because tuples are immutable, you cannot change the size of a tuple without making
>a copy. On the other hand, tuples can hold any type of object, including other
>compound objects (e.g., lists, dictionaries, other tuples), and so support arbitrary
>nesting.
* Arrays of object references
>Like lists, tuples are best thought of as object reference arrays; tuples store access
>points to other objects (references), and indexing a tuple is relatively quick.

#### Tuple literatuals & operations
| Operation                           | Interpretation                           |
| ----------------------------------- | ---------------------------------------- |
| ()                                  | An empty tuple                           |
| T = (0,)                            | A one-item tuple (not an expression)     |
| T = (0, 'Ni', 1.2, 3)               | A four-item tuple                        |
| T = 0, 'Ni', 1.2, 3                 | Another four-item tuple (same as prior line) |
| T = ('Bob', ('dev', 'mgr'))         | Nested tuples                            |
| T = tuple('spam')                   | Tuple of items in an iterable            |
| T[i]                                | Index                                    |
| T[i][j]                             | index of index                           |
| T[i:j]                              | slice                                    |
| len(T)                              | length                                   |
| T1 + T2                             | Concatenate                              |
| T * 3                               | repeat                                   |
| for x in T: print(x)                | iteration                                |
| 'spam' in T                         | membership                               |
| [x ** 2 for x in T]                 |                                          |
| T.index('Ni')                       | Methods in 2.6, 2.7, and 3.X: search, count |
| T.count('Ni')                       |                                          |
| namedtuple('Emp', ['name', 'jobs']) | Named tuple extension type               |

#### Files
You may already be familiar with the notion of files, which are named storage compartments
on your computer that are managed by your operating system. The last major
built-in object type that we’ll examine on our object types tour provides a way to access
those files inside Python programs.
In short, the built-in open function creates a Python file object, which serves as a link
to a file residing on your machine. After calling open, you can transfer strings of data
to and from the associated external file by calling the returned file object’s methods.
Compared to the types you’ve seen so far, file objects are somewhat unusual. They are
considered a core type because they are created by a built-in function, but they’re not
numbers, sequences, or mappings, and they don’t respond to expression operators;
they export only methods for common file-processing tasks. Most file methods are
concerned with performing input from and output to the external file associated with
a file object, but other file methods allow us to seek to a new position in the file, flush
output buffers, and so on. Table 9-2 summarizes common file operations.

#### Common files operations
| Operation                             | Interpretation                           |
| ------------------------------------- | ---------------------------------------- |
| output = open(r'C:\spam', 'w')        | Create output file ('w' means write)     |
| input = open('data', 'r')             | Create input file ('r' means read)       |
| input = open('data')                  | Same as prior line ('r' is the default)  |
| aString = input.read()                | Read entire file into a single string    |
| aString = input.read(N)               | Read up to next N characters (or bytes) into a string |
| aString = input.readline()            | Read next line (including \n newline) into a string |
| aList = input.readlines()             | Read entire file into list of line strings (with \n) |
| output.write(aString)                 | Write a string of characters (or bytes) into file |
| output.writelines(aList)              | Write all line strings in a list into file |
| output.close()                        | Manual close (done for you when file is collected) |
| output.flush()                        | Flush output buffer to disk without closing |
| anyFile.seek(N)                       | Change file position to offset N for next operation |
| for line in open('data'): use line    | File iterators read line by line         |
| open('f.txt', encoding='latin-1')     | Python 3.X Unicode text files (str strings) |
| open('f.bin', 'rb')                   | Python 3.X bytes files (bytes strings)   |
| codecs.open('f.txt', encoding='utf8') | Python 2.X Unicode text files (unicode strings) |
| open('f.bin', 'rb')                   | Python 2.X bytes files (str strings)     |



## Part III

### Chapter 10.Introducing Python Statements

#### Python's statements
| Statement                   | Role                         | Example                                 |
| --------------------------- | ---------------------------- | --------------------------------------- |
| Assignment                  | Creating references          | a, b = 'good', 'bad'                    |
| Calls and other expressions | Running functions            | log.write("spam, ham")                  |
| print calls                 | Printing objects             | print('The Killer', joke)               |
| if/elif/else                | Selecting actions            | if "python" in text: print(text)        |
| for/else                    | Iteration                    | for x in mylist: print(x)               |
| while/else                  | General loops                | while X > Y: print('hello')             |
| pass                        | Empty placeholder            | while True: pass                        |
| break                       | Loop exit                    | while True: if exittest(): break        |
| continue                    | Loop continue                | while True: if skiptest(): continue     |
| def                         | Functions and methods        | def f(a, b, c=1, *d): print(a+b+c+d[0]) |
| return                      | Functions results            | def f(a, b, c=1, *d): return a+b+c+d[0] |
| yield                       | Generator functions          | def gen(n):                             |
|                             |                              | for i in n: yield i*2                   |
| global                      | Namespaces                   | x = 'old'                               |
|                             |                              | def function():                         |
|                             |                              | global x, y; x = 'new'                  |
| nonlocal                    | Namespaces (3.X)             | def outer():                            |
|                             |                              | x = 'old'                               |
|                             |                              | def function():                         |
|                             |                              | nonlocal x; x = 'new'                   |
| import                      | Module access                | import sys                              |
| from                        | Attribute access             | from sys import stdin                   |
| class                       | Building objects             | class Subclass(Superclass):             |
|                             |                              | staticData = []                         |
|                             |                              | def method(self): pass                  |
| try/except/ finally         | Catching exceptions          | try:                                    |
|                             |                              | action()                                |
|                             |                              | except:                                 |
|                             |                              | print('action error')                   |
| raise                       | Triggering exceptions        | raise EndSearch(location)               |
| assert                      | Debugging checks             | assert X > Y, 'X too small'             |
| with/as                     | Context managers (3.X, 2.6+) | with open('data') as myfile:            |
|                             |                              | process(myfile)                         |
| del                         | Deleting references          | del data[k]                             |
|                             |                              | del data[i:j]                           |
|                             |                              | del obj.attr                            |
|                             |                              | del variable                            |

### Chapter 11. Assignments, Expressions, and Prints

#### Assignment Statements
* Assignments create object references.
* Names are created when first assigned.
* Names must be assigned before being referenced.
* Some operations perform assignments implicitly. 

#### Assignment Statement Forms
| Operation                    | Interpretation                           |
| ---------------------------- | ---------------------------------------- |
| spam = 'Spam'                | Basic form                               |
| spam, ham = 'yum', 'YUM'     | Tuple assignment (positional)            |
| [spam, ham] = ['yum', 'YUM'] | List assignment (positional)             |
| a, b, c, d = 'spam'          | Sequence assignment, generalized         |
| a, *b = 'spam'               | Extended sequence unpacking (Python 3.X) |
| spam = ham = 'lunch'         | Multiple-target assignment               |
| spams += 42                  | Augmented assignment (equivalent to spams = spams + 42) |


* Tuple- and list-unpacking assignments
>The second and third forms in the table are related. When you code a tuple or list
>on the left side of the =, Python pairs objects on the right side with targets on the
>left by position and assigns them from left to right. For example, in the second line
>of Table 11-1, the name spam is assigned the string 'yum', and the name ham is bound
>to the string 'YUM'. In this case Python internally may make a tuple of the items on
>the right, which is why this is called tuple-unpacking assignment.

* Sequence assignments
>In later versions of Python, tuple and list assignments were generalized into instances
>of what we now call sequence assignment—any sequence of names can be
>assigned to any sequence of values, and Python assigns the items one at a time by
>position. We can even mix and match the types of the sequences involved. The
>fourth line in Table 11-1, for example, pairs a tuple of names with a string of
>characters: a is assigned 's', b is assigned 'p', and so on.

* Extended sequence unpacking
>In Python 3.X (only), a new form of sequence assignment allows us to be more
>flexible in how we select portions of a sequence to assign. The fifth line in Table
>11-1, for example, matches a with the first character in the string on the right
>and b with the rest: a is assigned 's', and b is assigned 'pam'. This provides a simpler
>alternative to assigning the results of manual slicing operations.

* Multiple-target assignments
>The sixth line in Table 11-1 shows the multiple-target form of assignment. In this
>form, Python assigns a reference to the same object (the object farthest to the right)
>to all the targets on the left. In the table, the names spam and ham are both assigned
>references to the same string object, 'lunch'. The effect is the same as if we had
>coded ham = 'lunch' followed by spam = ham, as ham evaluates to the original string
>object (i.e., not a separate copy of that object).

* Augmented assignments
>The last line in Table 11-1 is an example of augmented assignment—a shorthand
>that combines an expression and an assignment in a concise way. Saying spam +=
>42, for example, has the same effect as spam = spam + 42, but the augmented form
>requires less typing and is generally quicker to run. In addition, if the subject is
>mutable and supports the operation, an augmented assignment may run even
>quicker by choosing an in-place update operation instead of an object copy. There
>is one augmented assignment statement for every binary expression operator in
>Python.

#### Naming conventions
Besides these rules, there is also a set of naming conventions—rules that are not required
but are followed in normal practice. For instance, because names with two leading and
trailing underscores (e.g., __name__) generally have special meaning to the Python interpreter,
you should avoid this pattern for your own names. Here is a list of the conventions
Python follows:
* Names that begin with a single underscore (_X) are not imported by a from module
  import * statement (described in Chapter 23).
* Names that have two leading and trailing underscores (__X__) are system-defined
  names that have special meaning to the interpreter.
* Names that begin with two underscores and do not end with two more (__X) are
  localized (“mangled”) to enclosing classes (see the discussion of pseudoprivate
  attributes in Chapter 31).
* The name that is just a single underscore (_) retains the result of the last expression
  when you are working interactively.

#### Expression Statements
* For calls to functions and methods
>Some functions and methods do their work without returning a value. Such functions
>are sometimes called procedures in other languages. Because they don’t return
>values that you might be interested in retaining, you can call these functions with
>expression statements.

* For printing values at the interactive prompt
>Python echoes back the results of expressions typed at the interactive command
>line. Technically, these are expression statements, too; they serve as a shorthand
>for typing print statements.

#### Common Python expression statements
| Operation              | Interpretation                           |
| ---------------------- | ---------------------------------------- |
| spam(eggs, ham)        | Function calls                           |
| spam.ham(eggs)         | Method calls                             |
| spam                   | Printing variables in the interactive interpreter |
| print(a, b, c, sep='') | Printing operations in Python 3.X        |
| yield x \*\* 2         | Yielding expression statements           |

#### Print Operations
In Python, print prints things—it’s simply a programmer-friendly interface to the standard
output stream.

Technically, printing converts one or more objects to their textual representations, adds
some minor formatting, and sends the resulting text to either standard output or another
file-like stream. In a bit more detail, print is strongly bound up with the notions
of files and streams in Python:
* File object methods
>In Chapter 9, we learned about file object methods that write text (e.g.,
>file.write(str)). Printing operations are similar, but more focused—whereas file
>write methods write strings to arbitrary files, print writes objects to the stdout
>stream by default, with some automatic formatting added. Unlike with file methods,
>there is no need to convert objects to strings when using print operations.

* Standard output stream
>The standard output stream (often known as stdout) is simply a default place to
>send a program’s text output. Along with the standard input and error streams,
>it’s one of three data connections created when your script starts. The standard
>output stream is usually mapped to the window where you started your Python
>program, unless it’s been redirected to a file or pipe in your operating system’s shell.
>Because the standard output stream is available in Python as the stdout file object
>in the built-in sys module (i.e., sys.stdout), it’s possible to emulate print with file
>write method calls. However, print is noticeably easier to use and makes it easy to
>print text to other files and streams.

##### Call format
Syntactically, calls to the 3.X print function have the following form (the flush argument
is new as of Python 3.3):
```
print([object, ...][, sep=' '][, end='\n'][, file=sys.stdout][, flush=False])
```
In this formal notation, items in square brackets are optional and may be omitted in a
given call, and values after = give argument defaults. In English, this built-in function
prints the textual representation of one or more objects separated by the string sep and
followed by the string end to the stream file, flushing buffered output or not per flush.

The sep, end, file, and (in 3.3 and later) flush parts, if present, must be given as keyword
arguments—that is, you must use a special “name=value” syntax to pass the arguments
by name instead of position. Keyword arguments are covered in depth in Chapter 18,
but they’re straightforward to use. The keyword arguments sent to this call may appear
in any left-to-right order following the objects to be printed, and they control the
print operation:
* sep is a string inserted between each object’s text, which defaults to a single space
  if not passed; passing an empty string suppresses separators altogether.
* end is a string added at the end of the printed text, which defaults to a \n newline
  character if not passed. Passing an empty string avoids dropping down to the next
  output line at the end of the printed text—the next print will keep adding to the
  end of the current output line.
* file specifies the file, standard stream, or other file-like object to which the text
  will be sent; it defaults to the sys.stdout standard output stream if not passed. Any
  object with a file-like write(string) method may be passed, but real files should
  be already opened for output.
* flush, added in 3.3, defaults to False. It allows prints to mandate that their text be
  flushed through the output stream immediately to any waiting recipients. Normally,
  whether printed output is buffered in memory or not is determined by
  file; passing a true value to flush forcibly flushes the stream.
  The textual representation of each object to be printed is obtained by passing the object
  to the str built-in call (or its equivalent inside Python); as we’ve seen, this built-in
  returns a “user friendly” display string for any object.5 With no arguments at all, the
  print function simply prints a newline character to the standard output stream, which
  usually displays a blank line.



| Python 2.X statement | Python 3.X equivalent   | Interpretation                           |
| -------------------- | ----------------------- | ---------------------------------------- |
| print x, y           | print(x, y)             | Print objects’ textual forms to sys.stdout; add a space between the items and an end-of-line at the end |
| print x, y,          | print(x, y, end='')     | Same, but don’t add end-of-line at end of text |
| print >> afile, x, y | print(x, y, file=afile) | Send text to afile.write, not to sys.stdout.write |