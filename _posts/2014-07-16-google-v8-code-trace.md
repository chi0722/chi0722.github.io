---
layout: default
title: Google V8 Code Trace
---

{{ page.title }}

It's a interesting macro used in v8 to perform a type checking.
In the macro, while (false) let the section will not be executed in runtime but check type-conversion in compile time.
(suspect) volatile is used to suppress warnings since de-referencing from null pointer.

{% highlight c++ %}
#define TYPE_CHECK(T, S)                                       \
  while (false) {                                              \
    *(static_cast<T* volatile*>(0)) = static_cast<S*>(0);      \
  }
{% endhighlight %}
