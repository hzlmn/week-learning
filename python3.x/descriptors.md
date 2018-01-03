## Python descriptors
> Notes on python data descriptors

#### Overview

`Descriptor` is simply an object attribute whose attribute access has been overridden by methods from `Descriptors Protocol`.
Those methods are __get__(), __set__(), and __delete__(). If any of those methods are defined for an object, it is said to be a descriptor.

There are two types of descriptors:

 - Data Descriptor - descriptor that has `__get__` and `__set__`
 - Non-data Descriptor - only `__get__`

#### Property lookup

Default behavior is `obj.__dict__['x'] -> type(obj).__dict__['x']`
but if attribute is a descriptor than behavior might be changed and propert accessor method will be called.

Lookup chain for descriptors is

 - `obj.x.__get__` if it data descriptor
 - `obj.__dict__['x']`
 - `obj.x.__get__` if non data descriptor
 - `type(obj).__dict__['x']`
 - ...


#### Example

```python
class SimpleDescriptor(object):
    def __init__(self):
        pass

    def __get__(self, obj):
        pass

    def __set__(self, obj, value):
        pass

    def __delete__(self, obj):
        pass

```

> LazyProperty descriptor

```python
class LazyProperty:
    def __init__(self, func):
        self.func = func
        self.__name__ = func.__name__
    
    def __get__(self, obj):
        value = self.func(obj)
        obj.__dict__[self.__name__] = value
        return value


class Test:
    @LazyProperty
    def x(self):
        return 'test'
    
```

#### Resources
https://docs.python.org/3/howto/descriptor.html
https://www.youtube.com/watch?v=ZdvpNaWwx24&t=722s
https://www.ibm.com/developerworks/library/os-pythondescriptors/