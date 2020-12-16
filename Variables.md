# Variables

Azure Pipelines has the concept of variables, the nearest in GitHub Actions is environment variables. 

## Key differences

Difference|Explanation|
-|-|
All system variables are different.| All system variable names are different, https://docs.github.com/en/free-pro-team@latest/actions/reference/environment-variables#default-environment-variables they are prefxied by GITHUB_
Setting of values at runtime| Github only allows for setting of string values at trigger time.

# Compatibility Advice
Advice on how to make any future transition to GitHub Actions easy

Only refer to system variables in your yml files, don't refer to them in your scripts, rather use variables you control the name of and set those from the system variables in the yml. 


### Setting of values at runtime
[Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/runtime-parameters?view=azure-devops&tabs=script) | [Github Actions](https://docs.github.com/en/free-pro-team@latest/actions/reference/events-that-trigger-workflows#workflow_dispatch)
In azure pipelines you specify parameters on the yml template to have the parameter settable at runtime. 
In GitHub Actions you add inputs to the workflow_dispatch trigger

> Note: You can only specify strings in Github actions. 
> Note: You can't specify drop down lists for inputs to the workflow
