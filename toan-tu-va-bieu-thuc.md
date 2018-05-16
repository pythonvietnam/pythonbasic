# Toán tử và biểu thức

Trong Python bạn có thể viết biểu thức trên các dòng.

Ví dụ:

```text
>>> 2 + 3
5
>>> 23 - 3
20
>>> 22.0 / 12
1.8333333333333333
```

Để lấy giá trị thập phân bạn thực hiện như trên. Để lấy giá trị làm trong bạn sử dụng toán tử %

```text
>>> 14 % 3
2
```

Ví dụ về số nguyên

```text
#!/usr/bin/env python
days = int(raw_input("Enter days: "))
months = days / 30
days = days % 30
print "Months = %d Days = %d" % (months, days)
```

Kết quả như sau:

```text
$ ./integer.py
Enter days: 265
Months = 8 Days = 25
```

Trong dòng đầu tiên chúng ta sẽ lấy số ngày, sau đó lấy số tháng và ngày và cuối cùng là in chúng ra màn hình. Bạn có thể làm chúng một cách dễ dàng.

```text
#!/usr/bin/env python
days = int(raw_input("Enter days: "))
print "Months = %d Days = %d" % (divmod(days, 30))
```

Hàm divmod\(num1, num2\) trả về hai giá trị , first is the division of num1 and num2 and in second the modulo of num1 and num2.

Relational Operators

You can use the following operators as relational operators Relational Operators Operator Meaning

&lt; Is less than &lt;= Is less than or equal to

> Is greater than = Is greater than or equal to == Is equal to != Is not equal to

```text
Ví dụ:

>>> 1 < 2
True
>>> 3 > 34
False
>>> 23 == 45
False
>>> 34 != 323
True

//

>>> 4.0 // 3
1.0
>>> 4.0 / 3
1.3333333333333333
```

Logical Operators

To do logical AND , OR we use and ,or keywords. x and y returns False if x is False else it returns evaluation of y. If x is True, it returns True.

```text
>>> 1 and 4
4
>>> 1 or 4
1
>>> -1 or 4
-1
>>> 0 or 4
4
```

Shorthand Operator

x op = expression is the syntax for shorthand operators. It will be evaluated like x = x op expression , Few examples are

```text
>>> a = 12
>>> a += 13
>>> a
25
>>> a /= 3
>>> a
8
>>> a += (26 * 32)
>>> a
840
```

```text
shorthand.py example

#!/usr/bin/env python
N = 100
a = 2
while a < N:
    print "%d" % a
    a *= a
```

The output

```text
$ ./shorthand.py
2
4
16
```

Expressions

Generally while writing expressions we put spaces before and after every operator so that the code becomes clearer to read, like

```text
a = 234 * (45 - 56.0 / 34)
```

One example code used to show expressions

```text
#!/usr/bin/env python
a = 9
b = 12
c = 3
x = a - b / 3 + c * 2 - 1
y = a - b / (3 + c) * (2 - 1)
z = a - (b / (3 + c) * 2) - 1
print "X = ", x
print "Y = ", y
print "Z = ", z
```

The output

```text
$ ./evaluationexp.py
X =  10
Y =  7
Z =  4
```

At first x is being calculated. The steps are like this

```text
9 - 12 / 3 + 3 * 2 -1
9 - 4 + 3 * 2 - 1
9 - 4 + 6 - 1
5 + 6 - 1
11 - 1
10
```

Now for y and z we have parentheses, so the expressions evaluated in different way. Do the calculation yourself to check them.

Chuyển đổi kiểu

Chúng ta có thể thưc hiện chuyển đổi thủ công. Ví dụ như:

```text
float(string) -> float value
int(string) -> integer value
str(integer) or str(float) -> string representation
>>> a = 8.126768
>>> str(a)
'8.126768'

evaluateequ.py
```

Sau đây là chương trình tính toán giá trị của dãy số 1/x+1/\(x+1\)+1/\(x+2\)+ ... +1/n với n tăng dần, trong trường hợp x = 1 và n =10

```text
#!/usr/bin/env python
sum = 0.0
for i in range(1, 11):
    sum += 1.0 / i
print "%2d %6.4f" % (i , sum)
```

Kết quả như sau:

```text
$ ./evaluateequ.py
1 1.0000
2 1.5000
3 1.8333
4 2.0833
5 2.2833
6 2.4500
7 2.5929
8 2.7179
9 2.8290
10 2.9290
```

Dòng code sum += 1.0 / i nó có nghĩa là sum = sum + 1.0 / i.

quadraticequation.py

Sau đây là chương trình giải phương trình bậc 2

```text
#!/usr/bin/env python
import math
a = int(raw_input("Enter value of a: "))
b = int(raw_input("Enter value of b: "))
c = int(raw_input("Enter value of c: "))
d = b * b - 4 * a * c
if d < 0:
    print "ROOTS are imaginary"
else:
    root1 = (-b + math.sqrt(d)) / (2.0 * a)
    root2 = (-b - math.sqrt(d)) / (2.0 * a)
    print "Root 1 = ", root1
    print "Root 2 = ", root2

salesmansalary.py
```

Trong ví dụ này chúng ta sẽ thực hiện tính toán lương của một nhân viên kinh doanh camera. Lương cơ bản là 1500, với mỗi một camera bán được anh ấy sẽ có 200 và hoa hồng của nhân viên kinh doanh là 2%. Đầu vào là số camera và tổng số giá của camera.

```text
#!/usr/bin/env python
basic_salary = 1500
bonus_rate = 200
commision_rate = 0.02
numberofcamera = int(raw_input("Enter the number of inputs sold: "))
price = float(raw_input("Enter the total prices: "))
bonus = (bonus_rate * numberofcamera)
commision = (commision_rate * numberofcamera * price)
print "Bonus        = %6.2f" % bonus
print "Commision    = %6.2f" % commision
print "Gross salary = %6.2f" % (basic_salary + bonus + commision)
```

Kết quả như sau:

```text
$ ./salesmansalary.py
Enter the number of inputs sold: 5
Enter the total prices: 20450
Bonus        = 1000.00
Commision    = 2045.00
Gross salary = 4545.00
```

