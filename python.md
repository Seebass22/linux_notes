# GENERAL
## copy list
newlist = list(A)

## array slicing
## [start:stop:step]
## stop does not include the element at which it stops
a = [0, 1, 2, 3, 4, 5]
a[1:3] # => [1, 2]

#| -4 | -3 | -2 | -1 | negative indexes
#| A  | B  | C  | D  | sequence elements
#| 0  | 1  | 2  | 3  | positive indexes
#| 0:3:1 ...... |

# copy list (does not deep-copy contained lists)
b = a.copy()
# deep-copying
import copy
b = copy.deepcopy(a)

# return multiple items
def rotateRight(x, y):
    return y, -x
x, y = rotateRight(x, y)

# convert to binary
bin(3)

# convert binary to int
b = '1011'
int(b, 2)

# list comprehensions (listcomps)
## quickly fill a list
lst = [5, 1, 4, 9]
l = [func(x) for x in lst]

# use a list comprehension as cartesian product
colors = ['black', 'white']
sizes = ['S', 'M', 'L']
shirts = [(color, size) for color in colors for size in sizes]

# ------------------------------------------------------------------------------
# FILE IO
## read file to string
f = open('filename.txt', 'r')
text = f.read()

## read lines of file to list of strings
f = open('filename.txt', 'r')
line_list = f.readlines()

# ------------------------------------------------------------------------------
# STRINGS
## split string into list
txt = "one two three four"
txt2 = "one#two#three#four"
## default separator is any whitespace
x = txt.split()
x2 = txt.split("#")
## result ['one', 'two', 'three', 'four']

## raw string literals
## treat backslash literally (no escapes, other than terminating quotes)
r'your string here'

## split string of numbers into list of ints
A = '1, 2, 3, 4'
B = [int(x) for x in A.split(',')]
## result: [1, 2, 3, 4]

## print format string
r = 5
c = 2
print('nr of rows:{rows}, nr of columns:{columns}'.format(rows=r, columns=c))
## or
print('nr of rows:{rows}, nr of columns:{columns}'.format(r, c))
## or
print(f'nr of rows:{rows}, nr of columns:{columns}')

## strip characters from end of string
## strip newlines from string (does not cause error if no nl in string)
a = 'asdf\n'
a.rstrip('\n')
## strip something from left of string
lstrip
## rstrip and lstrip remove all combinations of supplied characters
## the characters are not a suffix string! for example:
a = 'magenta bags'
a.rstrip(' bags')
## => magent

# ------------------------------------------------------------------------------
# REGULAR EXPRESSIONS (regex)
string = "#49ffd2xxx"
## match string
re.match(r'#[0-9a-f]{6}', string)
## match whole string
re.fullmatch(r'#[0-9a-f]{6}', string)
## return list of all matches
re.findall(r'\d+', string)

## split string by occurences of pattern
## (do not include delimiter pattern)
re.split(r'\d+', string)
## (include delimiter)
re.split(r'(\d+)', string)
