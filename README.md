# jhu-ds
JHU Data Science

###Control Structures

for(i in 1:10) {
  print(i)
}


x <- matrix(1:6, 2, 3)
for( i in seq_len(nrow(x))) {
  for(j in seq_len(ncol(x))) {
    print(x[i,j])
  }
}



#while loops begin by testing a condition - watch out for infinite loops!

count <- 0
while(count < 10) {
  print(count)
  count <- count + 1
}


#sometimes there will be more than one condition - evaluated left to right

z <- 5

while(z >= 3 && z <= 10) {
  print(z)
  coin <- rbinom(1, 1, 0.5)
  
  if(coin == 1) {   ##random walk
    z <- z+1
  } else {
    z <- z-1
  }
}


#repeat initiates an infinite loop - only escape is to call break
#n.b. computeEstimate is NOT a real fn! imagines if variance between x1 and x0 is within a certain tolerance
#e.g. iterative process to hone in on number
#good for optimization - solution to equations/maximising a function

x0 <- 1
tol <- 1e-8

repeat{
  x1 <- computeEstimate()
  
  if(abs(x1 - x0) < tol) {
    break
  } else {
    x0 <- x1
  }
}


#better to set a hard limit on number of iterations and report whether convergence was achieved
#next is used to skip an iteration

for(i in 1:100) {
  if(i <= 20) {
    ##skip first 20 iterations
    next
  }
  ##do something here
  
}

#return signals that a function should exit and return a given value