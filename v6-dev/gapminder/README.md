# Gapminder
This gapminder visualization requires an input data set of .csv format, that contains a header with variable names. The expected data format will contain at least 6 columns; although fewer may be provided if the same data are re-used where it seems appropriate.     
For example, it is possible to group the markers by the same data as the labels for specific markers. 6 columns is preferable, however, for a configuration that utilizes the visualization to it's fullest extent.

For more detail on the data file see [CSV file](Gapminder-‐-CSV-Data-File)

#### Configuration:
The Gapminder visualization requires that a configuration file is specified at the top of [index.html](Gapminder-‐-index.html).

```html
<script> ConfigurationFile = "path/to/configuration_file"; </script>
```

These configuration properties specify necessary information that the Gapminder Visualization requires to operate, as well as offers the user many options for customizing the visualization to meet their preferences.
This visualization was developed, and based off of,  [The Health & Wealth of Nations](https://bost.ocks.org/mike/nations/), created by [Mike Bostock](https://bost.ocks.org/mike/).

For more detail on the configuration file see [Configuration File](Gapminder-‐-configuration-file).

Given the appropriate input data and configuration file, the gapminder visualization should now be ready to deploy, which will result in a visualization as seen below.

This project is open source and can be cloned for deployment as well as development.

![Gapminder - Sample Chart](https://raw.githubusercontent.com/wiki/OpenWaterFoundation/owf-lib-viz-d3-js/images/Gapminder%20-%20Snodas.PNG?token=AQ9qWmuOeDr2qBKlyDSKL0mATfjNrU3yks5aqrhSwA%3D%3D)

## Deploy Gapminder

To deploy this visualization first see [Getting Started](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js#getting-started), for information about cloning the repository and running a local server to view in a web browser.

Files necessary for deploying Gapminder are all contained within the sub-folder [site](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/tree/master/v4/gapminder/site). To run the visualization with new data you must first create a [configuration file](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-configuration-file) and specify the location of that file in [index.html](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-index.html#configuration-file). 

## Development
### Documentation:
#### owf-lib-viz-d3-js wiki
### [Gapminder](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder) 
#### **Html Files**
  * [index.html](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-index.html)
  * [highchart.html](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-highchart.html) 
  * [developer-tools.html](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-developer-tools.html) 
#### **Data files**
   * [Configuration File](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-configuration-file)
   * [CSV File](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-CSV-Data-File)
#### **Javascript Files**
   * [gapminder-*.js](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/gapminder-4.0.0.js)
     
See also [Contributing](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js#contributing).  
	
## Resources/Credits  

[D3.js v4 API](https://github.com/d3/d3/blob/master/API.md)  
[Health & Wealth of Nations](https://bost.ocks.org/mike/nations/) - [Mike Bostock](https://bost.ocks.org/mike/)  
[Bootstrap](http://getbootstrap.com/)  
[Select2](https://select2.github.io/)  
[slider: days of the year](http://bl.ocks.org/zanarmstrong/ddff7cd0b1220bc68a58)  
[Drag Slider](https://bl.ocks.org/mbostock/6452972)  
[Clusterize](https://clusterize.js.org/)
