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
  
####Date and Time  
- Dates and times have special classes in R that allow for numerical and statistical calculations  
- Dates use the Date class  
- Times use the POSIXct and POSIXlt class  
- Character strings can be coerced to Date/Time classes using the strptime function or the as.Date, as.POSIXlt, or as.POSIXct  
- 
