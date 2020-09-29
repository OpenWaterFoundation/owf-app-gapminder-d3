# owf-app-gapminder-d3 #

**This repository is a work in progress.
The OWF team is evaluating the best way to develop D3.js-based Gapminder that can 
be used stand-alone and with Angular applications.  Challenges include:**

* **How to support agile development of the core Gapminder visualization component,
to encourage maintenance and enhancements and keep up to date with d3.js?**
* **How to allow the resulting Gapminder component to be included in stand-alone
visualization applications, Angular applications, and other configurations that
are not constrained by the Gapminder?**
* **How to allow development with various datasets from implementations,
without including all the data from those implementations in this repository?
It is OK to include test data here but also want to be able to test with full
implementation data in a nimble way.**
* **Should we be using some type of "live server" to detect changes so it is
easier to share files from repos during development?**

Open Water Foundation (OWF) GapMinder web application visualizes time series
as animated D3.js "bubble plot" with multiple data variables.

* [Introduction](#introduction)
* [Repository Contents](#repository_contents)
	+ [Stand-alone Gapminder Visualization (Full Developer Mode)](#single-topic-gapminder-visualization-full-developer-mode)
	+ [Stand-alone Gapminder Visualization (Web Developer Mode)](#single-topic-gapminder-visualization-web-developer-mode)
	+ [Integrated Gapminder Angular Application (Full Developer Mode)](#integrated-gapminder-angular-application-full-developer-mode)
	+ [Integrated Gapminder Angular Application (Angular Application Developer Mode)](#integrated-gapminder-angular-application-angular-application-developer-mode)
* [Getting Started](#getting-started)
	* [Running the Project](Running the Project)
* [Deploying the Site to Amazon Web Servers](#deploying-the-site-to-amazon-web-servers)
* [Contributing](#contributing)
* [Maintainers](#maintainers)
* [License](#license)
* [Resources](#resources)

## Introduction ##

This repository contains the files for developing and deploying the OWF "Gapminder" application.
The Gapminder is an implementation of the [Gapminder.org tool](https://www.gapminder.org/)
developed using the [D3.js](https://d3js.org/) JavaScript library.
A D3 approach was taken because no suitable solution was available at the time and D3 provided a dynamic option,
and even today there may not be an appropriate solution from Gapminder.org that can be used
(may need to evaluate this).

A previous iteration of this software is saved in the
[owf-lib-viz-d3.js](https://github.com/OpenWaterFoundation/owf-lib-viz-d3-js/tree/master/v4/gapminder) repository,
which assumed that multiple D3.js tools could be maintained together over time.
However, continuing a D3 repository for multiple tools is problematic for a number of reasons:

* not all tools are being used and updated at the same rate
* the Gapminder tool is complex and has been used more often, requiring special handling,
which has led to copying the original code into other repositories and subsequent modifications of the copy
(which complicates maintenance)

Consequently, this repository has been created to focus on Gapminder.
The following are possible implementations of Gapminder:

1. Stand-alone web pages, similar to previous Gapminder implementations.
See the [Single Topic Gapminder Visualization](#single-topic-gapminder-visualization) section below.
2. Embedding a Gapminder web page in another website.
This has been done in the past, although on a limited basis.
3. Linking a stand-alone Gapminder web page to InfoMapper application (parallel implementations).
This is similar to item 1, with appropriate software and data file management.
4. Integrating Gapminder in an InfoMapper application (such as popup with Gapminder visualization).
For example reuse the Gapminder software for multiple time series inputs within an Angular application.
See the [Integrated Gapminder Angular Application](#integrated-gapminder-angular-application)
section below.

In all cases, it is desirable to automate creation of input data and configuration if possible in order
to efficiently scale a visualization.
TSTool software functionality is being evaluated for data preparation, including the following options:

* Use existing functionality and add commands if necessary to create GapMinder time series data files
and configuration file, specific to Gapminder.
* Rely on template processing functionality,
which requires more editing of configuration files outside of TSTool command.

## Repository Contents ##

The following folder structure is recommended for development.
Top-level folders should be created as necessary.
The following folder structure clearly separates user files (as per operating system),
development area (`owf-dev`), product (`App-InfoMapper`),
repositories for product (`git-repos`), and specific repositories for the product.
Repository folder names should agree with GitHub repository names.
Scripts in repository folders that process data should detect their starting location
and then locate other folders based on the following convention.

```
C:\Users\user\                                 User's home folder for Windows.
/c/Users/user/                                 User's home folder for Git Bash.
/cygdrive/C/Users/user/                        User's home folder for Cygwin.
/home/user/                                    User's home folder for Linux.
  owf-dev/                                     Work done on Open Water Foundation projects.
    App-InfoMapper/                            InfoMapper product files (name of this folder is not critical).
      ---- below here folder names should match exactly ----
      git-repos/                               Git repositories for the Angular portal web application.
        owf-app-gapminder-d3/                  D3 Gapminder web application.
```

This repository contains the following main folders and files.
**Need to figure out how to allow developing Gapminder with dependency on D3.js and its
dependencies, while packaging into an `owf-gapminder.js` that can be distributed.**

```
owf-app-gapminder-d3/
  build-util/                                 Scripts to manage repository, as needed.
  gapminder/                                  Software development files for the InfoMapper.
  .git/                                       Standard Git software folder for repository (DO NOT TOUCH).
  .gitattributes/                             Standard Git configuration file for repository (for portability).
  .gitignore/                                 Standard Git configuration file to ignore dynamic working files.
  README.md                                   This readme file.
  site/                                       Location where website files exist, including data and configuration
                                              for Gapminder.
    assets/                                   Data and other assets for Gapminder visualiation,
                                              gitignored since in development will be copied from
                                              workflow/ for built-in examples,
                                              or copied from other repositories to test other implementations.
  src/                                        Location of Gapminder source files.
  workflow/                                   Workflow to create and copy examples into site folder.
```

### Stand-alone Gapminder Visualization (Full Developer Mode) ###

**This describes a developer mode approach where code for all components may be developed.**

Single topic websites that implement the Gapminder as the primary visualization tool
should typically have a folder structure similar the following,
where the Gapminder is used in a supporting role to implement a visualization.
In the future, an installer for Gapminder will be provided so that a repository clone is not required.
**How easy is it to create a file to distribute Gapminder?  Should the following rely
on owf-app-gapminder-d3 clone or the js file that results from that?**

```
C:\Users\user\                          User's home folder for Windows.
/c/Users/user/                          User's home folder for Git Bash.
/cygdrive/C/Users/user/                 User's home folder for Cygwin.
/home/user/                             User's home folder for Linux.
  owf-dev/                              Work done on Open Water Foundation projects.
    GapMinder-CoSnodas/                 Project that uses Gapminder software to implement a website.
      ---- below here folder names should match exactly ----
      git-repos/                        Git repositories for the Angular portal web application.
        owf-app-gapminder-d3/           Gapminder web application containing test visualizations.
          site/                         Location of stand-alone website, gitignored.
        owf-viz-co-snodas-gapminder/    Workflow files to process input for Colorado SNODAS
                                        data visualization.
                                        THIS IS A LEGACY REPOSITORY USING OLD GAPMINDER CODE.
        owf-gapminder-co-snodas/        MAY RENAME OR CREATE A NEW REPO WITH THIS NAME.
          web/                          Location of stand-alone web files, to be copied into 'site',
                                        gitignored except for scripts and static files.
          workflow/                     Location of workflow files to process data into 'web',
                                        gitignored except for workflow configuration and static files.
```

The following table lists deployed websites and corresponding implementation repositories
that illustrate this configuration.

| **Website** | **Content Generation Repository** |
| -- | -- |
| TBD | ? not sure |

### Stand-alone Gapminder Visualization (Web Developer Mode) ###

**This describes how to develop with GapMinder if only source for the stand-alone applidation code is needed,
where Gapminder is distributed in final form such as `js` file.  Need to figure out.**

The following table lists deployed websites and corresponding implementation repositories
that illustrate this configuration.

| **Website** | **Web Application Repository** |
| -- | -- |
| TBD | For example owf-viz-co-snodas-gapminder? |

### Integrated Gapminder Angular Application (Full Developer Mode) ###

**This describes a developer mode approach where code for all components may be developed.**

Integated Gapminder/Angular applications use Gapminder to provide a visualization within
a larger Angular application, such as the InfoMapper.
In this case, the Gapminder is a software component similar to other components used by the Angular application.
The Angular application should typically have a folder structure similar the following,
where the Gapminder is used in a supporting role to implement a visualization.
In the future, an installer for Gapminder will be provided so that a repository clone is not required.
However, when actively developing on the Gapminder it is helpful to use the clone.

```
C:\Users\user\                                 User's home folder for Windows.
/c/Users/user/                                 User's home folder for Git Bash.
/cygdrive/C/Users/user/                        User's home folder for Cygwin.
/home/user/                                    User's home folder for Linux.
  owf-dev/                                     Work done on Open Water Foundation projects.
    InfoMapper-Poudre/                         Angular product that uses Gapminder software to
                                               implement a visualization.
      ---- below here folder names should match exactly ----
      git-repos/                               Git repositories for the Angular portal web application.
        owf-app-gapminder-d3/                  Gapminder web application for core Gapminder development.
                                               HOW ARE FILES DEVELOPED HERE PACKAGED AND DEPLOYED/TESTED
                                               IN THE FULL ANGULAR APPLICATION?
                                               - as npm package (would be nice but what is involved
                                                 and do we want to support publicly since a custom component)?
                                               - as assets files (ugly since it mixes software with data)
                                               - something else?
        owf-app-infomapper-ng/                 Angular InfoMapper web application (may or may not require enhancement).
          infomapper/src/assets/app/           Location of deployed web application.
        owf-infomapper-poudre/                 Workflow files to process input for web application,
                                               deployed to folder above via copy during live development.
```

The following table lists deployed websites and corresponding implementation repositories
that illustrate this configuration.

| **Website** | **Angular Application Repository** |
| -- | -- |
| TBD | Maybe just owf-app-viz-demo-ng? |

### Integrated Gapminder Angular Application (Angular Application Developer Mode) ###

**This describes how to develop with GapMinder if only source for the Angular application is needed,
where Gapminder is distributed in final form such as `npm` package.  Need to figure out.**

The following table lists deployed websites and corresponding implementation repositories
that illustrate this configuration.

| **Website** | **Angular Application Repository** |
| -- | -- |
| TBD | For example owf-infomapper-poudre or owf-app-infomapper-ng? |

## Getting Started ##

Just clone the repository?

### Running the Project ###

Explain how to run the application and use test data.

## Deploying the Site to Amazon Web Servers ##

A Gapminder application is typically installed using a shell script
with Git Bash, Cygwin, or Linux.

```
copy-to-owf-amazon-s3.bat
```

Need to to provide a link to a specific implementation.

## Contributing ##

Contributions can be made via normal Git/GitHub protocols:

1. Those with commit permissions can make changes to the repository.
2. Use GitHub Issues to suggest changes (preferred for small changes).
3. Fork the repository and use pull requests.
Any pull requests should be based on current master branch contents.

## Maintainers ##

The Gapminder is maintained by the Open Water Foundation.

## License ##

The license is being determined.
Need to research the origin of the software - was some code copied from another project external to OWF?

## Resources ##

* [D3.js](https://d3js.org/)
* [d3 GitHub repository](https://github.com/d3/d3)
* ["D3 is not a Data Visualization Library"](https://medium.com/@Elijah_Meeks/d3-is-not-a-data-visualization-library-67ba549e8520)
* [D3 Gallery](https://observablehq.com/@d3/gallery)
