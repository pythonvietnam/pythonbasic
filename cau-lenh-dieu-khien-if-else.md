# Câu lệnh điều khiển If else

Cấu trúc câu lệnh điều khiển như sau:

```text
If statement

The syntax looks like

if expression:
    do this
```

Ví dụ: Viết chương trình kiểm tra số nhỏ (lớn) hơn 100
Code tham khảo
```text
#!/usr/bin/env python
number = int(raw_input("Enter a number: "))
if number < 100:
    print "The number is less than 100"
```

Kết quả:

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

Kết quả :

```text
$ ./number100.py
Enter a number: 345
The number is greater than 100
```

Ví dụ về cách sử dụng elif

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

Chúc các bạn thành công !
