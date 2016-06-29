# How to convert a string to lower or upper case in Ruby?

Ruby has a few methods for changing the case of strings. To convert to lowercase, use downcase:

"hello James!".downcase    #=> "hello james!"

Similarly, upcase capitalizes every letter and capitalize capitalizes the first letter of the 

string but lowercases the rest:

"hello James!".upcase      #=> "HELLO JAMES!"
"hello James!".capitalize  #=> "Hello james!"

If you want to modify a string in place, you can add an exclamation point to any of those methods:

string = "hello James!"
string.downcase!
string   #=> "hello james!"

[Refer to the documentation for String for more information](http://ruby-doc.org/core-2.3.1/String.html)