# Chuỗi

Chuỗi là văn bản đơn gian. Trong Python chúng ta khai báo chuỗi giữa các dấu "" hoặc '' hoặc ''' hoặc "" """. Ví dụ dưới đây sẽ giúp bạn hiểu rõ hơn.

```text
>>> s = "I am Indian"
>>> s
'I am Indian'
>>> s = 'I am Indian'
>>> s = "Here is a line \
... splitted in two lines"
>>> s
'Here is a line split in two lines'
>>> s = "Here is a line \n split in two lines"
>>> s
'Here is a line \n split in two lines'
>>> print s
Here is a line
split in two lines
```

Nếu bạn muốn in ra các chuỗi bạn có thể sử dụng dấu ba ngoặc/ hai ngoặc như sau:

```text
>>> s = """ This is a
... multiline string, so you can
... write many lines"""
>>> print s
This is a
multiline string, so you can
write many lines
```

Các phương pháp của chuỗi.

Mỗi chuỗi có cung cấp các phương thức làm việc có sẵn, chúng ta sẽ nghiên cứu hàm s.split\(""\)

```text
>>> s = "kushal das"
>>> s.title()
'Kushal Das'
```

Trong ví dụ này hàm title\(\) sẽ chuyển các ký tự đầu của chuỗi từ chữ thường thành chữ hoa.

Chúng ta có thể sử dụng để chuyển chuỗi thành chữ hoa hoặc chữ thường, ví dụ như sau:

```text
>>> z = s.upper()
>>> z
'KUSHAL DAS'
>>> z.lower()
'kushal das'
```

upper\(\) trả về ký tự hoa hoặc lower\(\) trả về ký tự thường như ví dụ trên.

```text
>>> s = "I am A pRoGraMMer"
>> s.swapcase()
'i AM a PrOgRAmmER'
```

swapcase\(\) trả về chuỗi với chuỗi đã được hoán đổi so với chuỗi ban đầu.

```text
>>> s = "jdwb 2323bjb"
>>> s.isalnum()
False
```

Với làm isalnum\(\) sẽ trả về kết quả False do hàm hay sẽ kiểm tra các ký tự có phải là ký tự hay không.

```text
>>> s = "jdwb2323bjb"
>>> s.isalnum()
True
```

Đây là kết quả khi không có ký tự trắng.

```text
>>> s = "SankarshanSir"
>>> s.isalpha()
True
>>> s = "Sankarshan Sir"
>>> s.isalpha()
False
```

isalpha\(\) kiểm tra ký tự trong bảng chữ cái.

```text
>>> s = "1234"
>>> s.isdigit() #To check if all the characters are digits or not
True
>>> s = "Fedora9 is coming"
>>> s.islower() # To check if all chracters are lower case or not
False
>>> s = "Fedora9 Is Coming"
>>> s.istitle() # To check if it is a title or not
True
>>> s = "INDIA"
>>> s.isupper() # To check if characters are in upper case or not
True
```

Để tách chuỗi chúng ta có thể dùng làm split\(\). Nó sẽ trả về chuỗi được tách ra.

```text
>>> s = "We all love Python"
>>> s.split(" ")
['We', 'all', 'love', 'Python']
>>> x = "Nishant:is:waiting"
>>> x.split(':')
['Nishant', 'is', 'waiting']
```

Chúng ta cũng có thể dùng làm join\(\) để thực hiện ghép chuỗi

```text
>>> "-".join("GNU/Linux is great".split(" "))
'GNU/Linux-is-great'
```

Trong ví dụ trên chúng ta chia chuỗi "GNU/Linux is great" được chia ra bằng dầu cách, và chúng ta sẽ thay thế bằng dấu "-".

Dải chuỗi

Ví dụ:

> > > s = " abc\n " s.strip\(\) 'abc'

Bạn có thể thực hành strip từ bên phải hoặc bên trái chuỗi sử dụng hai hàm lstrip\(chars\) hoặc rstrip\(chars\).

```text
>>> s = "www.foss.in"
>>> s.lstrip("cwsd.")
'foss.in'
>>> s.rstrip("cnwdi.")
'www.foss'
```

Tìm kiếm văn bản:

Python cũng cung cấp cho chúng ta hàm để tìm kiếm ký tự/ hoặc chuỗi con trong một chuỗi. Ví dụ:

```text
>>> s = "faulty for a reason"
>>> s.find("for")
7
>>> s.find("fora")
-1
>>> s.startswith("fa") #To check if the string startswith fa or not
True
>>> s.endswith("reason") #
True
```

find\(\) sẽ trả về chuỗi nếu như có kết quả và -1 nếu như không có.

Palindrome

```text
#!/usr/bin/env python
s = raw_input("Please enter a string: ")
z = s[::-1]
if s == z:
    print "The string is a palindrome"
else:
    print "The string is not a palindrome"
```

Kết quả

```text
$ ./palindrome.py
Please enter a string: madam1
The string is not a palindrome
$ ./palindrome.py
Please enter a string: madam
The string is a palindrome
```

Số từ

Trong ví dụ này chúng ta sẽ đếm số từ trong dòng. Ví dụ:

```text
#!/usr/bin/env python
s = raw_input("Enter a line: ")
print "The number of words in the line are %d" % (len(s.split(" ")))
```

Kết quả như sau

```text
$ ./countwords.py
Enter a line: Sayamindu is a great programmer
The number of words in the line are 5
```

Chúc bạn thành công!

