# Biến và kiểu dữ liệu

Từ khóa

Sau đây là danh sách các từ khóa của ngôn ngữ, chúng ta không thể sử dụng chúng như một định danh thông thường. Chúng ta phải dùng chính xác các từ sau đây:

```text
and       del      from      not   while
as        elif     global    or    with
assert    else     if        pass  yield
break     except   import    print
class     exec     in        raise
continue  finally  is        return
def       for      lambda    try
```

Trong Python chúng ta không chỉ định một kiểu dữ liệu trong một biến. Tuy nhiên chúng ta có thể viết abc = 1 và abc sẽ trở thành dữ liệu kiểu nguyên. Nếu viết abc = 1.0 thì abc sẽ là kiểu số thực. Sau đây là ví dụ cơ bản về việc gán giá trị cho biến:

```text
>>> a = 13
>>> b = 23
>>> a + b
36
```

Trong ví dụ trên bạn đã hiểu cách khai báo biến trong Python, bạn chỉ cần gõ tên và giá trị của biến. Python có thể thao tác trên chuỗi. Chúng được đặt trong dấu ngoặc đơn hoặc ngoặc kép như:

```text
>>> 'India'
'India'
>>> 'India\'s best'
"India's best"
>>> "Hello World!"
'Hello World!'
```

Nhận dữ liệu từ bàn phím:

Trong Python bạn không cần bước đọc dữ liệu từ bàn phím. Bạn có thể sử dụng hàm raw\_input để thực hiện nhập dữ liệu: Ví dụ như:

```text
raw_input("Xin chao Python Viet Nam")
```

và sẽ trả về chuỗi đầu vào. Chúng ta sẽ thử viết một chương trình đơn giản cho phép đọc số được nhập từ bàn phím sau đó kiểm tra nó lớn hơn 100 hoặc không. Tên chương trình này có tên là testhundred.py:

```text
#!/usr/bin/env python
number = int(raw_input("Enter an integer: "))
if number < 100:
    print "Your number is smaller than 100"
else:
    print "Your number is greater than 100"
```

Kết quả sẽ như sau:

```text
$ ./testhundred.py
Enter an integer: 13
Your number is smaller than 100
$ ./testhundred.py
Enter an integer: 123
Your number is greater than 100
```

Trong chương trình tiếp chúng ta sẽ lấy ví dụ về việc tính toán các khoản đầu tư:

```text
#!/usr/bin/env python
amount = float(raw_input("Enter amount: "))
inrate = float(raw_input("Enter Interest rate: "))
period = int(raw_input("Enter period: "))
value = 0
year = 1
while year <= period:
    value = amount + (inrate * amount)
    print "Year %d Rs. %.2f" % (year, value)
    amount = value
    year = year + 1
```

Kết quả như sau:

```text
$ ./investment.py
Enter amount: 10000
Enter Interest rate: 0.14
Enter period: 5
Year 1 Rs. 11400.00
Year 2 Rs. 12996.00
Year 3 Rs. 14815.44
Year 4 Rs. 16889.60
Year 5 Rs. 19254.15
```

Một vài ví dụ:

Một vài ví dụ về biến và kiểu dữ liệu:

Trung bình của số N

Trong chương trình này chúng ta sẽ tính toán trung bình của số N

```text
#!/usr/bin/env python
N = 10
sum = 0
count = 0
while count < N:
    number = float(raw_input(""))
    sum = sum + number
    count = count + 1
average = float(sum)/N
print "N = %d , Sum = %f" % (N, sum)
print "Average = %f" % average
```

Kết quả như sau

```text
$ ./averagen.py
1
2.3
4.67
1.42
7
3.67
4.08
2.2
4.25
8.21
N = 10 , Sum = 38.800000
Average = 3.880000
```

Chuyển đổi nhiệt độ: Chương trình phục vụ việc chuyển đổi từ độ F sang độ C sử dụng công thức: C=\(F-32\)/1.8

```text
#!/usr/bin/env python
fahrenheit = 0.0
print "Fahrenheit Celsius"
while fahrenheit <= 250:
    celsius = ( fahrenheit - 32.0 ) / 1.8 # Here we calculate the Celsius value
    print "%5.1f %7.2f" % (fahrenheit , celsius)
    fahrenheit = fahrenheit + 25
```

Kết quả như sau:

```text
[kd@kdlappy book]$ ./temperature.py
Fahrenheit Celsius
0.0  -17.78
25.0   -3.89
50.0   10.00
75.0   23.89
100.0   37.78
125.0   51.67
150.0   65.56
175.0   79.44
200.0   93.33
225.0  107.22
250.0  121.11
```

Gán nhiều giá trị cho biến trên một dòng:

Bạn có thể khai báo nhiều giá trị cho nhiều biến trên một dòng, ví dụ như sau:

```text
>>> a , b = 45, 54
>>> a
45
>>> b
54
```

Bạn cũng có thể chuyển đổi giữa hai giá trị rất dễ dàng:

```text
>>> a, b = b , a
>>> a
54
>>> b
45
```

Để hiểu hơn cách làm việc, chúng ta sẽ tìm hiểu về kiểu dữ liệu tuple. Chúng ta sẽ sử dụng dấu phẩy cho việc tạo tuple. Ở bên phải chúng ta sẽ tạo một tuple \( chúng ta gọi chúng là gói tuple\) và phía bên trái chúng ta gọi là tuple giải nén cho một tuple mới.

Dưới đây là một ví dụ:

```text
>>> data = ("Kushal Das", "India", "Python")
>>> name, country, language = data
>>> name
'Kushal Das'
>>> country
'India'
>>> language
'Python'
```

Chúc các bạn thành công!

