+++
date = "2017-01-16 05:58:45"
draft = "false"
title = "Python decorators: fish hat"
slug = "python-decorators-fish-hat"

+++

So, let's say we want to decorate a fish with a hat (here's a good [read](https://en.wikipedia.org/wiki/This_is_Not_My_Hat)). First let's make a fishy function called fish.

```
def fish():
    return "a fish" 
```

Now let's decorate this fish with a hat. Let's make a hat decorator!

```
def hat(old_func):
    def new_func():
        return old_func() + " with a hat"
    return new_func
```

And putting it all together we get:

```
def hat(old_func):
    def new_func():
        return old_func() + " with a hat"
    return new_func

@hat
def fish():
    return "a fish" 
```

![](img/fish-hat.jpg)
*Illustration by Jon Klassen*

So. Functions are "first class citizens" in python. This means we can pass them as parameters to "higher order functions" (like as an argument to our `hat` function) or access properties like `myfunction.__doc__` or we can assign them for use as a callback.

Anyway. Moose can now wear hats too!

```
@hat
def moose():
    return "a moose"
```

Executing `moose()` actually executes `hat(moose)()`. The `hat` function returns a new function that returns `a moose with a hat`. Ta-da! Syntactic sugar!
