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

*pokemon example*

```
summarizepokemonstat <- function(directory,func,gen=1:6,stat="Attack",...){
     # read the pokemon files and subset by gen
     thePokemonFiles <- list.files(directory,
                              full.names=TRUE)[gen]
     pokemonData <- lapply(thePokemonFiles,function(x) read.csv(x)[[stat]])
     # unlist to combine into a vector
     theStats <- unlist(pokemonData)
     # calculate the function passed as an argument 
     func(theStats,...)

}
```

