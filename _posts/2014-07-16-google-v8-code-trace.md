---
layout: default
title: google v8 code trace
---

{{ page.title }}

{% highlight c++ %}
#define TYPE_CHECK(T, S)                                       \
  while (false) {                                              \
    *(static_cast<T* volatile*>(0)) = static_cast<S*>(0);      \
  }
{% endhighlight %}
