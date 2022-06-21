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
class Msg:
    message : str
    def __init__(self, message) -> None:
        self.message = message

if __name__ == "__main__":
    pMessage = Pvalue(Msg("My message"))

    print(pMessage.value.message)
```




