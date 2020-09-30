# Gapminder Basic Site
This folder contains everything necessary to deploy a basic example of Gapminder as a static web page, with tabbed panels for viewing different data views as it related to the gapminder visualization.

### Tabs:
1. Visualization: Displays the Gapminder/Visualization.
2. Data: Displays data that is fed into the Gapminder Visualization formatted as a table
3. Documentation: Displays user Documentation on how to use the various elements of the visualization.
4. Sources: Displays short list of sources used in creating the Gapminder visualization.

## Folder Structure

```
├── site/..........................................................(Visualization website files - can stand alone as website.)
|   ├── css/.......................................................(CSS files for website.)
|   |   ├── bootstrap.min.css......................................(Style for bootstrap.js.)
|   |   ├── clusterize.css.........................................(Style for clusterize.js.)
|   |   ├── highchart.css..........................................(Style for highchart.html.)
|   |   ├── loader.css.............................................(Style for loading symbol on page load.)
|   |   ├── select2.min.css........................................(CSS for dropdown selector, using select2 in gapminder-*.js.)
|   |   ├── style.css..............................................(Style for index.html.)
|   ├── data/......................................................(Data files for website. Must run TS-tool to get all data files)
|   |   ├── annotations.json.......................................(Annotation data file for sample data.)
|   |   ├── sample-data.csv........................................(A sample csv file that contains only a few number of data points from a larger data set.)
|   |   ├── viz-config.json........................................(A configuration file for Gapminder Visualization.)
|   ├── fonts/.....................................................(Bootstrap fonts distributed with visualization.)
|   |   ├── glyphicons-halflings-regular.eot..................................................................................
|   |   ├── glyphicons-halflings-regular.svg..................................................................................
|   |   ├── glyphicons-halflings-regular.ttf..................................................................................
|   |   ├── glyphicons-halflings-regular.woff.................................................................................
|   |   ├── glyphicons-halflings-regular.woff2................................................................................
|   ├── images/....................................................(Images used in the visualization.) 
|   ├── javascript/................................................(Javascript files for website.)
|   |   ├── bootstrap.min.js.......................................(Bootstrap javascript file.)
|   |   ├── clusterize.js..........................................(Clusterize javascript file used for creating data table.)
|   |   ├── data-class.js......................................... (Initiliazes different data objects form the configuration file.)
|   |   ├── data.js................................................(Javascript file that makes data table when clicking on data tab.)
|   |   ├── developer-tools.js.....................................(Strictly used for devlopment/debugging purposes.)
|   |   ├── display-data.js........................................(Called when clicking on 'data' tab to display the csv file.)
|   |   ├── expand-parameter.js....................................(Javascript file used to insert data set values into a property value that is used in looking up separate data sets when dealing with multiple files.)
|   |   ├── gapminder-4.0.0.js.....................................(Javscript file that creates/initializes all of the visualization attributes.)
|   |   ├── highstock.js...........................................(Used in creating a timeseries chart in highchart.html.)
|   |   ├── highstock.src.js.......................................(Used in creating a timeseries chart in highchart.html.)
|   |   ├── jquery-3.2.0.min.js....................................(JQuery javascript file.)
|   |   ├── papaparse.js...........................................(Used to parse through the csv file.)
|   |   ├── properties.js..........................................(Used in creating a property object from configuration file to access different configured values.)
|   |   ├── select2.min.js.........................................(Javascript for dropdown selector, using select2 in gapminder-*.js.)
│   ├── index.html
│   ├── highchart.html
│   ├── developer-tools.html
```

## developer-tools.html
This is a static web-page that is used for testing and debugging purposes from a development standpoint. When specified in the configuration file the developer can have access to a pop-up window that offers insight into the different values of importance in the gapminder visualization.

[documentation](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-developer-tools.html)

## highchart.html
This is a static web-page that utilizes [highcharts](https://www.highcharts.com/) to display a time-series graph based off the data for the selected item/marker on the visualization.

[documentation](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-highchart.html)

## index.html
This is the landing page for the sunburst visualization site. This page contains the basic outline for the visualization elements which are added to the DOM using the tools provided by D3.js. Also in this file is the information for the `Documentation`, `Data`, and `Sources` tabs.  

[documentation](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-index.html)

## Documentation
#### owf-lib-viz-d3-js wiki:

#### [Gapminder](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder) 
#### **Html Files**
   * [index.html](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-index.html)
   * [highchart.html](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder) 
   * [developer-tools.html](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-developer-tools.html) 
#### **Data files**
   * [Configuration File](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-configuration-file)
   * [CSV File](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-CSV-Data-File)
   * [Annotations File](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-annotations-file)
#### **Javascript Files**
   * [gapminder-4.0.0.js](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/gapminder-4.0.0.js)
