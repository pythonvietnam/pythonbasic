# Exceptions

Trong phần này chúng ta sẽ nghiên cứu về exception trong Python và làm sao đề xử lý trong trong code.

Một số lỗi xảy ra trong quá trình chạy chương trình được gọi là exception. Mỗi một exception đều sinh ra một số thông báo lỗi.

NameError

Khi chúng ta bắt đầu viết code, đây sẽ là hầu hết các exceoption mà các bạn có thể tìm thấy. Ví dụ như chúng ta cố gắng truy cập vào biến và nó chưa được khai báo.

```text
>>> print kushal
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'kushal' is not defined
```

Dòng cuối cùng chứa nội dung cụ thể của thông báo lỗi, phần còn lại đưa ra thông báo cụ thể làm thế nào để nó xảy ra \( hoặc những gì gây ra ngoại lệ\).

TypeError

TypeError là một trong các lỗi phổ biến nhất xuất hiện. Nó thường xuất hiện với các chương trình liên quan đến kiểu dữ liệu. Ví dụ:

```text
>>> print 1 + "kushal"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

Làm sao để xử lý exceptions?

Chúng ta sử dụng cú pháp try... except để xử lý exception. Cú pháp cơ bản như sau:

```text
try:
    statements to be inside try clause
    statement2
    statement3
    ...
except ExceptionName:
    statements to evaluated in case of ExceptionName happens
```

Nó làm theo các bước sau:

```text
    First all lines between try and except statements.
    If ExceptionName happens during execution of the statements then except clause statements execute
    If no exception happens then the statements inside except clause does not execute.
    If the Exception is not handled in the except block then it goes out of try block.
```

Ví dụ sau sẽ thực hiện kịch bản trên.

```text
>>> def get_number():
...     "Returns a float number"
...     number = float(raw_input("Enter a float number: "))
...     return number
...
>>>
>>> while True:
...     try:
...         print get_number()
...     except ValueError:
...         print "You entered a wrong value"
...
```

```text
Enter a float number: 45.0
45.0
Enter a float number: 24,0
You entered a wrong value
Enter a float number: Traceback (most recent call last):
  File "<stdin>", line 3, in <module>
  File "<stdin>", line 3, in get_number
```

KeyboardInterrupt

Trong lần nhập giá trị đầu tiên chúng ta nhập vào số thực, và sau đó in nó ra màn hình, sau đó chúng ta sẽ đưa vào dấu phẩy trong số thực, và sẽ có lỗi khi chúng ta làm như vậy.

Trong lần thứ 3 chúng ta ấn tổ hợp phím ctrl +C sẽ xuất hiện một lỗi là KeyboardInterrupt, sẽ không có một exception nào.

Sẽ có một cách để tổng hợp lại tất cả các exception đó. Ví dụ các bạn có thể xem dưới đây:

```text
>>> try:
...     raw_input() # Press Ctrl+c for a KeyboardInterrupt
... except:
...     print "Unknown Exception"
...
Unknown Exception
```

Raising exceptions

```text
>>> raise ValueError("A value error happened.")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: A value error happened.
```

Chúng ta có thể bắt exception như một exception bình thường.

```text
>>> try:
...     raise ValueError("A value error happened.")
... except ValueError:
...     print "ValueError in our code."
...
ValueError in our code.
```

Using finally for cleanup

Nếu chúng ta muốn có một vài báo cái mỗi khi thực hiện trong mọi hoàn cảnh, chúng ta có thể sử dụng mệnh đề, nó sẽ chạy trước khi kết thúc biểu thức.

```text
>>> try:
...     fobj = open("hello.txt", "w")
...     res = 12 / 0
... except ZeroDivisionError:
...     print "We have an error in division"
... finally:
...     fobj.close()
...     print "Closing the file object."
...
We have an error in division
Closing the file object.
```

Trong ví dụ này chúng ta đảm bảo chắc chắn rằng tập tinđược mở, đóng. Chúc bạn thành công!

