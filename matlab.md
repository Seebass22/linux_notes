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

## indexing
A(2) % 2
D_m(3, 1) % 4

## generate points from 0 to 2pi with steps of 0.01
x = start:step:end
## generate 100 evenly spaced points between x1 and x1
x = linspace(x1, x2)
## generate n evenly spaced points between x1 and x1
x = linspace(x1, x2, n)

%% -----------------------------------------------------------------------------
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
if expression
	statements
elseif
	statements
else
	statements
end
%% -----------------------------------------------------------------------------
# PLOTS
## plot and label
plot(x, y)
xlabel('x')
ylabel('sin(x)')

## legend
legend('sin')

##polynomial curve fitting
### return coefficients of polynomial p(x) of degree n
p = polyfit(x, y, n)
### return values of polynomial p at each point in x
vals = polyval(p,x)
### plot
plot(x, vals)
