# Câu lệnh điều khiển If else

Mẫu câu điều khiển như sau:

```text
If statement

The syntax looks like

if expression:
    do this
```

Dưới đây là ví dụ để check một số lớn hơn hoặc nhỏ hơn 100:

```text
#!/usr/bin/env python
number = int(raw_input("Enter a number: "))
if number < 100:
    print "The number is less than 100"
```

Sau đó chạy nó như sau:

```text
$ ./number100.py
Enter a number: 12
The number is less than 100
```

Else

Trong trường hợp muốn in ra số đó lớn hơn 100, trường hợp này chúng ta sử dụng else. Nó sẽ thực hiện khi biểu thức if không hoàn thành.

```text
#!/usr/bin/env python
number = int(raw_input("Enter a number: "))
if number < 100:
    print "The number is less than 100"
else:
    print "The number is greater than 100"
```

Kết quả như sau:

```text
$ ./number100.py
Enter a number: 345
The number is greater than 100
```

Một ví dụ rất đơn giản như sau:

```text
>>> x = int(raw_input("Please enter an integer: "))
>>> if x < 0:
...      x = 0
...      print 'Negative changed to zero'
... elif x == 0:
...      print 'Zero'
... elif x == 1:
...      print 'Single'
... else:
...      print 'More'
```

Kiểm tra giá trị thật

```text
if x:
    pass

Warning

Don’t do this

if x == True:
    pass
```

