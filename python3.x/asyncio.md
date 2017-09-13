## asyncio
> Notes related to learning asyncio library


#### History

Python has a long history of developing `asyncio` module, finally in python3.6 it included as a core library. First proto of asyncio was called `Tulip`.

For better understanding of design principles of asyncio/tulip watch [lecture](https://www.youtube.com/watch?v=1coLC-MUCJc&t=215s) byt Guido.

#### Overview

`asyncio` allows programmer to write single-threaded concurrent event-based programs.

Old way of performing concurrent operating was by using `threading` or `multiprocessing` modules, that abstracts OS threads and processes operations. Core lib also includes synchronization primitives lile `mutex` 

Why it works fine, for high loaded I/O related applications, it could take some time for processing requests. Asyncio based on concept of coroutines (Kinda light weight threads) and EventLoop

So instead of Creating individual threads and handle them on os level, we handle coroutine objects by EventLoop.

Loop is structure that shedules, stop, etc coroutines.

Instead of waiting for some data (IO results or fetching data from external service) we pass `Future` object that is structure that handle operations that not finished yet and unblock call stack so the other requests can be perfomaned while another waiting for some data. 

asyncio EventLoop manage it and give back context when coroutine finished.

#### Resources

  - `asyncio` [chapter](https://pymotw.com/3/asyncio/index.html) on Python3 module of the week
  - Python `asyncio` official [documentation](https://docs.python.org/3/library/asyncio.html)
