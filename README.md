# dietaryindex
<img src="https://github.com/jamesjiadazhan/dietaryindex/assets/108076575/53c43fbd-effa-4a43-bf81-79ef4d4514cd" width=350>

___
## Overview
___

**dietaryindex** aims to provide streamlined methods for standardizing the definition of dietary patterns and assessing adherence to dietary patterns in epidemiologic and clinical studies, promoting precision nutrition.

As of version 1.0.2, the package supports the latest version of the Healthy Eating Index (HEI2020) for National Health and Nutrition Examination Survey (NHANES) data. NHANES data from 2005 to 2018 are compiled and available within the dietaryindex package. Data can be accessed with commands like `data("NHANES_20172018")` or `data("NHANES_20152016")`. Also, all NHANES functions allow users to enter the first day data, or the second day data, or first day + second day data and return the results accordingly. 

The **dietaryindex** package performs calculations in two steps:
1. Compute the serving size of each food and nutrient category.
2. Compute the individual dietary index using the serving size information.

This package can calculate the following dietary pattern indexes:
- Healthy Eating Index 2020 (HEI2020 & HEI-Toddlers-2020) 
- Healthy Eating Index 2015 (HEI2015)
- Alternative Healthy Eating Index (AHEI)
- Dietary Approaches to Stop Hypertension Index (DASH)
- DASH Index in serving sizes from the DASH trial (DASHI)
- Mediterranean Diet Index (MED)
- MED Index in serving sizes from the PREDIMED trial (MEDI)
- Dietary Inflammation Index (DII)
- American Cancer Society 2020 diet score (ACS2020_V1 and ACS2020_V2)
- Planetary Health Diet Index from the EAT-Lancet Commission (PHDI)

**dietaryindex** has compiled and included NHANES data from 2005 - 2018 for your convenience. This includes NHANES 2005-2006, NHANES 2007-2008, NHANES 2009-2010, NHANES 2011-2012, NHANES 2013-2014, NHANES 2015-2016, NHANES 2017-2018. To retrieve the data, use the following codes:
- NHANES 2005-2006: data("NHANES_20052006")
- NHANES 2007-2008: data("NHANES_20072008")
- NHANES 2009-2010: data("NHANES_20092010")
- NHANES 2011-2012: data("NHANES_20112012")
- NHANES 2013-2014: data("NHANES_20132014")
- NHANES 2015-2016: data("NHANES_20152016")
- NHANES 2017-2018: data("NHANES_20172018")

For a detailed explanation of these indexes, please check the attached Excel files:
- [dietaryindex_SERVING_SIZE_DEFINITION.xlsx](https://github.com/jamesjiadazhan/dietaryindex/blob/main/dietaryindex_SERVING_SIZE_DEFINITION.xlsx)
- [dietaryindex_SCORING_ALGORITHM.xlsx](https://github.com/jamesjiadazhan/dietaryindex/blob/main/dietaryindex_SCORING_ALGORITHM.xlsx)

Package dependencies: **dplyr**, **readr**, **haven** (automatically installed).


## Installation
___

Currently, **dietaryindex** is not available on [CRAN]

To install from this GitHub repository, use the **devtools** package:

```
install.packages("devtools") #If you don't have "devtools" installed already
devtools::install_github("jamesjiadazhan/dietaryindex") # Install the package from GitHub
# If the previous steps not working, you can try the following steps by removing the "#" marks
# library(devtools) # Load devtools
# install_github("jamesjiadazhan/dietaryindex")
```

If something comes up like this, first try enter 1 in the terminal (lower box). If not successful, then try enter 2. It will take a while if you are a new R user.
```
  These packages have more recent versions available.
  It is recommended to update all of them.
  Which would you like to update?

  1: All                          
  2: CRAN packages only           
  3: None                         
  4: tzdb  (0.3.0 -> 0.4.0) [CRAN]
  5: vroom (1.6.1 -> 1.6.3) [CRAN]
```

## Getting Started
___
To start using dietaryindex, load the package after installation:
```
library(dietaryindex)
```

Detailed function descriptions, examples, and NHANES data access instructions are provided here: [Manual](https://github.com/jamesjiadazhan/dietaryindex/blob/main/Manual.md)


## Related Work
___

**dietaryindex** is mainly intended as a versatile tool to help for calculating different dietary indexes conveniently. It is designed to be flexible to work for almost all types of dietary assessment tools, including food frequency questionnaires, 24-hours dietary recalls, and even food records, while itself supports many 1-step dietary index calculations for NHANES, ASA24, and DHQ3.  Please follow the instruction of your specific dietary assessment tools and relevant articles regarding how to accurately define the serving size (see above) if it is not provided in our package, as they are the key to obtain high-quality dietary indexes. **dietaryindex** also provides some help in defining the serving size in the help file, argument section. Note: some very specific dietary index components (low-fat dairy and sugar sweetened beverage) are not easily available and thus are difficult to assess. The author used individual-level food data to compute the population-level food group data. For example, the sugar sweetened beverage serving is estimated by dividing the total added sugar intakes in grams from beverages by 26, because 1 bottle (8 oz) of Coke has 26 g added sugars and this is used as the benchmark, as different sugar sweetened beverages have largely different added sugar contents. Please use your own judgment to determine if the dietary indexes calculated using the **dietaryindex** package is appropriate for your research.

For NHANES data:

- FPED file refers to the DR1TOT file in the Food Patterns equivalents for foods in the WWEIA (https://www.ars.usda.gov/northeast-area/beltsville-md-bhnrc/beltsville-human-nutrition-research-center/food-surveys-research-group/docs/fped-databases/). This is a exe zip file, so please unzip this file first to retrieve the SAS file. 

- NUTRIENT file refers to the DR1TOT file in the Dietary Interview - Total Nutrient Intakes, First Day, Dietary Data (example: 05-06 https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Dietary&CycleBeginYear=2005). 

- DEMO file refers to the DEMO file in the Demographic Variables & Sample Weights (example: 05-06 https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Demographics&CycleBeginYear=2005)

FPED, NUTRIENT, and DEMO files are available in the Google Drive collected by the package developer for your convenience (https://drive.google.com/drive/folders/1umjhuS22aHEW_bU5AjYa8vrae91gsb0D?usp=share_link). 

### Contributing & Notes
**dietaryindex** is licensed under the [MIT License](https://github.com/jamesjiadazhan/dietaryindex/blob/main/other/LICENSE.txt). Please check out the [Contribution guide](https://github.com/jamesjiadazhan/dietaryindex/blob/main/CONTRIBUTING.md) for questions, feature requests and bug reports. The maintainer will review pull requests and incorporate contributions at his discretion. You may also reach out to the maintainer, **James Jiada Zhan**, via his email: jzha832@emory.edu. **James Jiada Zhan** home page at Emory is: https://www.sph.emory.edu/phd-students/profile/index.php?FID=jiada-zhan-12906. **Becky Hodge** provided significant contributions to validate this package. Thanks a lot for her help. 
