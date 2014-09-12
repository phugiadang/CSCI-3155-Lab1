# Lab 1

Include your writeup for the Lab 1 questions here. Use correct
Markdown markup. For more details, start with the article
https://help.github.com/articles/github-flavored-markdown

>:1)Scala basics: Blinding and scope
>a) Consider the following Scala code.
>1 val pi = 3.14
>2 def circumference(r: Double): Double = {
>3 val pi = 3.14159
>4 2.0 * pi * r
>5 }
>6 def area(r: Double): Double =
>7 pi * r * r
>The use of pi at line 4 is bound at which line? The use of pi at line 7 is bound at which
line?
>_Answer:_
>The use of pi in line 4 is bound at line 3, since pi was redefined inside function circumference.
>The use of pi in line 7 is bound at line 1. Since pi in this line is out of the function circumference, 
it will take the value of the global variable pi in line 1.

>b)Consider the following Scala code.
>1 val x = 3
>2 def f(x: Int): Int =
>3 x match {
>4 case 0 => 0
>5 case x => {
>6 val y = x + 1
>7 ({
>8 val x = y + 1
>9 y
>10 } * f(x - 1))
>11 }
>12 }
>13 val y = x + f(x)
>The use of x at line 3 is bound at which line? The use of x at line 6 is bound at which
line? The use of x at line 10 is bound at which line? The use of x at line 13 is bound at
which line?
>_Answer:_
>The use of x at line 3 is bound at line 2, since x is a parameter of function f(x) in line 2.
>The use of x at line 6 is bound at line 2, since x is still inside the function f(x) in this line.
>The use of x at line 10 is bound at line 2, since x is still inside the function f(x) in this line 
and we call the recursive function at this line.
>The use of x at line 13 is bound at line 1. Since pi in this line is out of the function f(x), 
it will take the value of the global variable x in line 1.

>:2) Scala Basics: Typing. In the following, I have left off the return type of function g. The body
of g is well-typed if we can come up with a valid return type. Is the body of g well-typed?
>1 def g(x: Int) = {
>2 val (a, b) = (1, (x, 3))
>3 if (x == 0) (b, 1) else (b, a + 2)
>4 }
>_Answer:_
>Yes, the body of g is well-typed. g will return ((Int,Int),Int). a is type Int and b is the tuples of (Int,Int)
>(b,1):((Int,Int),Int) and (b,a+2):((Int,Int),Int) because
>>(a,b)=(1,(x,3)):(Int,(Int,Int)) because
>>>1:Int
>>>x:Int
>>>3:Int
