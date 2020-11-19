# BASIC OPERATIONS
## Vectors
A = [1 2 3 4 5];
B = [9 7 5 3 1];
C = [2 4];

## matrices
D_m = [2 5 2
       1 2 3
       4 2 5];

E_m = [4 5 5; 5 2 4];

## scalar variables
f = 5;

## complex numbers
z = 2 + 4i;
zz = 1 + 5i;

## struct
person.name = 'bob';
person.age = 55;

## sum vector
sum(A)

## dotproduct (skalarprodukt)
dot(A,B)

## matrixmultiplication, inversion
D_m * inv(D_M)

## absolute value (betrag)
abs(z)

## transpose matrix
D_m'

## powers (potenzen)
f^2
## (quadratische Matrix mit sich selbst multiplizieren)
D_m^2
## (elementweise potenzieren)
D_m.^2

## square root (wurzeln)
sqrt(f)
## element-wise
sqrt(A)
sqrt(D_m)

## indexing (y, x)
A(2)        % 2
D_m(3, 1)   % 4
D_m(2:3, 3) % row 2-3, column 3
D_m(:, 1:2) % all rows, column 1-2

## generate points from 0 to 2pi with steps of 0.01
x = start:step:end
## generate 100 evenly spaced points between x1 and x1
x = linspace(x1, x2)
## generate n evenly spaced points between x1 and x1
x = linspace(x1, x2, n)

## get matrix/array dimensions
size(A)

## get number of array elements (length)
numel(A)

## reshape array/matrix
### to have 2 colmuns
reshape(Arr, [], 2)
### to have 4 rows
reshape(Arr, 4, [])

## get max (or min) in array
max(A)
## get max (or min) and index in array
[max_size, max_index] = max(A)

## sort rows of matrix, table or cell array
sortrows(A)
## sort by column 2
sortrows(A, [2])
## sort by column 2, then 4
sortrows(A, [2, 4])

## get data type of variable
class(A)

## print variable (incl. strings)
disp(A)

# -----------------------------------------------------------------------------
# CELL ARRAYS

## create cell array
c = {}
c = {1, [1 2 3], 'bob', true}

## access cell 1
c(1)
## access contents of cell 1
c{1}

## delete cell 1
c(1) = []
## delete contents of cell 1 -> empty cell
c{1} = []

## convert cell array to array
a = cell2mat(b)

# -----------------------------------------------------------------------------
# LOOPS AND CONDITIONALS 
## for loop
for n = 2:6
	x(n) = % something
end

## while loop
while n > 1
	% do something
	n = n - 1;
end

## exit a loop
break
## skip to next iteration
continue

## if, else statement
if expression && expression
	statements
elseif expression
	statements
else
	statements
end

## equality
==
## inequality
~=

## determine if variable has specified data type
isa(A, 'double')

# -----------------------------------------------------------------------------
# PLOTS

## multiple plot windows
figure(1)
plot(...)
figure(2)
plot(...)

## multiple plots in one window
### m-by-n grid, position = index of next plot
subplot(m, n, position)

## plot and label
plot(x, y)
xlabel('x')
ylabel('sin(x)')

# enable grid
grid on

## legend
legend('sin')

## overlay more plots
hold on
## stop overlay
hold off

## polynomial curve fitting
### return coefficients of polynomial p(x) of degree n
p = polyfit(x, y, n)
### return values of polynomial p at each point in x
vals = polyval(p,x)
### plot
plot(x, vals)

# -----------------------------------------------------------------------------
# IMAGES
pkg load image

## read image
img = imread('pic1.ppm')

## convert to grayscale
g_img = rgb2gray(img)

## calculate histogram, return counts and bin locations
[counts, binLocations] = imhist(g_img)
## display histogram
imhist(g_img)
