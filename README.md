# Energy-Efficiency-ML

Web application estimating energy efficiency of a building based on its 5 parameters.

Utilizing Azure Machine Learning Regression Model which is not part of this repository.

## Usage

* Change `aml.url` and `aml.apiKey` in `web.config` appSettings in accordance to your Azure Machine Learning Web Service configuration

* Make a POST request to `/api/heatingload` using below JSON schema (sample values):


    `{
        "surfaceArea": 808.5,
        "wallArea" : 367.5,
        "roofArea" : 220.5,
        "overallHeight" : 3.5,
        "glazingArea" : 0
    }`

## Response

Object with following properties, numeric values are yearly consumption:

    `{
      "consumptionPerSquareMeter": 32.702969600571,
      "totalConsumption": 2616.2375680456803,
      "efficiency": "High"
    }`

Efficiency thresholds can be altered in `appSettings` in `web.config`.
