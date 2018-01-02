## Python descriptors
> Notes on python data descriptors

#### Overview

`Descriptor` is simply an object attribute whose attribute access has been overridden by methods from `Descriptors Protocol`.
Those methods are __get__(), __set__(), and __delete__(). If any of those methods are defined for an object, it is said to be a descriptor.

#### Property lookup

Default behavior is `obj.__dict__['x'] -> type(obj).__dict__['x']`
but if attribute is a descriptor than behavior might be changed and propert accessor method will be called.


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

#### Resources
https://docs.python.org/3/howto/descriptor.html
https://www.youtube.com/watch?v=ZdvpNaWwx24&t=722s
https://www.ibm.com/developerworks/library/os-pythondescriptors/