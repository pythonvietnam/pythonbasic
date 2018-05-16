# Hàm

Trong lập trình chúng ta sẽ có lúc sử dụng một đoạn code lặp đi lặp lại nhiều lần trong chương trình. Hàm sẽ giúp chúng ta thực hiện điều này. Chúng ta có thể viết tất cả những gì chúng ta muốn thực hiện trong hàm sau đó chỉ cần gọi khi sử dụng. Như ở trên chúng ta đã sử dụng các hàm có sẵn như len\(\), divmod\(\).

Định nghĩa hàm

Chúng ta sẽ dùng tư khóa _def_ để thực hiện định nghĩa hàm. Ví dụ như sau:

```text
def functionname(params):
    statement1
    statement2
```

Chúng ta sẽ thử viết một chương trình nhỏ để thực hiện tính tổng của hai số nguyên.

```text
>>> def sum(a, b):
...     return a + b
```

ở dòng thứ hai với giá trị từ bàn phím, chúng ta sẽ trả lại kết quả của a + b. Bạn phải gọi lại nó như sau:

```text
>>> res = sum(234234, 34453546464)
>>> res
34453780698L
```

Trong chương trình về số palindrom ở chương trước, chúng ta hay viết một hàm để kiểm tra chuỗi có phải là palindrome hay không sau đó trả về kết quả True hoặc False

```text
#!/usr/bin/env python
def palindrome(s):
    return s == s[::-1]
if __name__ == '__main__':
    s = raw_input("Enter a string: ")
    if palindrome(s):
        print "Yes, this is  a palindrome"
    else:
        print "Oh no, not a palindrome"
```

Giờ bạn kiểm tra nào.

**Biến cục bộ và biến toàn cục**

Để có thể hiểu thế nào là biến cục bộ và biến toàn cục chúng ta sẽ xem hai ví dụ sau"

```text
#!/usr/bin/env python
def change(b):
    a = 90
    print a
a = 9
print "Before the function call ", a
print "inside change function", change(a)
print "After the function call ", a
```

Kết quả như sau:

```text
$ ./local.py
Before the function call  9
inside change function 90
After the function call  9
```

_Giải thích:_

Chúng ta có thể thấy, đầu tiên chúng ta sẽ gán 9 cho biến a, sau đó sẽ gọi hàm change\(\), trong hàm change\(\) chúng ta sẽ gán giá trị 90 cho a và in ra số a. Sau khi hàm được gọi chúng ta sẽ in ra một lần nữa giá trị của a. Khi chúng ta gán a = 90 trong hàm, nó sẽ tạo một biến mới là biến a, nhưng biến a chỉ có giá trị và thực thi khi hàm được gọi và kết thúc khi hàm thực hiện xong. Ở đây cùng một tên nhưng chúng khác nhau khi ở trong và ngoài hàm.

```text
#!/usr/bin/env python
def change(b):
    global a
    a = 90
    print a
a = 9
print "Before the function call ", a
print "inside change function",
change(a)
print "After the function call ", a
```

Ở ví dụ này chúng ta sẽ định nghĩa biến toàn cục, tuy nhiên khi thay đổi giá trị a trong hàm nó chuyển đổi ra bên ngoài của hàm.

Kết quả ví dụ trên như sau:

```text
>>> 
Before the function call  9
inside change function 90
After the function call  90
>>>
```

Giá trị đối số mặc định

Trong hàm biến có thể có đối số mặc định, điều đó có nghĩa nếu chúng ta không đưa bất kì giá trị nào cho biến thì nó sẽ được gán mặc định.

```text
>>> def test(a , b=-99):
...     if a > b:
...         return True
...     else:
...         return False
```

Ở ví dụ trên chúng ta gán b = -99 trong hàm. Điều đó có nghĩa là giá trị của b sẽ là -99. Và nếu khi truyền giá trị cho biến của hàm nếu không truyền giá trị b thì mặc định sẽ là -99

```text
>>> test(12, 23)
False
>>> test(12)
True

Important
```

Bạn hãy ghi nhớ chúng ta không thể có một đối số với đối sô mặc địn nếu bạn không có một giá trị mặc định trước đó. Ví dụ f\(a, b=90, c\) thì a, b sẽ có giá trị còn c không có giá trị nào.

Và bạn cũng nên chú ý giá trị mặc định chỉ được tính toán một lần, nếu bạn có bất cứ sự thay đổi nào sẽ làm danh sách thay đổi. Hãy xem ví dụ sau:

```text
>>> def f(a, data=[]):
...     data.append(a)
...     return data
...
>>> print f(1)
[1]
>>> print f(2)
[1, 2]
>>> print f(3)
[1, 2, 3]
```

Để tránh điều này Python cung cấp cách cho bạn như sau:

```text
>>> def f(a, data=None):
...     if data is None:
...         data = []
...         data.append(a)
...         return data
...
>>> print f(1)
[1]
>>> print f(2)
[2]
```

Keyword arguments

```text
>>> def func(a, b=5, c=10):
...     print 'a is', a, 'and b is', b, 'and c is', c
...
>>> func(12, 24)
a is 12 and b is 24 and c is 10
>>> func(12, c = 24)
a is 12 and b is 5 and c is 24
>>> func(b=12, c = 24, a = -1)
a is -1 and b is 12 and c is 24
```

Trong ví dụ trên bạn có thể thấy chúng ta sẽ gọi hàm với tên biến, ví dụ như func\(12, c = 24\), bằng cách đó chúng ta sẽ gán 24 cho c và b sẽ lấy giá trị mặc định. Bạn cũng nên chú ý trường hợp như sau:

```text
>>> def func(a, b=13, v):
...     print a, b, v
...
File "<stdin>", line 1
SyntaxError: non-default argument follows default argument
```

Docstrings

Trong Python chúng ta sử dụng docstrings để giải thích sử dụng code như thế nào, nó sẽ hữu ích trong trình thông dịch và tạo tài liệu tự động. Dưới đây là ví dụ về docstring

```text
#!/usr/bin/env python
import math

def longest_side(a, b):
    """
    Function to find the length of the longest side of a right triangle.

    :arg a: Side a of the triangle
    :arg b: Side b of the triangle

    :return: Length of the longest side c as float
    """
    return math.sqrt(a*a + b*b)

if __name__ == '__main__':
    print longest_side(4, 5)
```

Chúng ta sẽ tìm hiểu thêm về docstrings trong chương sau.

**Hàm bậc cao** Hàm bậc cao hay là functor là hàm có các chức năng sau:

```text
    Takes one or more functions as argument.
    Returns another function as output.
```

Ví dụ:

```text
>>> def high(func, value):
...     return func(value)
...
>>> lst = high(dir, int)
>>> print lst[-3:]
['imag', 'numerator', 'real']
>>> print lst
```

map function

map rất hữu dụng trong hàm bậc cao trong Python.

Ví dụ:

```text
>>> lst = [1, 2, 3, 4, 5]
>>> def square(num):
...     "Returns the square of a given number."
...     return num * num
...
>>> print map(square, lst)
[1, 4, 9, 16, 25]
```

Chúc các bạn thành công!

