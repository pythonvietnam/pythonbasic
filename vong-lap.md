# Vòng lặp

Trong ví dụ trước, đôi khi nó được yêu cầu làm vài công việc cùng một lúc. Chúng ta sẽ phải thực hiện code nhiều lần cho việc thưc thi. Nói một cách kỹ thuật thì đây là vòng lặp. Trước tiên chúng ta sẽ xem biểu thức Wile cho vòng lặp.

Vòng lặp While

Cú pháp của vòng lặp While như sau:

```text
while condition:
    statement1
    statement2
```

Đoạn code chúng ta muốn chạy sau vòng lặp while phải được thụt đầu dòng. Chúng ta sẽ thực hiện chúng nếu biểu thức là đúng. Chúng ta sẽ viết đoạn code in ra số từ 0 đến 10 như sau:

```text
>>> n = 0
>>> while n < 11:
...     print n
...     n += 1
...
0
1
2
3
4
5
6
7
8
9
10
```

Trong dòng đầu tiên ta khai báo n = 0, sau đó trong biểu thức while khi n &lt; 11, điều đó có nghĩa là chúng sẽ được thực hiện đến khi n &lt; 11. Trong vòng lặp chúng ta in giá trị của n sau đó sắp sếp chúng.

Dãy số Fibonacci Chúng ta sẽ giải bài toán Fibonacci. Chương trình như sau:

```text
#!/usr/bin/env python
a, b = 0, 1
while b < 100:
    print b
    a, b = b, a + b
```

Kết quả như sau:

```text
$ ./fibonacci1.py
1
1
2
3
5
8
13
21
34
55
89
```

Trong dòng đầu tiên của đoạn code chúng ta sẽ gán a và b, sau đó vòng lặp while với b có giá trị nhỏ hơn 100. Trong lặp đầu tiên chúng ta sẽ in ra giá trị b sau đó tiếp theo sẽ in giá trị của b cho a và a +b cho b trong dòng tiếp theo.

```text
#!/usr/bin/env python
a, b = 0, 1
while b < 100:
    print b,
    a, b = b, a + b
```

Kết quả sẽ như sau:

```text
$ ./fibonacci2.py
1 1 2 3 5 8 13 21 34 55 89
```

Power Series

Chúng ta sẽ viết chương trình để tính toán ví dụ: e**x =1+x+x**2/2! +x**3/3! +....+ x**n/n! where 0 &lt; x &lt; 1

```text
#!/usr/bin/env python
x = float(raw_input("Enter the value of x: "))
n = term = num = 1
sum = 1.0
while n <= 100:
    term *= x / n
    sum += term
    n += 1
    if term < 0.0001:
        break
print "No of Times= %d and Sum= %f" % (n, sum)
```

Kết quả như sau:

```text
$ ./powerseries.py
Enter the value of x: 0
No of Times= 2 and Sum= 1.000000
$ ./powerseries.py
Enter the value of x: 0.1
No of Times= 5 and Sum= 1.105171
$ ./powerseries.py
Enter the value of x: 0.5
No of Times= 7 and Sum= 1.648720
```

Trong chương trình chúng ta có một từ khóa mới được gọi là break. Từ khóa sẽ thực hiện dừng khi vòng lặp đang chạy. Ví dụ như sau:

```text
if term < 0.0001:
    break
```

Điều nayfcos nghĩa nếu giá trị của term nhỏ hơn 0.0001 sau đó thoát khỏi vòng lặp.

Phép nhân bảng:

Trong ví dụ sau chúng ta sẽ in ra bảng phéo nhân tới 10

```text
#!/usr/bin/env python
i = 1
print "-" * 50
while i < 11:
    n = 1
    while n <= 10:
        print "%4d" % (i * n),
        n += 1
    print ""
    i += 1
print "-" * 50
```

Kết quả như sau:

```text
$ ./multiplication.py
--------------------------------------------------
   1    2    3    4    5    6    7    8    9   10
   2    4    6    8   10   12   14   16   18   20
   3    6    9   12   15   18   21   24   27   30
   4    8   12   16   20   24   28   32   36   40
   5   10   15   20   25   30   35   40   45   50
   6   12   18   24   30   36   42   48   54   60
   7   14   21   28   35   42   49   56   63   70
   8   16   24   32   40   48   56   64   72   80
   9   18   27   36   45   54   63   72   81   90
  10   20   30   40   50   60   70   80   90  100
--------------------------------------------------
```

Trong hàm print ở trên chúng ta in chuỗi với số lần là n, chuỗi sẽ được xuất hiện n lần. Ví dụ:

```text
>>> print "*" * 10
**********
>>> print "#" * 20
####################
>>> print "--" * 20
----------------------------------------
>>> print "-" * 40
----------------------------------------
```

Some printing \* examples

Here are some examples which you can find very often in college lab reports

Design 1

```text
#!/usr/bin/env python
row = int(raw_input("Enter the number of rows: "))
n = row
while n >= 0:
    x =  "*" * n
    print x
    n -= 1
```

Kết quả như sau

```text
$ ./design1.py
Enter the number of rows: 5
*****
****
***
**
*
```

Design 2

```text
#!/usr/bin/env python
n = int(raw_input("Enter the number of rows: "))
i = 1
while i <= n:
    print "*" * i
    i += 1

The output
```

```text
$ ./design2.py
Enter the number of rows: 5
*
**
***
****
*****
```

Design 3

```text
#!/usr/bin/env python
row = int(raw_input("Enter the number of rows: "))
n = row
while n >= 0:
    x = "*" * n
    y = " " * (row - n)
    print y + x
    n -= 1
```

