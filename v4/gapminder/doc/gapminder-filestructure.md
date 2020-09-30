# Gapminder filestructure

```
├── gapminder
│   ├── index.html #tabbed version of the visualization
│   ├── basic_gapminder_graph.html #the basic stand-alone gapminder graph 
│   ├── css
│   │   ├── style.css #style for visualization
│   │   ├── tab_style.css #style for index.html page
│   ├── files #files for different kinds of data for gapminder
│   |   ├── annotations #annotation files
│   │   |   ├── annotations_test.json
│   │   |   ├── annotations_test01.json #currently used in index.html
│   |   ├── config #configuration files
│   │   |   ├── config00.json
│   │   |   ├── config01.json
│   │   |   ├── County_Pop_GPCD_config.csv
│   │   |   ├── County_Pop_GPCD_config.json
│   │   |   ├── County_Population_WaterUse_GPCD_config.json
│   │   |   ├── Provider_Population_Wateruse_GPCD_config.json #currently used in index.html
│   |   ├── data #water data files
│   │   |   ├── County_Pop_GPCD_rmv_outliers.csv
│   │   |   ├── County_Pop_GPCD_test2.csv
│   │   |   ├── County_Population_WaterUse_GPCD.csv
│   │   |   ├── County_Population_WaterUse_GPCD_rmout.csv
│   │   |   ├── Provider_Population_WaterUse_GCPD.csv #currently used in index.html
│   │   |   ├── Provider_Population_WaterUse_GCPD_rmout.csv
│   │   |   ├── Provider_Population_WaterUse_GCPD01.csv
│   |   ├── metadata #json metadata file
│   │   |   ├── jsonMeta
│   |   ├── test_files #test files 
│   │   |   ├── exampleJSON00.json
│   │   |   ├── exampleJSON01.json
│   │   |   ├── jsonFile.json
│   │   |   ├── test00.csv
│   │   |   ├── test01.csv
│   │   |   ├── test02.csv
│   ├── javascript
│   │   ├── data.js 
│   │   ├── gapminder.js #the actual d3.js gapminder graph
│   │   ├── jquery-3.2.0.min.js
│   │   ├── papaparse.min.js
```
