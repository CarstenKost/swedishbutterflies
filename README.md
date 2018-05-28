[![Build Status](https://travis-ci.org/rekonstrukt/swedishbutterflies.svg?branch=master)](https://travis-ci.org/rekonstrukt/swedishbutterflies)

<!-- README.md is generated from README.Rmd. Please edit that file -->
`swedishbutterflies` is an R package for SeBMS - the Swedish Butterfly Monitoring Scheme - offering tools for accessing data, making plots and a Shiny app.

Installing from github
----------------------

If you want to install the latest version:

``` r
# First make sure you have the devtools package
# which simplifies installations from github
# Note: Windows users have to first install Rtools to use devtools

install.packages("devtools") 
library(devtools)
install_github("rekonstrukt/swedishbutterflies")
```

Quick start
-----------

Load the package in your R environment and create a `config.yml` with the db connection details:

``` r

library(swedishbutterflies)
library(rappdirs)

# location for config.yml with db connection details
app_dir("sebms")$config()
```

Example content that can be used in the `config.yml`:

    default:
      sebms:
        driver: !expr RPostgres::Postgres() 
        server: 'localhost'
        dbuser: !expr Sys.getenv("DBUSER")
        dbpass: !expr Sys.getenv("DBPASS")  
        port: 5432
        database: 'test3'

Before being able to access data from the database, set up the `config.yml` and if you use environment variables in it for uid or password, also set up your `.Renviron` with that content:

``` console
DBUSER = your_db_user
DBPASS = your_db_pwd
```

Then, to see some quick usage examples to get you started, read the Vignette.

Credits
-------

The package bundles code and data assembled and curated by Lars Petterson at <https://dagfjarilar.lu.se>

Meta
----

-   Please [report any issues or bugs](https://github.com/rekonstrukt/swedishbutterflies/issues).
-   License: AGPL
