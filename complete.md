__complete__

```
complete<-function(directory,id=1:322){
      
      files_full <- list.files(directory,full.names = T)
      
      nob <- numeric()
      
      for(i in id){
            data <- data.frame()
            
            data <- read.csv(files_full[i])
            
            nob <- rbind(nob,sum(complete.cases(data)))
            
            
      }
      
      data.frame(id, nobs = nob)
      
}
```
