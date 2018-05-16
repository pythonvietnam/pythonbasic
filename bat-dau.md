# Bắt đầu

Python là ngôn ngữ lập trình thông dịch, điều đó có nghĩa là bạn có thể viết code ngay trên trình thông dịch hoặc viết vào file sau đó chạy chúng. Đầu tiên chúng ta sẽ sử dụng trình thông dịch để bắt đầu viết một chương trình đầu tiên \(bạn có thể sử dụng shell trên Windows hoặc Terminal trên Linux\)

```text
$ python
Python 2.5.1 (r251:54863, Oct 30 2007, 13:54:11)
q[GCC 4.1.2 20070925 (Red Hat 4.1.2-33)] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

Để có thể in ra dòng chữ "Xin chào Python Viet Nam" bạn có thể làm như sau:

```text
>>> print "Xin chào Python Viet Nam!"
Hello World!

helloworld.py
```

Bây giờ ta sẽ làm cách mà lập trình viên hay làm, bạn sẽ tạo một file helloworld.py, bạn có thể sử dụng bất cứ một trình soạn thảo mà bạn biết để tạo ra file này. Chú ý đuôi mở rộng là .py

```text
#!/usr/bin/env python
print "Hello World!"
```

Để thực hiện chạy, bạn cần trao quyền cho file đó được thực thi. Bạn dùng lệnh sau:

```text
$ chmod +x helloworld.py
```

Sau đó chạy

```text
$ ./helloworld.py
Hello World!
```

Trong dòng đầu tiên có dấu \#!, chúng ta gọi nó là sha-bang. Sử dụng để thông báo cho trình thông dịch Python chạy đoạn code. Dòng tiếp theo trong đoạn code trên chúng ta in ra thông báo. Trong Python chúng ta gọi các dòng văn bản là chuỗi.

Khoảng trắng và thụt đầu dòng

Trong Python khoảng trắng rất quan trọng. Chúng ta phân biệt cách sử dụng dấu khoảng trắng. Khoảng trắng trong dòng đầu tiên được xem như dấu thụt đầu dòng. Nhưng nếu sử dụng sai thì sẽ báo lỗi.

Ví dụ như sau:

```text
>>> a = 12
>>>  a = 12
File "<stdin>", line 1
a = 12
IndentationError: unexpected indent
^
```

Chú ý: Có một dấu cách đầu tiên gây ra lỗi trong đoạn code trên, do đó chúng ta cần đặt dấu thụt đầu dòng thích hợp.

Chúng ta có một số chú ý cho việc sử dụng dấu khoảng trắng và định danh

```text
Use 4 spaces for indentation.
Never mix tab and spaces.
One blank line between functions.
Two blank lines between classes.
```

Có nhiều nơi trong đoạn code mà bạn phải áo dụng cách dùng dấu cách, ví dụ như:

```text
Add a space after ”,” in dicts, lists, tuples, and argument lists and after ”:” in dicts.
Spaces around assignments and comparisons (except in argument list)
No spaces just inside parentheses.
```

Comments Comments là một đoạn văn bản được viết trong code, chúng được sử dụng để giải thích hoặc chú thích cho người khác hiểu về đoạn code đó. Một đoạn comment bắt đầu bằng dấu \#, mọi thứ sau dấu comment không được thực thi trong chương trình.

```text
>>> # This is a comment
>>> # The next line will add two numbers
>>> a = 12 + 34
>>> print c #this is a comment too :)
```

Comments giúp cho lập trình viên dễ dàng cải tiến mã nguồn, ghi chú các chức năng của đoạn code thực hiện, nó có thể là người viết, ngày viết.

```text
# FIXME -- fix these code later
# TODO -- in future you have to do this
```

Modules Modules trong Python là các tập tin chưa các hàm được định nghĩa sẵn, biến cái mà chúng ta có thể sử dụng lại, nó cũng có đuôi mở rộng là .py. Python đã cung cấp sẵn một số module mặc định. Chúng ta có thể sử dụng chúng. Để sử dụng chúng ta cần dùng lệnh import. Ví dụ như sau:

```text
>>> import math
>>> print math.e
2.71828182846
```

Chúng ta sẽ tìm hiểu chi tiết về các Module trong các phần sau. Chúc các bạn thành công!

