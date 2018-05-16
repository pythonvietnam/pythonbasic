# Class

Chương trình đầu tiên.

Để viết một chương trình đầu tiên, bạn cần biết cú pháp của class trong chương trình như sau:

```text
class nameoftheclass(parent_class):
    statement1
    statement2
    statement3
```

Trong statement bạn có thể viết bất cứ điều gì, bạn có thể định nghĩa hàm \(cái mà chúng ta gọi là method của một class\)

```text
>>> class MyClass(object):
...     a = 90
...     b = 88
...
>>> p = MyClass()
>>> p
<__main__.MyClass instance at 0xb7c8aa6c>
```

Trong ví dụ trên chúng ta có thể thấy đầu tiên chúng ta sẽ khai báo một class có tên là MyClass, chúng ta sẽ viết một vài biểu thức nào đó trong class đó. Sau khi class được định nghĩa, chúng ta sẽ tạo một object p của class MyClass.

```text
>>> dir(p)
['__doc__', '__module__', 'a', 'b']
```

bạn có thể nhìn thấy biến a và b trong nó.  
**init** method

**init** is là một method đặc biệt trong class Python, nó là một phương thức để khởi tạo một lớp. Trong ví dụ sau sẽ sử dụng nó.

```text
class Student(object):
    """
    Returns a ```Student``` object with the given name, branch and year.

    """
    def __init__(self, name, branch, year):
            self.name = name
            self.branch = branch
            self.year = year
            print "A student object is created"

    def print_details(self):
        """
        Prints the details of the student.
        """
        print "Name:", self.name
        print "Branch:", self.branch
        print "Year:", self.year
```

Init được gọi khi có một đối tượng của lớp được xây dựng. Điều đó có nghĩa là khi nào chúng ta sẽ tạo ra một đối tượng student chúng ta sẽ thấy thông báo "Một đối tượng student được tạo ra" trong dấu nhắc. Bạn có thể thấy các đối số đầu tiên của phương pháp là tự. Nó là một biến đặc biệt chỉ đến đối tượng hiện tại \(như thế này trong C ++\). Đối tượng được truyền ngầm cho mọi phương thức có trong nó, nhưng chúng ta phải làm rõ nó trong mọi phương thức khi viết các phương thức. Ví dụ

```text
>>> std1 = Student()
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
TypeError: __init__() takes exactly 4 arguments (1 given)
>>> std1 = Student('Kushal','CSE','2005')
A student object is created
```

Trong ví dụ này lúc đầu, chúng ta đã cố gắng tạo ra một đối tượng Student mà không phải truyền bất kỳ đối số nào và trình thông dịch Python phàn nàn rằng phải mất 4 đối số mà chỉ nhận được một \(self\). Sau đó chúng ta tạo ra một đối tượng với các giá trị đối số thích hợp và từ thông báo đã in, ta có thể dễ dàng hiểu rằng phương thức init đã được gọi là phương thức constructor.

Bây giờ chúng ta sẽ gọi phương thức print\_details \(\).

```text
>>> std1.print_details()
Name: Kushal
Branch: CSE
Year: 2005
```

Inheritance

In general we human beings always know about inheritance. In programming it is almost the same. When a class inherits another class it inherits all features \(like variables and methods\) of the parent class. This helps in reusing codes.

In the next example we first create a class called Person and create two sub-classes Student and Teacher. As both of the classes are inherited from Person class they will have all methods of Person and will have new methods and variables for their own purpose.  
student\_teacher.py

```text
#!/usr/bin/env python
class Person(object):
    """
    Returns a ```Person``` object with given name.

    """
    def __init__(self, name):
        self.name = name

    def get_details(self):
        "Returns a string containing name of the person"
        return self.name

class Student(Person):
    """
    Returns a ```Student``` object, takes 3 arguments, name, branch, year.

    """
    def __init__(self, name, branch, year):
        Person.__init__(self, name)
        self.branch = branch
        self.year = year

    def get_details(self):
        "Returns a string containing student's details."
        return "%s studies %s and is in %s year." % (self.name, self.branch, self.year)


class Teacher(Person):
    """
    Returns a ```Teacher``` object, takes a list of strings (list of papers) as
    argument.
    """
    def __init__(self, name, papers):
        Person.__init__(self, name)
        self.papers = papers

    def get_details(self):
        return "%s teaches %s" % (self.name, ','.join(self.papers))
```

```text
person1 = Person('Sachin')
student1 = Student('Kushal', 'CSE', 2005)
teacher1 = Teacher('Prashad', ['C', 'C++'])

print person1.get_details()
print student1.get_details()
print teacher1.get_details()
```

Kết quả như sau:

```text
$ ./student_teacher.py
Sachin
Kushal studies CSE and is in 2005 year.
Prashad teaches C,C++
```

In this example you can see how we called the **init** method of the class Person in both Student and Teacher classes’ **init** method. We also reimplemented get\_details\(\) method of Person class in both Student and Teacher class. So, when we are calling get\_details\(\) method on the teacher1 object it returns based on the object itself \(which is of teacher class\) and when we call get\_details\(\) on the student1 or person1 object it returns based on get\_details\(\) method implemented in it’s own class.  
Multiple Inheritance

One class can inherit more than one classes. It gets access to all methods and variables of the parent classes. The general syntax is:

```text
class MyClass(Parentclass1, Parentclass2,...):
    def __init__(self):
        Parentclass1.__init__(self)
        Parentclass2.__init__(self)
        ...
        ...
```

Deleting an object

As we already know how to create an object, now we are going to see how to delete an Python object. We use del for this.

```text
>>> s = "I love you"
>>> del s
>>> s
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 's' is not defined
```

del actually decreases reference count by one. When the reference count of an object becomes zero the garbage collector will delete that object.  
Getters and setters in Python

One simple answer, don’t. If you are coming from other languages \(read Java\), you will be tempted to use getters or setters in all your classes. Please don’t. Just use the attributes directly. The following shows a direct example.

```text
>>> class Student(object):
...     def __init__(self, name):
...         self.name = name
...
>>> std = Student("Kushal Das")
>>> print std.name
Kushal Das
>>> std.name = "Python"
>>> print std.name
Python
```

Properties

If you want more fine tuned control over data attribute access, then you can use properties. In the following example of a bank account, we will make sure that no one can set the money value to negative and also a property called inr will give us the INR values of the dollars in the account.

```text
#!/usr/bin/env python

class Account(object):
    """The Account class,
    The amount is in dollars.
    """
    def __init__(self, rate):
        self.__amt = 0
        self.rate = rate

    @property
    def amount(self):
        "The amount of money in the account"
        return self.__amt

    @property
    def inr(self):
        "Gives the money in INR value."
        return self.__amt * self.rate

    @amount.setter
    def amount(self, value):
        if value < 0:
            print "Sorry, no negative amount in the account."
            return
        self.__amt = value

if __name__ == '__main__':
    acc = Account(61) # Based on today's value of INR :(
    acc.amount = 20
    print "Dollar amount:", acc.amount
    print "In INR:", acc.inr
    acc.amount = -100
    print "Dollar amount:", acc.amount
```

Kết quả như sau:

```text
$ python property.py
Dollar amount: 20
In INR: 1220
Sorry, no negative amount in the account.
Dollar amount: 20
```

