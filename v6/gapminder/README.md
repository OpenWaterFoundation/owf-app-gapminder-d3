# Gapminder
This gapminder visualization requires an input data set of .csv format, that contains a header with variable names. The expected data format will contain at least 6 columns; although fewer may be provided if the same data are re-used where it seems appropriate.     
For example, it is possible to group the markers by the same data as the labels for specific markers. 6 columns is preferable, however, for a configuration that utilizes the visualization to it's fullest extent.

For more detail on the data file see [CSV file](Gapminder-‐-CSV-Data-File)

This project is open source and can be cloned for deployment as well as development.

![Gapminder - Sample Chart](https://raw.githubusercontent.com/wiki/OpenWaterFoundation/owf-lib-viz-d3-js/images/Gapminder%20-%20Snodas.PNG?token=AQ9qWmuOeDr2qBKlyDSKL0mATfjNrU3yks5aqrhSwA%3D%3D)



### Gapminder Fundementals  

#### Configuration:

These configuration properties specify necessary information that the Gapminder Visualization requires to operate, as well as offers the user many options for customizing the visualization to meet their preferences. 

This visualization was developed, and based off of, [The Health & Wealth of Nations](https://bost.ocks.org/mike/nations/), created by [Mike Bostock](https://bost.ocks.org/mike/).

The Gapminder visualization requires that a configuration file is specified within logic file of the Gapminder:

This path can either be hard coded or provided through top level configuration.

```
let configurationFile = "path/to/configuration_file"; 
```

The configuration file must be of [JSON](https://www.json.org/) format. The file should contain a single JSON structure as follows:

```
{
   "Properties":{ 
            "ConfigurationProperty" : "Property Value" 
    }
}
```

These configuration properties specify necessary information that the Gapminder Visualization requires to operate, as well as offers the user many options for customizing the visualization to meet their preferences.

For more detail on the configuration file see [Configuration File](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-configuration-file).

#### CSV File Format:

This gapminder visualization requires an input data set of .csv format, that contains a header with variable names. The expected data format will contain at least 6 columns; although fewer may be provided if the same data are re-used where it seems appropriate.
For example, it is possible to group the markers by the same data as the labels for specific markers. 6 columns is preferable, however, for a configuration that utilizes the visualization to it's fullest extent.

For more detail on the data file see [CSV file](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-CSV-Data-File)

#### Annotations File Format:

The Gapminder visualization has the ability to configure annotations . These annotations are able to provide relevant information on certain dates, or data. Specifying an annotations file is optional, and can be omitted from configurations.

General annotations will be displayed in a text box at the lower right corner of the visualization, when animating to the specified date.

Annotations must be specified within the [configuration file](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-‐-configuration-file) by providing the path to the respected annotations file.  Additionally you may also specify whether or not to initially display [specific annotation shapes](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-‐-annotations-file#specific-annotations) on page load.

`` assets/gapminder-data/viz-config.json: ``

```
{
    "Properties":{
         "AnnotationsFileName":"./data/annotations.json",
         "AnnotationShapes":"On"
    }
}
```

As with the CSV file, the annotations file must be of [JSON](https://www.json.org/) format with `date` as the `key`, and a nested JSON object as the `value`. The nested JSON object must specify two properties `Title` and `Description`.

`` assets/gapminder-data/annotations.json: ``

```
{
     "Annotations":{
          "GeneralAnnotations":{
               "2002":{
                    "Title":"Drought",
                    "Description":"Colorado has experienced widespread, severe drought since the late 1800s.  As of 2013, the drought of 2002 is considered the worst single year drought on record in Colorado‘s history. Statewide snowpack was at or near all-time lows. What made 2002 so unusual was that the entire state was dry at the same time.  These conditions were rated exceptional by the U.S. Drought Monitor and were the most severe drought conditions experienced in the region since the Dust Bowl in the 1930s. During 2011-2013, some regions throughout southeastern Colorado have experienced persistent severe to exceptional drought conditions that are comparable to conditions seen during both the 2002 drought and the Dust Bowl of the 1930s."
	        }
          }
     }
}
```

For more detail on annotations see [Annotations File](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/wiki/Gapminder-%E2%80%90-annotations-file#specific-annotations)

_______________________________

## Gapminder V4 => V6 Updates

### [ ``gapminder-6-1-1.js`` ]:

This file adds to the logic that defines the Gapminder component and specifies where all the visualization/animation elements are added to the DOM through the use of [D3.js](https://d3js.org/).

It is important to note that with the update of D3 from V4 to V6 comes exciting new features and improvements!

Relevant changes: 

**d3-selection** has a new event manager:

- d3.event ⇨ (event) passed as the first argument to all listeners [[details](https://observablehq.com/@d3/d3v6-migration-guide#events)]

  ```
  
  ```

**d3-collection** is deprecated, and its methods are replaced:

- d3.nest ⇨ d3.group and d3.rollup (from d3-array) [[details](https://observablehq.com/@d3/d3v6-migration-guide#group)]

- d3.map ⇨ Map [[details](https://observablehq.com/@d3/d3v6-migration-guide#collection)]

- d3.set ⇨ Set [[details](https://observablehq.com/@d3/d3v6-migration-guide#collection)]

- d3.keys ⇨ Object.keys [[details](https://observablehq.com/@d3/d3v6-migration-guide#collection)]

- d3.values ⇨ Object.values [[details](https://observablehq.com/@d3/d3v6-migration-guide#collection)]

- d3.entries ⇨ Object.entries [[details](https://observablehq.com/@d3/d3v6-migration-guide#collection)]

  ```
  
  ```

Refer to the full [D3 6.0 Migration guide](https://observablehq.com/@d3/d3v6-migration-guide) for an detailed look at important API changes.

_________________

Given the appropriate input data and configuration file, the gapminder visualization should now be ready to deploy, which will result in a visualization as seen with this example.

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