Kết quả:

```text
$ ./design3.py
Enter the number of rows: 5
*****
 ****
  ***
   **
    *
```

Danh sách

Danh sách là kiểu dữ liệu có cấu trúc.

Chúng ta sẽ tìm hiểu về một kiểu dữ liệu có cấu trúc trước khi chúng ta tìm hiểu thêm về vòng lặp. Danh sách có thể viết như một danh sách các giá trị cách nhau bởi dấu phẩy \(,\) và nằm trong dấu ngoặc vuông.

```text
>>> a = [ 1, 342, 2233423, 'India', 'Fedora']
>>> a
[1, 342, 2233423, 'India', 'Fedora']
```

Danh sách có thể chứa bất cứ dữ liệu nào trong chúng. Nó hoạt động liên tiếp có nghĩa là

```text
>>> a[0]
1
>>> a[4]
'Fedora'
```

Bạn có thể chia chúng thành nhiều phần khác nhau ví dụ:

```text
>>> a[4]
'Fedora'
>>> a[-1]
'Fedora'
>>> a[-2]
'India'
>>> a[0:-1]
[1, 342, 2233423, 'India']
>>> a[2:-2]
[2233423]
>>> a[:-2]
[1, 342, 2233423]
>>> a[0::2]
[1, 2233423, 'Fedora']
```

Trong ví dụ này dấu : đại diện cho khoảng dữ liệu, cụ thể s\[i:j:k\] có nghĩa là giá trị s từ j tới j sau đó đến k. Để kiểm tra nếu giá trị có hoặc tồn tại trong danh sách hoặc không bạn có thể dùng

```text
>>> a = ['Fedora', 'is', 'cool']
>>> 'cool' in a
True
>>> 'Linux' in a
False
```

Điều đó có nghĩa là bạn có thể sử dụng biểu thức như một mệnh đề if. Hàm len\(\) cung cấp cho chúng ta độ dài của danh sách.

```text
>>> len(a)
3
```

Ghi chú

Nếu bạn kiểm tra nếu danh sách rỗng hoặc không, bạn có thể làm như sau:

```text
if list_name: #This means the list is not empty
    pass
else: #This means the list is empty
    pass

For loop
```

Đây cũng là một dạng vòng lặp sử dụng biểu thức. Trong Python biểu thức có cách làm việc khác với trong C. Ví dụ

```text
>>> a = ['Fedora', 'is', 'powerfull']
>>> for x in a:
...     print x,
...
Fedora is powerfull
```

Chúng ta cũng có thể dùng như sau:

```text
>>> a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> for x in a[::2]:
...     print x
...
1
3
5
7
9
```

Hàm range\(\)

Là một hàm được cung cấp sẵn trong Python ví dụ

range\(...\) range\(\[start,\] stop\[, step\]\) -&gt; danh sách số nguyên

Trả về danh sách các số nguyên. range\(i, j\) trả về \[i, i+1, i+2, ..., j-1\]; bắt đầu \(!\) được gán mặc định là 0.

Ở bước đưa ra, nó chỉ định tăng dần hoặc giảm dần. Ví dụ, range\(4\) sẽ trả về giá trị \[0, 1, 2, 3\]. Điểm cuối cùng được bỏ qua. Đây là các giá trị chính xác của danh sách gồm 4 phần tử.

Giờ nếu chúng ta muốn nhìn thấy thông điệp giữ đỡ của hệ thống bạn có thể sử dụng lệnh help\(range\) trong trình thông dịch Python, lệnh help\(s\) sẽ trả về dòng hướng dẫn trong một object s. Ví dụ với hàm range

```text
>>> range(1, 5)
[1, 2, 3, 4]
>>> range(1, 15, 3)
[1, 4, 7, 10, 13]
>>> range(10)
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

Continue statement Nếu như chúng ta có lệnh dừng biểu thức break, thì cũng sẽ có continue, cái mà sẽ bỏ qua việc thực thi đoạn code và quay trở lại điểm xuất phát của vòng lặp. Điều đó có nghĩa nó sẽ giúp bạn bỏ qua một phần vòng lặp. Trong ví dụ dưới đây chúng ta sẽ thực hiện lại.

```text
#!/usr/bin/env python
while True:
    n = int(raw_input("Please enter an Integer: "))
    if n < 0:
        continue #this will take the execution back to the starting of the loop
    elif n == 0:
        break
    print "Square is ", n ** 2
print "Goodbye"
```

Kết quả là

```text
$ ./continue.py
Please enter an Integer: 34
Square is 1156
Please enter an Integer: 4
Square is 16
Please enter an Integer: -9
Please enter an Integer: 0
Goodbye
```

Vòng lặp Else

Chúng ta có tùy chọn else của biểu thức sau bất cứ vòng lặp nào. Nó sẽ được thực hiện sau khi vòng lặp dừng lại.

```text
>>> for i in range(0, 5):
...     print i
... else:
...     print "Bye bye"
...
0
1
2
3
4
Bye bye
```

Game of sticks

```text
#!/usr/bin/env python
sticks = 21

print "There are 21 sticks, you can take 1-4 number of sticks at a time."
print "Whoever will take the last stick will loose"

while True:
    print "Sticks left: " , sticks
    sticks_taken = int(raw_input("Take sticks(1-4):"))
    if sticks == 1:
        print "You took the last stick, you loose"
        break
    if sticks_taken >= 5 or sticks_taken <= 0:
        print "Wrong choice"
        continue
    print "Computer took: " , (5 - sticks_taken) , "n\n"
    sticks -= 5
```

