# Python에서 문자열과 변수 출력하는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![타자기로 문서 작성하는 사람](https://www.freecodecamp.org/news/content/images/size/w2000/2021/12/denise-jans-_dXkaD3l574-unsplash.jpg)

영어 원문: [Python Print Variable – How to Print a String and Variable](https://www.freecodecamp.org/news/python-print-variable-how-to-print-a-string-and-variable/)   
원문 글쓴이: [Dionysia Lemonaki](https://www.freecodecamp.org/news/author/dionysia/)


### Python은 다기능적이고 유연한 언어이기 때문에 보통 무언가를 프로그래밍할 때 여러 방법이 있습니다.

이 튜토리얼에서는 문자열과 변수를 함께 출력할 수 있는 몇 가지 방법을 살펴보겠습니다. 

그럼 시작하겠습니다.

## Python에서 `print()` 함수를 사용하는 방법

Python에서 무언가를 출력하려면 `print()` 함수를 사용합니다. `print` 키워드 뒤에 일련의 괄호 `()` 한 쌍을 붙입니다.

```
#문자열 출력하는 방법
print("Hello world")

#정수 출력하는 방법 
print(7)

#변수 출력하는 방법 
#변수 자체를 출력하려면 변수 이름만 표기합니다 

fave_language = "Python"
print(fave_language)

#출력된 값

#Hello world
#7
#Python
```

괄호를 생략하면 오류가 발생합니다:

```
print "hello world"

#코드 실행 후 출력된 값:
#File "/Users/dionysialemonaki/python_articles/demo.py", line 1
#    print "hello world"
#    ^^^^^^^^^^^^^^^^^^^
#SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
```

Visual Studio Code에서 [Python 확장 프로그램](https://marketplace.visualstudio.com/items?itemName=ms-python.python)을 다운로드 받고 Python 코드를 작성하면, 해당 코드에 밑줄과 힌트가 표시되어 오류가 발생했다는 것을 알 수 있습니다:

![오류가 발생해서 코드가 밑줄이 그어져있고 힌트가 표시됩니다](https://www.freecodecamp.org/news/content/images/2021/12/Screenshot-2021-12-07-at-3.08.14-PM.png)

위에 언급했던 것처럼, `print()` 함수는 모든 종류의 정보를 출력하는 데 사용됩니다. 여기에는 텍스트 및 숫자 데이터, 변수 및 기타 데이터 유형이 포함됩니다.    

변수와 결합된 텍스트(또는 문자열)를 한 번에 출력할 수도 있습니다.

You'll see some of the different ways to do this in the sections that follow.

## How to print a variable and a string in Python using concatenation

To concatenate, according to the dictionary, means to link (things) together in a chain or series.

You do this by adding various things (in this case programming – you add data) together with one another, using the Python addition operator, `+`.

Keep in mind that concatenation is only used for strings, so if the variable you want to concatenate with the rest of the strings is of an integer data type, you'll have to convert it to a string with the `str()` function.

In the following example, I want to print the value of a variable along with some other text.

I add the strings in double quotes and the variable name without any surrounding it, using the addition operator to chain them all together:

```
fave_language = "Python"

print("I like coding in " + fave_language + " the most")

#output
#I like coding in Python the most

```
With string concatenation, you have to add spaces by yourself, so if in the previous example I hadn't included any spaces within the quotation marks the output would look like this:

```
fave_language = "Python"

print("I like coding in" + fave_language + "the most")

#output
#I like coding inPythonthe most
```

You can even add the spaces separately:

```
fave_language = "Python"

print("I like coding in" + " " + fave_language + " "  + "the most")

#output
#I like coding in Python the most
```

This is not the most preferred way of printing strings and variables, as it can be error prone and time-consuming.


## How to print a variable and a string in Python by separating each with a comma
You can print text alongside a variable, separated by commas, in one print statement.

```
first_name = "John"

print("Hello",first_name)

#output
#Hello John

```

In the example above, I first included some text I wanted to print in double quotation marks – in this case, the text was the string `Hello`.

After the closing quotation mark, I added a comma which separates that piece of text from the value held in the variable name (`first_name` in this case) that I then included.

I could have added more text following the variable, like so:

```
first_name = "John"

print("Hello",first_name,"good to see you")

#output
#Hello John good to see you

```

This method also works with more than one variable:

```
first_name = "John"
last_name = "Doe"

print("Hello",first_name,last_name,"good to see you")

#output
Hello John Doe good to see you
```

Make sure to separate everything with a comma.

So, you separate text from variables with a comma, but also variables from other variables, like shown above.

If the comma hadn't been added between `first_name` and `last_name`, the code would've thrown an error:

```
first_name = "John"
last_name = "Doe"

print("Hello",first_name last_name,"good to see you")

#output
#File "/Users/dionysialemonaki/python_articles/demo.py", line 4
#    print("Hello",first_name last_name,"good to see you")
#                 ^^^^^^^^^^^^^^^^^^^^
#SyntaxError: invalid syntax. Perhaps you forgot a comma?
```
As you see, Python error messages are extremely helpful and make the debugging process a bit easier :)

## How to print a variable and a string in Python using string formatting

You use string formatting by including a set of opening and closing curly braces, `{}`, in the place where you want to add the value of a variable.

```
first_name = "John"

print("Hello {}, hope you're well!")
```

In this example there is one variable, `first_name`.

Inside the print statement there is a set of opening and closing double quotation marks with the text that needs to be printed.

Inside that, I've added a set of curly braces in the place where I want to add the value of the variable `first_name`.

If I try and run this code, it will have the following output:

```
#output
#Hello {}, hope you're well!
```

It doesn't actually print the value of `first_name`!

To print it, I need to add the `.format()` string method at the end of the string – that is immediately after the closing quotation mark:

```
first_name = "John"

print("Hello {}, hope you're well!".format(first_name))

#output
#Hello John, hope you're well!
```

When there is more than one variable, you use as many curly braces as the number of variables you want to print:

```
first_name = "John"
last_name = "Doe"

print("Hello {} {}, hope you're well!")
```

In this example, I've created two variables and I want to print both, one after the other, so I added two sets of curly braces in the place where I want the variables to be substituted.

Now, when it comes to the `.format()` method, the order in which you place the variable names inside matters.

So, the value of the variable name that will be added first in the method will be in the place of the first curly brace, the value of the variable name that will be added second will be in the place of the second curly brace, and so on.

Make sure to separate the variable names by commas inside the method:

```
first_name = "John"
last_name = "Doe"

print("Hello {} {}, hope you're well!".format(first_name,last_name))

#output
#Hello John Doe, hope you're well!
```


If I'd reversed the order of the names inside the method, the output would look different:

```
first_name = "John"
last_name = "Doe"

print("Hello {} {}, hope you're well!".format(last_name,first_name))

#output
#Hello Doe John, hope you're well!
```

## How to print a variable and a string in Python using `f-strings`
`f-strings` are a better and more readable and concise way of achieving string formatting compared to the method we saw in the previous section.

The syntax is easier and requires less manual work.

The general syntax for creating an `f-string` looks like this:

```
print(f"I want this text printed to the console!")

#output
#I want this text printed to the console!
```


You first include the character `f` before the opening and closing quotation marks, inside the `print()` function.

To print a variable with a string in one line, you again include the character `f` in the same place – right before the quotation marks.

Then you add the text you want inside the quotation marks, and in the place where you want to add the value of a variable, you add a set of curly braces with the variable name inside them:

```
first_name = "John"

print(f"Hello, {first_name}!")

#output
#Hello, John!
```


To print more than variable, you add another set of curly braces with the second variable name:

```
first_name = "John"
last_name = "Doe"

print(f"Hello, {first_name} {last_name}!")

#output
#Hello, John Doe!
```

The order you place the variable names does matter, so make sure you add them according to the output you want.

If I had reversed the order of the names, I'd get the following output:

```
first_name = "John"
last_name = "Doe"

print(f"Hello, {last_name} {first_name}!")

#output
#Hello, Doe John!
```


## 결론 
끝까지 읽어주셔서 감사합니다! 이 튜토리얼에서는 Python에서 문자열과 변수를 한 줄로 함께 출력하는 몇 가지 방법을 배웠습니다.

Python에 대해 더 배우고 싶다면 freeCodeCamp의 [Python 수료증 과정](https://www.freecodecamp.org/learn/scientific-computing-with-python/)을 확인하세요. 

EHLAKWJFELKAWJEFLKJAWEFLKAWJEF 기초부터 시작해서 점차 고급 개념으로 진도를 나가기 때문에 초보자에게 적합합니다. 또한 5개의 프로젝트를 진행하면서 습득한 모든 프로그래밍 지식을 응용할 수 있을 것입니다.

Happy coding!