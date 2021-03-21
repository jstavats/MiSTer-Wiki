# Temporary quick introduction

Cores need to be update with new framework. Cores released from 2020/06/18 and later should support audio filters.
Filter setting files should be placed into `Filters_Audio`
Each file is simple text file with extension `txt`.
Example of filter file:
```
# version
v1

# sampling frequency
# must be multiple of 48000 for best results
7056000

#base gain
0.00000316778645516‬

#gain scale for X0
2

#gain scale for X1
1

#gain scale for X2
0

#coefficient for Y0
-1.9974813602

#coefficient for Y1
0.9974845280

#coefficient for Y2
0
```