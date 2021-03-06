| rank | ▲ | ✰ | vote | url |
|:-:|:-:|:-:|:-:|:-:|
|  19  |  710 | 261 | 493 | [url](http://stackoverflow.com/questions/576169/understanding-python-super-and-init-methods) |

***

## 理解Python中`super()`和`__init__()`方法

我试着理解`super()`方法.从表面上看,两个子类实现的功能都一样.我想问它们俩的区别在哪里?

```python
class Base(object):
    def __init__(self):
        print "Base created"

class ChildA(Base):
    def __init__(self):
        Base.__init__(self)

class ChildB(Base):
    def __init__(self):
        super(ChildB, self).__init__()

print ChildA(),ChildB()
```

***


`super()`的好处就是可以避免直接使用父类的名字.但是它主要用于多重继承,[这里面](http://www.artima.com/weblogs/viewpost.jsp?thread=236275)有很多好玩的东西.如果还不了解的话可以看看[官方文档](https://docs.python.org/2/library/functions.html#super)

注意在Python3.0里语法有所改变:你可以用`super().__init__()`替换`super(ChildB, self).__init__()`.(在我看来非常nice)
