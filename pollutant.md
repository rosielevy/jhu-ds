*mean function returning NA - not numeric or logical*

```
pollutantmean <- function(directory, pollutant, id = 1:332) {
      files_full <- list.files(directory, full.names = T)
      data <- data.frame()
      for (i in id) {
            data <- rbind(data, read.csv(files_full[i]))
      }
      mean(data$pollutant, na.rm=T)
      
}
```



