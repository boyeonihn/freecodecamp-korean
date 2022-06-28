# Python에서 빈 리스트 만드는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![파이썬 로고와 영문으로 빈 리스트라고 적혀 있는 배너](https://www.freecodecamp.org/news/content/images/size/w2000/2020/06/Empty-list.png)

영어 원문: [Python Empty List Tutorial – How to Create an Empty List in Python](https://www.freecodecamp.org/news/python-empty-list-tutorial-how-to-create-an-empty-list-in-python/)   
원문 글쓴이: [Estefania Cassingena Navone](https://www.freecodecamp.org/news/author/estefaniacn/)


### Python에서 빈 리스트 생성하는 방법을 알고 싶으시면 이 기사를 계속 읽어보시길 바랍니다. 

이 기사에서는 다음 내용을 배울 수 있습니다: 
- 대괄호 `[]`를 사용해 빈 리스트를 만드는 방법
- `list()` 함수를 사용해 빈 리스트를 만드는 방법
- 두 방법의 사용 사례 
- `timeit` 모듈을 통해 어떤 방법이 더 효율적이고 실행 속도가 빠른지    

<strong>그럼 시작하겠습니다.</strong> ✨    

## 🔹 대괄호 `[]`를 사용하는 방법 

다음과 같이 빈 대괄호 `[]` 쌍을 사용해 빈 리스트를 만들 수 있습니다.


![변수가 빈 리스트를 표현하는 대괄호 한 쌍을 가르킵니다](https://www.freecodecamp.org/news/content/images/2020/06/image-131.png)

💡 <strong>팁</strong>: 이후 프로그램에 사용할 수 있게 빈 리스트를 변수에 저장합니다.    

예를 들어: 

```
num = [] 
```

빈 리스트의 길이는 다음과 같이 0입니다:    

```
>>> num = []
>>> len(num)
0
```

빈 리스트는 거짓같은 값입니다. 즉, 불리언 문맥에서 false로 평가됩니다. 


```
>>> num = []
>>> bool(num)
False

```

### 빈 리스트에 요소 추가하는 방법 

`append()`와 `insert()` 메서드를 사용해 빈 리스트에 요소를 추가할 수 있습니다: 

- `append()`는 리스트 맨 끝에 요소를 추가합니다.
- `insert()`는 선택한 리스트의 특정 인덱스에 요소를 추가합니다.    

리스트는 비어 있는지 여부에 따라 참 같은 또는 거짓같은 값으로 평가될 수 있어서 다음과 같이 조건문에 사용할 수 있습니다.


```
if num:
	print("이 리스트는 비어 있지 않습니다")
else:
	print("이 리스트는 비어 있습니다")
```

이 코드 블록이 출력하는 값은 다음과 같습니다:

```
이 리스트는 비어 있습니다
```

리스트가 비어 있기 때문에 `False`로 평가됩니다.    


일반적으로: 
- 리스트가 비어 있지 않다면 `True`로 평가되어서 `if`문이 실행됩니다. 
- 리스트가 비어 있다면 `False`로 평가되어서 `else`문이 실행됩니다.


### 예시: 

In the example below, we create an empty list and assign it to the variable `num`. Then, using a for loop, we add a sequence of elements (integers) to the list that was initially empty:

```
>>> num = []
>>> for i in range(3, 15, 2):
	num.append(i)

```


We check the value of the variable to see if the items were appended successfully and confirm that the list is not empty anymore:  

```
>>> num
[3, 5, 7, 9, 11, 13]
```

💡 Tip: We commonly use append() to add the first element to an empty list, but you can also add this element calling the insert() method with index 0:


```
>>> num = []
>>> num.insert(0, 1.5) # add the float 1.5 at index 0
>>> num
[1.5]
```

## 🔸 Using the list() Constructor
Alternatively, you can create an empty list with the type constructor `list()`, which creates a new list object.

According to the [Python Documentation](https://docs.python.org/3/library/stdtypes.html#list):

> If no argument is given, the constructor creates a new empty list, `[]`.

![var라는 변수에 list() 함수가 저장되었습니다](https://www.freecodecamp.org/news/content/images/2020/06/image-132.png)

💡 Tip: This creates a new list object in memory and since we didn't pass any arguments to `list()`, an empty list will be created.


예를 들어서: 

```
num = list()
```

빈 리스트의 길이는 다음과 같이 0입니다:   

```
>>> num = list()
>>> len(num)
0
```

And it is a <strong>falsy</strong> value when it is empty (it evaluates to `False` in a boolean context):

```
>>> num = list()
>>> bool(num)
False
```

### 예시: 

This is a fully functional list, so we can add elements to it:

```
>>> num = list()
>>> for i in range(3, 15, 2):
	num.append(i)
```

And the result will be a non-empty list, as you can see right here:

```
>>> num
[3, 5, 7, 9, 11, 13]
```

## 🔹 두 방법의 사용 사례 
- We typically use `list()` to create lists from existing iterables such as strings, dictionaries, or tuples.
- You will commonly see square brackets `[]` being used to create empty lists in Python because this syntax is more concise and faster.


## 🔸 Efficiency
Wait! I just told you that `[]` is faster than `list()`...

But how much faster?

Let's check their time efficiencies using the [timeit](https://docs.python.org/3/library/timeit.html#module-timeit) module.

To use this module in your Python program, you need to import it:

```
>>> import timeit
```

Specifically, we will use the [timeit function](https://docs.python.org/3/library/timeit.html#timeit.timeit) from this module, which you can call with this syntax:

![timeit 모듈의 timeit 함수를 활용한 코드](https://www.freecodecamp.org/news/content/images/2020/06/image-129.png)

💡 <strong>Tip</strong>: The code is repeated several times to reduce time differences that may arise from external factors such as other processes that might be running at that particular moment. This makes the results more reliable for comparison purposes.

🚦 <strong>On your marks... get set... ready!</strong> Here is the code and output:

First, we import the module.

```
>>> import timeit
```

Then, we start testing each syntax.

### Testing `[]`:
```
>>> timeit.timeit('[]', number=10**4)
0.0008467000000109692
```


### Testing `list()`:
```
>>> timeit.timeit('list()', number=10**4)
0.002867799999989984
```

💡 <strong>Tip</strong>: Notice that the code that you want to time has to be surrounded by single quotes `''` or double quotes `""`. The time returned by the `timeit` function is expressed in seconds.

Compare these results:    
- `[]`: `0.0008467000000109692`
- `list()`: `0.002867799999989984`


You can see that `[]` is much faster than `list()`. There was a difference of approximately `0.002` seconds in this test:

```
>>> 0.002867799999989984 - 0.0008467000000109692
0.0020210999999790147
```

<strong></strong>
I'm sure that you must be asking this right now: Why is `list()` less efficient than `[]` if they do exactly the same thing?

Well... `list()` is slower because it requires looking up the name of the function, calling it, and then creating the list object in memory. In contrast, `[]` is like a "shortcut" that doesn't require so many intermediate steps to create the list in memory.

This time difference will not affect the performance of your program very much but it's nice to know which one is more efficient and how they work behind the scenes.

## 🔹 In Summary
You can create an empty list using an empty pair of square brackets `[]` or the type constructor `list()`, a built-in function that creates an empty list when no arguments are passed.

Square brackets `[]` are commonly used in Python to create empty lists because it is faster and more concise.


제 글이 도움이 되었기를 바랍니다. 이제 Python 프로젝트에서 빈 리스트를 만들 수 있습니다. 원문 글쓴이의 [온라인 강좌](https://www.udemy.com/user/estefania-cn/)를 구경해보시고, [트위터](https://twitter.com/EstefaniaCassN) 계정도 팔로우 해주세요.

리스트에 대해 더 배우고 싶다면, 아래 기사들을 한 번 읽어보세요:
- [Python List Append – How to Add an Element to an Array, Explained with Examples](https://www.freecodecamp.org/news/python-list-append-how-to-add-an-element-to-an-array-explained-with-examples/)
- [The Python Sort List Array Method – Ascending and Descending Explained with Examples](https://www.freecodecamp.org/news/the-python-sort-list-array-method-ascending-and-descending-explained-with-examples/)
- [Python List Append VS Python List Extend – The Difference Explained with Array Method Examples](https://www.freecodecamp.org/news/python-list-append-vs-python-list-extend/)