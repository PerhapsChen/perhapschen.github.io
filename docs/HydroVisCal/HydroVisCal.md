# HydroVisCal

?> `HydroVisCal` (**Hydro**logy **Vis**ualization & **Cal**culation) is a `Python` package maintained by me. 

在科研计算中，经常会需要编写大量的计算和可视化的代码以达到我们期望的效果。例如，当我们想要画一幅折线图，需要调整各种绘图细节参数，这些参数可能分布在不同行的代码中，尤其是参数较多的时候并不是特别方便。更加泛用的代码能更显著提高我们的工作效率，因此，未解决上述问题，我着手编写了一系列类和函数，方便更高效的进行科研的计算和可视化。它们大部分采用数据和逻辑分离的方式，使用Json统一管理参数，进而让我们的工程代码文件更加简洁，逻辑更加清晰。让我们可以把更多的时间留给科学问题的思考，而不是繁琐的代码参数调整。在某些情况下，这些代码能够数倍提高我们的工作效率。

<!-- In scientific research, especially when it comes to computing and visualisation, we often need to write special code for our scientific tasks. And the parameters need to be adjusted frequently to achieve the results we expect. Therefore, I have written some of the frequently used functional code in a more general form. In the future, this code will increase the efficiency of my work several times over. -->

### Generic Modules

- **HYDRO_Generate**:  Used to generate some test data from scratch
- **HYDRO_Plot**: Used for visualisation, e.g. box plots, trend plots  of multiple subplots, etc.
- **HYDRO_MapPlot**: Used for mapping, including multiple submaps of maps and processing shp files
- **HYDRO_Time**: Used to process time series data
- **HYDRO_Format**: Used for conversion and export of various formats such as `nc`, `tif`, etc.
- **HYDRO_MultiProcess**: Some Python multi-processing, multi-thread functions
- **HYDRO_AI**: Some machine learning and deep learning related functions
- ...

### Scientific Modules

- ...

# HYDRO_Plot

方便绘制使用`Json`**高度定制**的折线图、箱线图、热力图等。不包括地图，地图可以参考`HYDRO_MapPlot`

