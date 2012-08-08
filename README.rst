RCPY - Racoon Calculator in Python
==================================


SYNOPSIS
--------

rcpy
echo 10 20 + p | rcpy



DESCRIPTION
-----------

RCPY is a simple reverse-polish notation calculator written in python.  Its
purpose was to add thing I felt were missing in dc(1) that I need in my daily
usage of a calculator.

It supports decimal, hexadecimal, binary as well as binary operation on these
values.



STACK HANDLING
--------------

pop:     print and remove the value from stack

dump:    dump the current stack content

d:       duplicate the top value of the stack

print:   print the value on top of stack
p:       same as `print`

swap:    swap the last 2 values on top of stack
r:       same as `swap`

clear:   empty the stack
c:       same as clear

Current  mode  is shown in the prompt, the used mode won't neither the values
already in stack nor the inputed values. If you add 0x42 to your stack while
being in bin mode, the stack will still con‐ tains 0x42 but if you do an
operation, the output will be in the chosen mode.

hex:     switch output of operations to hexadecimal

bin:     switch output of operations to binary

dec:     switch output of operations to decimal

conv:    convert value on top of the stack to the selected mode, this command won't work on floating values

int:     convert a floating value to an integer



GENERIC COMMANDS
----------------

quit:    quit RC
q:       same as `quit`


OPERATIONS
----------

+        Addition
-        Substraction
*        Multiplication
x        Multiplication
/        Division
%        Modulo
^        Power
v        Square root



All operation pop the two top values, and replace them by the result of the
operation in the stack.


BINARY OPERATIONS
-----------------

&        Logical and

|        Logical or

xor      Logical xor (^ being used for power)

<<       Shift to left

>>       Shift to right


All binary operation pop the two top values, and replace them by the result of
the operation in the stack.



EXAMPLE
-------

Sample session of RC:

[dec] rcpy> 10 20 30
[dec] rcpy> dump
10
20
30
[dec] rcpy> + d
10
50
[dec] rcpy> hex
[hex] rcpy> + p
0x3c
[hex] rcpy> bin
[bin] rcpy> conv
0x3c -> 0b111100
[bin] rcpy> dec
[dec] rcpy> 7 / p
8
[dec] rcpy> 22 / p
0.363636363636
[dec] rcpy> 10.7 + p
11.0636363636
[dec] rcpy> 1 4 << 1 8 << | p
272
[dec] rcpy> hex
[hex] rcpy> conv
272 -> 0x110

