# PyPoint
Python library which allows you to encrypt values at Runtime and prevent memory hacking modification using XOR encryption and pickle


### Some precisions

The algorithm used to encrypt values is XOR which is not cryptographically secure.
By default, if the encrypted value (which is set at ``__init__`` and when the ``set_value`` method is called) does not match with the current value, the method ``on_value_modified`` will be called. This method restore the original value and raise an ``IllegalValueModification`` exception

## Get started

Importing the library:

```py
from PyPoint.Values import Pvalues
```

## A basic example

```py
from PyPoint.Values import Pvalue

class Msg:
    message : str
    def __init__(self, message) -> None:
        self.message = message

if __name__ == "__main__":
    # You can also protect the Object itself, in that case, the properties of this object won't be protected.
    pMessage = Msg(Pvalue("Protected message"))
    
    print(pMessage.message.value)

    pMessage.message.value = "New message"


```




