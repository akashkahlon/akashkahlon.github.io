---
layout: post
title: "Attribute Accessors"
description: "Using Attribute Accessors"
tags: ['Ruby']
author: Akashdeep Singh
---

In ruby, instance variables can not be accessed outside the method in which they are defined in the x.y form. We need to define `setter` and `getter` methods for accessing instance variables outside their respective functions. The `setter` and `getter` methods could be of the form:

~~~ Ruby
class Blog

  def getter
    @instance_variable   
  end

  def setter(argument_passed)
    @instance_variable = argument_passed
  end

end

~~~

  This means, every time we need to access and modify an instance variable outside its function we will have to define a `getter` and a `setter` method for this `instance variable`.
  Attribute accessor, used as `attr_accessor`, is a function which gives us the power of using an instance variable outside the function without having to define the setter and getter methods for it. The setting and getting permissions can be provided separately or together using a single function.

~~~ Ruby
  attr_reader :instance_variable
~~~

  `attr_reader` function is used for providing an approach like the `getter` function,

~~~ Ruby
  Blog.new.instance_variable
~~~


  when called, this will give the value of instance_variable.But with just `attr_reader`, we can not set the value for this instance_variable.

~~~ Ruby
  Blog.new.instance_variable = some_value #this will give an error
~~~

  For setting the values, we can use another attribute accessor function, `attr_writer`.

~~~ Ruby
  attr_writer :instance_variable
~~~

  Now the call for setting the value of instance_variable will not give an error.

~~~ Ruby
  Class.new.instance_variable = some_value  #this will set the value for instance_variable as some_value.
~~~

  For doing both these things, i.e. the read and write access, by just one function, we use the `attr_accessor` function.

~~~ Ruby
  attr_accessor :instance_variable
~~~

  Now, we can get and set the value of this variable, outside its function without defining the `setter` and `getter` methods.

~~~ Ruby
Blog.new.instance_variable #this will give the value of the variable
Blog.new.instance_variable = some_value #this will set the value of the instance variable as some_value.
~~~

  So we see that how easy it gets by using just one function, after all Ruby is all about making things easy.
