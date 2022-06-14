## Midterm 

### introduction to ruby (self summary)

Ruby is...
The open source programming language is dynamic, easy to understand and productive. Ruby's syntax is elegant, natural, easy to read and write.

> Seeing Everything as an Object

In Ruby, everything is an object. Any information and code can be assigned properties and actions. Object-oriented programming calls properties with the names of instance variables and actions, which are called methods. The purely object-oriented approach is especially evident in the demonstration of a bit of code rendered in a number.

```
5. times { print "We *love* Ruby -- Ruby is awesome!" }
```

In many other languages, numbers and primitive types are not objects. Ruby follows the influence of the Smalltalk language by providing methods and instance variables of all types. This makes using Ruby easier because the rules about objects all apply to Ruby.

> Ruby Flexibility

Ruby is considered a flexible language because parts of Ruby can be changed freely. Important parts in Ruby can be deleted or redefined. Existing parts can be added. Ruby tries not to limit programmers.

For example, addition is done with the plus (`+`) operator. However, if you want to use the word `plus` which is easier to read, then you can add that method to the built-in `Numeric` class.

```
class Numeric
  def plus(x)
    self.+(x)
  end
end

y = 5.plus 6
# y sekarang adalah 11
```

For convenience's sake, Ruby's operators are also methods. You can also redefine operators.

> Blocks: A Truly Expressive Feature

Ruby blocks are also considered a very flexible source of Ruby's power. Programmers can include closures for each method, explaining how the respective method should behave. Closures are called blocks and have become one of the most popular Ruby features in many newcomers to Ruby from other imperative languages such as PHP or Visual Basic.

Blocks are inspired by functional languages. Matz said, “I want to respect the Lisp culture in Ruby3 closures.”

```
search_engines =
   %w[Google Yahoo MSN].map do |engine|
     "http://www." + engine.downcase + ".com"
   end
```

In the code above, the block is described in the form of `do ... end`. The map method enforces a block to accept an array of words (Google, Yahoo, and MSN). Many of the other methods in Ruby are left with holes opened for programmers to write their blocks to fill in what a method is supposed to do.

> Ruby and Mixin

Unlike many other object-oriented languages, Ruby only provides single inheritance on purpose. But Ruby knows the concept of modules (referred to as Categories in Objective-C). The module is a collection of methods.

A class can mix (combine) a module and accept all methods (from the module in question) freely. For example, any class that implements `each` method can mixin the `Enumerable` module, which adds multiple methods that use `each` to loop.

```
class MyArray
   include Enumerable
end
```

In general, Rubyists find this a much clearer way than multiple inheritances, which is cumbersome and even too restrictive.

> Visual Appearance of Ruby

Ruby rarely uses punctuation and usually tends to use English keywords, some punctuation is used to clarify Ruby's code. Ruby doesn't need variable declarations. Ruby uses simple naming rules to define the scope of variables.

* `var` is a local variable.
* `@var` is an instance variable.
* `$var` is a global variable.

These sigils aim to make it easier and clearer when read for programmers to identify the function of each variable. Sigil can also be unnecessary if it has to be used on every instant `self.`

## Ruby Key Concepts
source : https://www.codecademy.com/

>  Ruby Variables

```
myVar = 48
```

In Ruby, a variable is a place to store values of almost any type including Integer, Boolean, String, Array, and Hashes.

Each variable has its own name which cannot begin with a capital letter or a number and we use the equal sign for assigning a value to that variable.

The variable declaration does not require that you mention a specific data type.

The following program declares `myvar` variable and assigns the value `48`.

> Put and print command

```
print "Hello"
puts "This is written in a new line"
print "Still printing"
```

`put` and `print` commands can be used to display text in the console.

> Code comments in Ruby

```
# I am a single line comment.
 
=begin
I am a multi line comment. 
I can take as many lines as needed.
=end
```

Commenting code helps programmers write free text that is commonly used to explain the code written, or can even be used to add TODO’s to the code. There are two types of comments that can be written in Ruby:

* Single line comments start with a `#`.
* Multi line comments start with `=begin` and end with `=end`.

> Numeric data types in Ruby

```
# Integer value
x = 1
 
# Float value
y = 1.2
```

In Ruby, the Numeric data type represents numbers including `integers` and `floats`.

> Arithmetic operations in Ruby

