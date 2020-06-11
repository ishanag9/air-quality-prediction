## Air Quality Prediction of Relative Humidity - Regression

The dataset contains 9358 instances of hourly averaged responses from an array of 5 metal oxide chemical sensors embedded in an Air Quality Chemical Multisensor Device. The device was located on the field in a significantly polluted area, at road level. Data were recorded for a period of one year (March 2004 - February 2005) in an Italian city. [(Dataset)](https://archive.ics.uci.edu/ml/datasets/Air+Quality#:~:text=The%20dataset%20contains%209358%20instances,Air%20Quality%20Chemical%20Multisensor%20Device.&text=This%20dataset%20can%20be%20used,Commercial%20purposes%20are%20fully%20excluded.)

## Features

| Date                        | Date (DD/MM/YYYY) |
| --- | --- |
| Time                        | Time (HH.MM.SS) |
| CO(GT)                | True hourly averaged concentration CO in mg/m^3 (reference analyzer) |
| PT08.S1(CO)                | PT08.S1 (tin oxide) hourly averaged sensor response (nominally CO targeted) |
| NMHC(GT) | Non Metanic HydroCarbons concentration in microg/m^3 (reference analyzer) |
| C6H6(GT) | True hourly averaged Benzene concentration in microg/m^3 (reference analyzer) |
| PT08.S2(NMHC) | PT08.S2 (titania) hourly averaged sensor response (nominally NMHC targeted) |
| NOx (GT) | True hourly averaged NOx concentration in ppb (reference analyzer) |
| PT08.S3(NOx) | PT08.S3 (tungsten oxide) hourly averaged sensor response |
| NO2(GT)         | True hourly averaged NO2 concentration in microg/m^3 (reference analyzer) |
| PT08.S4(NO2)         | PT08.S4 (tungsten oxide) hourly averaged sensor response |
| PT08.S5(O3)           | PT08.S5 (indium oxide) hourly averaged sensor response (nominally O3 targeted) |
| T | Temperature in Â°C |
| RH | Relative Humidity (%)|
| AH | AH Absolute Humidity |



## Model and hyper-parameters comparison

|   | Score Default Parameters | ScoreGrid Search | Best Parameters |
| --- | --- | --- | --- |
| ﻿Linear Regression | ﻿88.24 | ﻿88.19 | ﻿fit\_intercept: True, normalize: True |
| ﻿ Random Forest | ﻿99.76 | 99.82 | ﻿max \_features: &#39;auto&#39;, n\_estimators: 30} |
| ﻿ SVM | ﻿96.26 | ﻿94.86 | ﻿degree: 3, kernel: rbf |
| ﻿ Polynomial Regression | ﻿99.24 | ﻿99.20 | ﻿fit\_intercept: True, &#39;normalize&#39;: True |

## Conclusions

- Random Forests and Polynomial Regression did a great job predicting relative humidity.
- Since the default parameters already did a great job, there was no room left for improvement of the models with the help of grid search.
- Based on the correlation between the variables and the target, removal of less correlated variables did not improve the accuracy of the prediction, therefore, all the variables were used in the prediction.
- In addition, for Linear and Polynomial regressions not many parameters can be changed, therefore, grid search contribution to the improvement of the model score was very low.
