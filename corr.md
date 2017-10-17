__corr work in progress__

```
corr<-function(directory,threshold = 0){
      
      files_full <- list.files(directory,full.names = T)
      
      nob <- numeric()
      
      corr <- vector(mode = "numeric", length = 0)
      
      for(i in 332){
            
            data <- read.csv(files_full[i])
            
            nob <- sum(complete.cases(data))
            
            if(nob > threshold) {
                  
                  cleandata<- na.omit(data)
                  keeps <- c("sulfate", "nitrate")
                  cleandatasub <- cleandata[keeps]
                  corr <- rbind(cor(cleandatasub))           
            }
            
      }
      
      corr
      
}
```
