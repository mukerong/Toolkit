## Dictionary

---

### dict.keys()

* return a list of all keys
* dict_keys type
* use list() to transfer to a list

### dict.values()

* return a list of all values
* dict_values type
* use list() to transfer to a list

### dict.items()

return a list of tuples of keys and values

```Python
for key, value in dict.items():
    pass
```

### dict.get()

### defaultdict

Here is [some examples](https://www.accelebrate.com/blog/using-defaultdict-python/)

```Python
from collections import defaultdict
mydict = defaultdict(function)
```

### append multiple values for one key

[Reference](http://stackoverflow.com/questions/3199171/append-multiple-values-for-one-key-in-python-dictionary)

```Python
dict[key].append()
```

 Loop issues

When looping a dictionary and appending to a list, you will see that all the dictionary has the same values. This is because, when you create keys and values for a dictionary in a loop, the values assigned to the keys are stored as a reference. Therefore, if in the same loop you give a key another value, it will update the reference to the value for this loop and all preceding loops.

There are two ways to deal with this:

1. Append a copy of the dictionary each loop

```Python
list.append(dictionary.copy())
```

2. Initialize the dictionary for each loop

```Python
for element in root:
    element_dict = {}
    for item in list:
        element_dict[item] = something
        desired_list.append(element_dict)
```
