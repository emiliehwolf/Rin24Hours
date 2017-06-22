# The Basics

### The R Environment (Chapter 2)
```r
search()
```
```
 [1] ".GlobalEnv"        "tools:rstudio"     "package:stats"    
 [4] "package:graphics"  "package:grDevices" "package:utils"    
 [7] "package:datasets"  "package:methods"   "Autoloads"        
[10] "package:base"     
```

```r
searchpaths()
```
```
 [1] ".GlobalEnv"                                                              
 [2] "tools:rstudio"                                                           
 [3] "/Library/Frameworks/R.framework/Versions/3.3/Resources/library/stats"    
 [4] "/Library/Frameworks/R.framework/Versions/3.3/Resources/library/graphics" 
 [5] "/Library/Frameworks/R.framework/Versions/3.3/Resources/library/grDevices"
 [6] "/Library/Frameworks/R.framework/Versions/3.3/Resources/library/utils"    
 [7] "/Library/Frameworks/R.framework/Versions/3.3/Resources/library/datasets" 
 [8] "/Library/Frameworks/R.framework/Versions/3.3/Resources/library/methods"  
 [9] "Autoloads"                                                               
[10] "/Library/Frameworks/R.framework/Resources/library/base"              
```

```r
objects(4)
```
```
 [1] "abline"          "arrows"          "assocplot"       "axis"           
 [5] "Axis"            "axis.Date"       "axis.POSIXct"    "axTicks"        
 [9] "barplot"         "barplot.default" "box"             "boxplot"        
[13] "boxplot.default" "boxplot.matrix"  "bxp"             "cdplot"         
[17] "clip"            "close.screen"    "co.intervals"    "contour"        
[21] "contour.default" "coplot"          "curve"           "dotchart"       
[25] "erase.screen"    "filled.contour"  "fourfoldplot"    "frame"          
[29] "grconvertX"      "grconvertY"      "grid"            "hist"           
[33] "hist.default"    "identify"        "image"           "image.default"  
[37] "layout"          "layout.show"     "lcm"             "legend"         
[41] "lines"           "lines.default"   "locator"         "matlines"       
[45] "matplot"         "matpoints"       "mosaicplot"      "mtext"          
[49] "pairs"           "pairs.default"   "panel.smooth"    "par"            
[53] "persp"           "pie"             "plot"            "plot.default"   
[57] "plot.design"     "plot.function"   "plot.new"        "plot.window"    
[61] "plot.xy"         "points"          "points.default"  "polygon"        
[65] "polypath"        "rasterImage"     "rect"            "rug"            
[69] "screen"          "segments"        "smoothScatter"   "spineplot"      
[73] "split.screen"    "stars"           "stem"            "strheight"      
[77] "stripchart"      "strwidth"        "sunflowerplot"   "symbols"        
[81] "text"            "text.default"    "title"           "xinch"          
[85] "xspline"         "xyinch"          "yinch"          
```

```r
objects("package:graphics")
```
```
 [1] "abline"          "arrows"          "assocplot"       "axis"           
 [5] "Axis"            "axis.Date"       "axis.POSIXct"    "axTicks"        
 [9] "barplot"         "barplot.default" "box"             "boxplot"        
[13] "boxplot.default" "boxplot.matrix"  "bxp"             "cdplot"         
[17] "clip"            "close.screen"    "co.intervals"    "contour"        
[21] "contour.default" "coplot"          "curve"           "dotchart"       
[25] "erase.screen"    "filled.contour"  "fourfoldplot"    "frame"          
[29] "grconvertX"      "grconvertY"      "grid"            "hist"           
[33] "hist.default"    "identify"        "image"           "image.default"  
[37] "layout"          "layout.show"     "lcm"             "legend"         
[41] "lines"           "lines.default"   "locator"         "matlines"       
[45] "matplot"         "matpoints"       "mosaicplot"      "mtext"          
[49] "pairs"           "pairs.default"   "panel.smooth"    "par"            
[53] "persp"           "pie"             "plot"            "plot.default"   
[57] "plot.design"     "plot.function"   "plot.new"        "plot.window"    
[61] "plot.xy"         "points"          "points.default"  "polygon"        
[65] "polypath"        "rasterImage"     "rect"            "rug"            
[69] "screen"          "segments"        "smoothScatter"   "spineplot"      
[73] "split.screen"    "stars"           "stem"            "strheight"      
[77] "stripchart"      "strwidth"        "sunflowerplot"   "symbols"        
[81] "text"            "text.default"    "title"           "xinch"          
[85] "xspline"         "xyinch"          "yinch"     
```

There are more than a thousand objects in the base package, the last 
one being "zapsmall"
```r
objects("package:base")
tail(objects("package:base"),214)
?zapsmall
x2 <- pi * 100^(-1:3)
x2
```
```
[1] 3.141593e-02 3.141593e+00 3.141593e+02 3.141593e+04 3.141593e+06
```

```r
print(x2, digits = 4)
```
```
[1] 3.142e-02 3.142e+00 3.142e+02 3.142e+04 3.142e+06
```

```r
zapsmall(x2, digits = 4)
```
```
[1]       0       3     314   31416 3141593
```

Remove all objects with either of these commands:
```r
rm(list = objects())
rm(list = ls())
```

```r
list.files()
```
```
"readme.md"        "Rin24Hours.Rproj"
```

```r
getwd()
```
```
[1] "/Users/admin/Programming/Rin24Hours"
```
### Saving Large Objects
The save() function can be used at any time during an R session. For example, it can be used to create custom .RData files containing objects you specify directly. The save() function, along with its counterpart load(), are great for working with very large datasets because the time to load objects stored as .RData files can be an order of magnitude faster than reading data from a CSV file or other formats.


```r
install.packages("mangoTraining")
library(mangoTraining)
objects("package:mangoTraining")
```
```
 [1] "demoData"     "dowJonesData" "drugs"        "emaxData"     "emaxFun"     
 [6] "logisticFun"  "messyData"    "missingPk"    "pkData"       "policyData"  
[11] "qtpk2"        "runData"      "tubeData"     "xpData" 
```

### Chapter 3 - Single-Mode Data Structures
```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

```r

```
```

```

