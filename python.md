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
## open file for reading only
## creates file if does not exist, replaces content of existing file
f = open('filename.txt', 'r')

## open for both read and write
f = open('filename.txt', 'r+')

## read file to string
text = f.read()

## read lines of file to list of strings
line_list = f.readlines()

## close file
f.close()
## automatically close file
with open('file.txt') as f:
	data = f.read()

# ------------------------------------------------------------------------------
# STRINGS
# int to string
str(42)

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
# ARGUMENT PARSING

import argparse
parser = argparse.ArgumentParser()
# add arguments, then
args = parser.parse_args()

## add positional argument "start", set help text
parser.add_argument("echo", help="thing to echo")

## optional argument
parser.add_argument("--verbose", help="display verbose output")

## set variable to true if argument exists
parser.add_argument("--verbose", action="store_true")
if args.verbose:
	print("verbose output enabled")
	
## short and long options
parser.add_argument("-v", "--verbose")
	
## argument with optional parameter, const on empty
## set name of parameter in usage message
parser.add_argument('--start', nargs='?', const='', metavar='activity')

## restrict to int, 3 choices
parser.add_argument("-v", "--verbosity", type=int, choices=[0, 1, 2])

## count argument, for example "-v" x3 = "-vvv", default value 0 (if arg not used)
parser.add_argument("-v", "--verbosity", action="count", default=0, help="increase output verbosity")
print(args.verbosity)

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

# ------------------------------------------------------------------------------
# BUILT IN MODULES
## simple http server
- runs hosts content of current director
python3 -m http.server

# ------------------------------------------------------------------------------
# ADDITIONAL TOOLS
## PEP8 code style checker
- pycodestyle