```
print 1+3
# Addition: output 4
 
print 1-2
# Subtraction: output -1
 
print 9/3
# Division: output 3
 
print 2*3
# Multiplication: output 6
 
print 2**3
# Exponentiation: output 8
 
print 16%9
# Modulo: output 7
```

In Ruby, we can use arithmetic operators to evaluate mathematical expressions. The most common Ruby arithmetic operators are addition (+), subtraction (-), division(/), multiplication(*), exponentiation(**) and modulo(%).

> Ruby Object Methods

```
var = "codecademy"
 
# Method to get the length of a string
print var.length # 10
 
# Method to get the string reversed
print var.reverse # ymedacedoc
 
# Method to conver all letters to uppercase
print var.upcase # CODECADEMY
```

In Ruby, methods are built-in abilities of objects. To access an object’s methods, you need to call it using a `.` and the method name.

> Strings in Ruby

```
# String 1
s1 = 'I am a single string!'
 
# String 2
s2 = "I am a double string!"
```

Strings in Ruby are a sequence of characters enclosed by single quotation marks (‘’) or double quotation marks (“”).

> Boolean Data Types in Ruby

```
# Boolean true variable
year2019 = true
 
# Boolean false variable
year2018 = false
```

In Ruby, in order to represent values of truth about specific statements, we use Boolean variables. Boolean variables values are either `true` or `false`.

> Ruby .upcase and .downcase Methods

```
puts "ruby".upcase
 
puts "ruby".downcase
```

Ruby strings have an `.upcase` and a `.downcase` method used to change their case. `.upcase` returns a version of the string in all uppercase, and `.downcase` returns a version in all lowercase.

> Ruby string interpolation

```
age = 30
 
print "Hi, my name is Cody, and I am #{age} years old"
# "Hi, my name is Cody, and I am 30 years old"
```

In Ruby, string interpolation is used to insert the result of Ruby code into a string.

> Get user input in Ruby

In Ruby, we can get the user’s input using `gets.chomp`. `gets` is the method that is used to retrieve user input. Ruby automatically adds a new line after each bit of input, so `chomp` is used to remove that extra line.

> `elsif` Statements in Ruby

```
print "enter a number: "
num = gets.chomp
num =  num.to_i;
 
if num == 5
  print "number is 5"
elsif num == 10
  print "number is 10"
elsif num == 11
  print "number is 11"
else
  print "number is something other than 5, 10, or 11"
end
```

In Ruby, an `elsif` statement can be placed between `if` and `else` statements. It allows us to check for additional conditions.

More than one `elsif` can be placed between `if` and `else`.

> Ruby not Operator

The `!` (not) operator in Ruby flips a boolean value. If a value is `true` then applying `!` to the value changes it to `false` and vice versa.

> Else statement in Ruby.

```
if number > 50 
  print "number is greater than 50"
else
  print "number is not greater than 50" 
end  
```

In Ruby, an if statement evaluates to either true or false. The code indented after the if portion is executed for true while the code indented after the else portion is executed for false.

> Comparison operators in Ruby.

The following comparison or relational operators are used in Ruby to compare values.

`>` - greater than; `<` - less than; `>=` - greater than or equal to; `<=` - less than or equal to; `==` - equal to

> Or operator in Ruby.

```
grade1 = 50
grade2 = 30
grade3 = 80
 
if grade1 > grade2 || grade1 > grade3
  puts "Grade 1 is not the lowest score!"
end
```

The `||` (or) operator is a logical operator which returns `true` if either of the expressions on left-hand side or right-hand side is `true`.

> `if` Statement in Ruby

```
number = 10
if number == 10
  puts "Your condition was true!"
end
```

An `if` statement in Ruby evaluates an expression, which returns either `true` or `false`. If the expression is `true`, Ruby executes the code block that follows the `if` whereas if the expression is `false`, Ruby returns nil.

In this example, the string `"Your condition was true!"` will print because the condition `number == 10` is true.

> And operator in Ruby.

```
if score1 > score2 && score1 > score3
  print "Score 1 is the greatest in value."
else
  print "Score 1 is not the greatest in value."
end
```

`&&` is a logical operator in Ruby which evaluates to `true` only if both expressions on either side of `&&` evaluates to `true`.

> Unless statement in Ruby.

```
#This construct requires a "number" variable to be less than 10 in order to execute:
print "Enter a number"
number = gets.to_i
unless number > 10
  puts "number is less than 10."
end
```

An `unless` statement in Ruby is used to evaluate an expression. If the expression evaluates to `false`, then the code following `unless` is executed.