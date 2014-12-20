####object:   
- create new vector  x<-vector("name",type,length)  
- as.*funtion coercion type of object  

####matrices  
matrics are vectors with a dimention attribute.  
- m <- matrix(1:6, nrow=2, ncol=3)  #create new matrix  
- cbind(), rbind #another way to create new matrix  

####lists  
Lists are a special type of vector that can contain elements of different classes. Lists are very important.  

####Factors  
Factors are used to represent categorical data.   
  
####Missing Values  
function is.na()  and  is.nan()  

####Data Frames  
Data Frames are used to store tabular data.  

####Names  
objects can have names.  

####Subsetting  
[]  [[]]  $  
[[ can be used with computed indices and can take an integer sequence; $ can only be used with literal names.  
complete.cases()  

####Vectorized Operations  
  
  
####Reading Data  
- read.table, read.csv   
-  
- 
- file, gzfile, bzfile, url  
- colClasses

####Writing Data  
-    
  
####Coding Standard  
1. Always use text files/text editor  
2. Indent your code
3. Limit the width of your code(80 columns?)  
4.     
  
####lapply  


####apply  
apply is used to a evaluate a function over the margins of an array.  
- rowSums = apply(x,1,sum)  
- rowMeans = apply(x,1,mean)  
- colSums = apply(x,2,sum)  
- colMeans = apply(x,2,mean)  
Quantiles of the rows of a matrix    
x<-matrix(rnorm(200),20,10)  
apply(x,1,quantile, probs = c(0.25,0.75))  
  
####mapply  
mapply is a multivariate apply of sorts which applies a function in parallel over a set of arguments.  
   
####tapply  
tapply is used to apply a function over subsets of a vector.   
  
####split  
split takes a vector or other objects and splits it into groups determined by a factor or list of factors.  

  
####Date and Time  
- Dates and times have special classes in R that allow for numerical and statistical calculations  
- Dates use the Date class  
- Times use the POSIXct and POSIXlt class  
- Character strings can be coerced to Date/Time classes using the strptime function or the as.Date, as.POSIXlt, or as.POSIXct  
 
####debugging tools in R  
trackback, debug, browser trace recover  


####str function  
compactly display the internal structure of an R object.  
  
####Simulation  
- rnorm: generate random Normal variates with a given mean and standard deviation.  
- dnorm: evaluate the Normal probability density (with a given mean/SD) at a point (or vector of points)  
- pnorm: evaluate the cumulative distribution function for a Normal distribution  
- rpois: generate random Poisson variates with a given rate  
  
Probability distribution function usually have four functions associated with them. The function are prefixed with a  
- d  
- p  
- r  
- q  
  
####Profiling code  
Profiling is a systematic way to examine how much time is spend in different parts of a program  
system.time()   
Rprof(): this function starts the profiler in R  
   
####2 functions  
#####complete.R  
  
    complete <- function(directory,  id = 1:332) {
      paths <- list.files(directory, pattern = "csv", full.names = TRUE)
      k = length(id)
      j=1
      p2 <- matrix(0,k,2)
      for(i in id) {
        data <- read.csv(paths[i]) 
        data1 <- na.omit(data)##忽略NA
        p2[j,1] = i
        p2[j,2] = nrow(data1)
        j = j+1   
      }
      colnames(p2) <- c("id","nobs")
      p2
    }  
 

#####pollutantmean.R  
  
    pollutantmean <- function(directory, pollutant, id = 1:332) {
      paths <- list.files(directory, pattern = "csv", full.names = TRUE)
      p=c()##建一个空向量
      for(i in id) {
        data <- read.csv(paths[i])
        p1 <- data[ ,pollutant]
        p <- c(p1,p)    
      }
      mean(p,na.rm=TRUE)## “id”向量中的 (忽略 NA值)
    }
