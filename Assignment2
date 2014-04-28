## We have two functions in order to cache the inverse of a matrix
## The first one is called makeCacheMatrix. It takes a matrix (which 
## will be inversed) as an argument, and then creates a list composed 
## of four different functions.

makeCacheMatrix <- function (x = matrix ()) {
        ## x is a matrix used as the argument of our function makeCacheMatrix
        
        m <- NULL ## Here we establish that there is an object m that 
        ## is null for now.
        
        set <- function (y) {   ## We create a function called set. It 
                x <<- y         ## takes the argument "y" from the superior
                m <<- NULL      ## enviroment, and then we use the <<-
        }                       ## operator in order to preserve the value
        ## of "y" assigned to "x" within all the enviroment. If we had used the
        ## <- operator, "x" will no longer be the same as "y" once we leave the
        ## enviroment of the set function. Then, we reset the object "m", it
        ## is essential when running the makeCacheMatrix funtion several times
        ## one after another.
        
        
        get <- function () x    ## The second function is called get. 
        ## It just return the value of the object "x". 
        
        setinverse <- function (solve) m <<- solve      ## Here is a
        ## new one, set inverse. It applies the function solve, which 
        ## provides the inverse of a matrix, to the object "m". This is the 
        
        
        getinverse <- function () m     ##The fourth and final one is
        ## getinverse, which returns the value of the object "m".
        
        list (set = set, get = get, setinverse = setinverse,
              getinverse = getinverse)  ## Finally, we create the list
              ## with our four functions: set, get, setinverse and 
              ## getinverse. By now, we have defined four functions and
              ## put them into a list.
}


## Now we will use the functions inside the makeCacheMatrix one to calculate
## the inverse of a matrix and storing it in the object "m". But first we will 
## check if "m" has already been calculated for the same matrix, and if so, we
## will just return its previous value avoiding having to repeat the 
##computation. 

cacheSolve <- function (x, ...) {       ## First, we take an argument: "x". 
        ## That's why we used the <<- operator in the set function we defined 
        ## earlier: we are refering to the same object in both funcitons.
        
        m <- x$getinverse () ## Here we check if for this "x" there's something 
        ## cached. If so, this line of code will pass the cached values to the
        ## m object. 
        
        if (!is.null(m)) {      ## These are the key lines. If we had calculated
                message ("Getting cached data") ## the inverse before, "m" won't
                return (m)      ## be null, and this will just return the cached
        }                       ## value.
        
        data <- x$get ()        ## And if we have not calculated it beforehand, 
        m <- solve (data, ...)  ## we do it now and stores the value to be able
        x$setinverse (m)        ## to cache it next time.
        m
}
