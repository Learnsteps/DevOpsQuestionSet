**Tell about threading in python**

Python is single threaded. Even if you use multi thread in python it will only execute one thread at a time. This happens because of a component called GIL or global interpreter lock. It is used to make python thread safe. If you want to run parallel code use multiprocessing. 


**Which one is better in case of IO bound processes, multithreading or multiprocessing?**

Multithreading will work fine in this case as in the IO process the CPU doesn’t do a lot of work but waits for IO to complete. 


**What do you mean by GIL?**

Global Interpreter lock is used to synchronise processes in python and doesn’t allow multiple pieces of code to execute at the same time. 


**What are decorators in python?**

Decorators are types of functions which can be used to wrap other functions. With wrapper you can modify the argument, their order and the functionality. We can also assume it like oregano and chilli flakes we put in pizza. The oregano and chilli flakes are the decorator in pizza.  


**What are iterators in python?**

Iterators in python are a type of python which helps in iterating over any group of objects and can be used with clauses in python. You can get the iter of any object using iter keyword. 
Example: 

```
A = (1,2,3,4,5)
B = iter(A)
print(next(B))
print(next(B))
print(next(B))
```

OUTPUT: 
```
1
2
3
```

**What are generators?**

Generators are simple python functions but instead of return value they use yield statements. So they return an iterator object on which when you can next you get the next data. 
Generators are very useful as they save memory. How? Let us look at an example or generate infinite numbers. This is not possible as there is not enough RAM to save it. But we can accomplish it using generators. Look at the cook sample below. 
```
def loo():
    i=0
    while True:
         yield i
         i=i+1
a=loo()
in a:
    print(i)
```           


You can see that infinite numbers will start printing. So there were infinite numbers in a. But how?  This is what generators do differently. It tries to do lazy processing. It processes things when it is required to return the value at that time. 


**What is comprehension?**

Comprehension in python provides us a way to create sequences using shorthand notations. For example: 
```
[ x*x for x in range(1,100)]
```
This will generate a list with numbers of squares of 1 to 100. 


**Are tuples mutable?**

Tuples are immutable. 


**What is lambda in python?**

Lambda is a first class function in python. It is also known as an anonymous function. They are just like python which don’t need any definitions. They can take any number of arguments. Here is an example of lambda function. 
```
g = lambda x:x*x
print(g(6))
```
This function here is calculating squares of any number passed to it. 


**What is the difference between range and xrange?**

Range function generates the numbers. While Xrange is a generator which generates the numbers when required. Also known as lazy evaluation. 


**How to see all the attributes of any object?**
***dir()***


**What are *args and **kwargs?**

*args is used to pass a variable number of arguments to a function. It's actually the * that allows this capability that this object is iterable. It is used to pass a list of arguments. 
```
Example: 
def fun(*args):
	for i in args:
		print(i)

fun(1,2,3,4,5)
```

**kwargs is used to pass variable number of keyword arguments like below
```
def fun_call(**kwargs):
        for i,j in kwargs.items():
                    print(i,j) 
A = {“var1”:”val1”,“var2”:”val2”,“varn”:”valn”}
fun_call(valn)
```


**What is pickling in python?**

Pickling is used in python to convert any python object in byte stream and unpickling is the reverse of those. In short it is serialization and deserialization of python objects. 


**Do you know what help() does?**

Help function is used in python to get the details of the objects or function that is passed to it. 
Usage: ***help(object)***



