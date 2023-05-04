# Assignment-2
#setting my working directory
setwd("C:/Users/Micheal/Desktop/practice")

#Creating special matrix
makeCacheMatrix<-function(x=matrix()){
inv<-NULL
set<-function(y){
x<<-y
inv<<-NULL
}
get<-function()x
setInverse<-function(inverse)inv<<-inverse
getInverse<-function()inv
list(set=set, get=get,
setInverse=setInverse,
getInverse=getInverse)
}
##Inverse of special matrix
cacheSolve<-function(x, ...){
inv<-x$getinv()
if(!is.null(inv)){
message("obtain the cached output")
return(inv)
}
assgt<-x$get()
inv<-solve(assgt, ...)
x$setinv(inv)
inv
}
