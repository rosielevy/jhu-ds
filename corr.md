__corr work in progress__

```
corr<-function(directory,threshold = 0){
      
      files_full <- list.files(directory,full.names = T)
      
      nob <- numeric()
      
      corr <- c()
      
      for(i in 1:332){
            
            data <- read.csv(files_full[i])
            
            nob <- sum(complete.cases(data))
            
            if(nob > threshold) {
                  
                  cleandata<- na.omit(data)
                  cleandatan <- cleandata$nitrate
                  cleandatas <- cleandata$sulfate
                  corr <- c(corr, cor(cleandatan, cleandatas, use = "complete.obs")) 
                  
            }
            
      }
      
      corr
      
}

#returning 0 as first value?
```
