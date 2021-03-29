# GENERAL
## function documentation (R console)
?sum

## generate vector
## : operator
> c(1:5)
[1] 1 2 3 4 5
## seq function
## seq(start, end, inc_amount)
> seq(0, 15, 5)
[1] 0 5 10 15

# ------------------------------------------------------------------------------
# MISC 
## integer division
a %/% b

# ------------------------------------------------------------------------------
# COMBINATORICS
## calculate binomial coefficient
choose(n,k)

## binomial distribution
## probability of k ourcomes in n trials, where probability of outcome is p
## dbinom(n, k, p)

## quiz with 12 questions, 5 choices, probablity of exactly 4 correct answers
dbinom(4, 12, 0.2)
## probability of 4 or less correct answers
pbinom(4, 12, 0.2)

## sum 1 to 100
## pbinom(q, size, prob, lower.tail=TRUE)
pbinom(0, 100, 0.00720, lower.tail=FALSE)

# ------------------------------------------------------------------------------
# RANDOM VALUES
## generate n random values from 0 to 1
> runif(2)
[1] 0.3165484 0.7841279
## optional parameters for min, max

## sample from vector (only use values once)
## sample(vec, size)
> socks <- c("red", "grey", "white", "red", "black")
> sample(socks, 2)
[1] "grey" "red"
## with replacement
> sample(socks, 8, replace=TRUE)

# ------------------------------------------------------------------------------
# LOOPS AND CONDITIONALS
while (expression) {
}

x <- c(2,5,3,9,8,11,6)
for (val in x){
}

if (expression) {
} else {
}

## ifelse(test, yes, no)
> x <- c(1,2,3)
> ifelse(x < 3, "small", "too big")
[1] "small"    "small"    "too big"

# ------------------------------------------------------------------------------
# FUNCTIONS
get_fuel <- function(mass) {
	result <- mass / 3 + 1
	return(result)
}

# ------------------------------------------------------------------------------
# READING FILES
my.data <- read.table("input.txt", header=FALSE)
