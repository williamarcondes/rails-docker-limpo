# Cálculos

```ruby
1 + 1
2 * 2
5 / 3
5 % 3
5 ** 2
```

# Manipulando String

```ruby
"Hi"
'Hi'
"My age is #{1+2}"
puts "Hi"
printf("%d", 2+2)
```

# Manipulando Boolean

```ruby
true
false
nil
```

# if, unless, until, while, case

```ruby
if x == 1
  puts "X é 1"
else
  puts "X não é 1"
end
```

```ruby
unless x == 0
  puts "X não é 0"
else
  puts "X é 0"
end
```

```ruby
message = case grade
when "A"
  puts "Congratulations!"
when "B"
  puts "Well done"
when "C"
  puts "You can do better than that"
when "D"
  puts "Study harder"
when "E"
  puts "Did you do the tests?"
else
  puts "WTF of grade is that"
end
```

# if Inline
```ruby
puts "0" if x == 0
```

```ruby
x = 0

while x < 10
  puts "Valor de x é: #{x}"
  x += 1
end
```

```ruby
x = 0

until x == 10
  puts "Valor de x é: #{x}"
  x += 1
end
```

```ruby
for i in [1, 2, 3]
  puts i
end
```

```ruby
[1,2,3].each do |i|
  puts i
end
```

# Symbol

```ruby
:abcd
:aaa_daa
:aaaa_1
"aaa".__id__ == "aaa".__id__
:aaa.__id__ == :aaa.__id__
```

# Range

```ruby
(1..10)
(1...10).to_a
('a'..'z')
('aa'..'zz')
```

# Range de letras

```ruby
('a'..'z') === 'q'
('a'..'z').to_a
```

# Métodos

```ruby
def hello(name)
  puts 'Hello,' + name
end

hello("Will")
hello(1)
hello "OK"

def my_method(my_first_argument, my_last_optional_argument = false)
  puts "Eu tenho um último argumento" if my_last_optional_argument
  puts my_first_argument
end
```

# Object

```ruby
"Hi".size
"Kakaroto".reverse
"Kakaroto".downcase
"Kakaroto".upcase
```

```ruby
1.zero?
1.even?
32.to_s
-1.abs
```

```ruby
/a/.match("aaa")
```

```ruby
String.new("aaaa")
```
```ruby
String.class
```

# Classes

```ruby
class Gato
  def mia
    puts "Miau"
  end
end

gato = Gato.new
gato.mia
```

```ruby
class Person
  def initialize(age)
    @age = age
  end

  def adult?
    @age >= 18
  end
end

person1 = Person.new(2)
person1.adult?

person2 = Person.new(20)
person1.adult?
```

```ruby
class Dog
  def self.initialize_puppy
    self.new(0)
  end
end

dog = Dog.initialize_puppy
dog.class
dog.puppy?
```

```ruby
class Dog
  def age
    @age
  end

  def age=(age)
    @age = age
  end
end

dog = Dog.initialize_puppy
dog.age
dog.age = 10
dog.age
```

```ruby
class Dog
  attr_writer :name
end

dog = Dog.new
dog.name = "Rex"
dog.name
```

```ruby
class Dog
  attr_accessor :race
end

dog = Dog.new
dog.race = "Chihuahua"
dog.race
```

```ruby
class Dog
  attr_reader :mad?
end

dog = Dog.new
dog.mad?
```

# == and ===

```ruby
/a/ == 'a'
(1..10) == 1
String == "A"
'a' === 'a'
```

```ruby
/a/ === 'a'
(1..10) === 1
String === "A"
```

```ruby
case price
when 0..10
  puts "Cheap"
when 11..100
  puts "Not so cheap"
when 101..1000
  puts "Expensive"
when 1001..10000
  puts "Fucking expensive"
else
  puts "I wonder who would buy it"
end
```

```ruby
case object
when String
  puts object
when Fixnum
  puts object.to_s
when Symbol
  puts object.to_s
when MyAwesomeClass
  puts object.inspect
end
```

# Array

```ruby
list_of_chars = ["a", "b", "c"]

list_of_chars[0]
list_of_chars[2]
list_of_chars[-1]

list_of_chars = Array.new(10)

list_of_chars.pop
list_of_chars.push

list_of_chars.unshift
list_of_chars.shift

list_of_chars.size
list_of_chars.join(",")
```

# Hash

```ruby
hash = { :a => 10, :b => 5 }
hash[:a]
hash[:b]

hash.keys
hash.values

hash2 = { :c => 15, :d => 20}
hash.merge(hash2)
```

# Functional programming

## Block

```ruby
[1,2,3].each do |item|
  puts item
end
```

## Proc and Lambda

```ruby
my_lambda_method = lambda { |x| puts x }
my_proc_method = Proc.new { |x| puts x }

[1,2,3].each(&my_lambda_method)
[1,3,4].each(&my_proc_method)

def each_squared_element(array, method)
  array.each do |elem|
    method.call(elem)
  end
end

def each_squared_element_2(array, &method)
  array.each do |elem|
    yield(elem)
  end
end

def call_method(method)
  method.call
end
```

## Proc vs Lambda

```ruby
arg_error_lambda = lambda { |x| puts x }
arg_error_proc = Proc.new { |x| puts x }

call_method(arg_error_lambda)
call_method(arg_error_proc)

returned_lambda = lambda { return "OK" }
returned_proc = Proc.new { return "Not ok" }

call_method(returned_lambda)
call_method(returned_proc)
```

## Modules

```ruby
module SayHi
  def say_hi
    puts "Hi"
  end
end

class Dog
  include SayHi
end

dog = Dog.new
dog = dog.say_hi

class Dog
  extend SayHi
end

Dog.say_hi
```

# P.O.O

```ruby
Array.ancestors
```

```ruby
class Dog
  def bark
    puts "Au"
  end
end

class Doberman < Dog
end

dog = Doberman.new
dog.bark
```

## Acessos curiosos

```ruby
x = ['a', 'b', 'c']

x.first
x.last

x.second

class Array
  def second
    self[1]
  end
end
```
