# Challenge 6 - Bicep Modules

[< Previous Challenge](./Bicep-Challenge-06.md) - [Home](../README.md) 

## Introduction

The goals for this challenge include understanding:
- Bicep modules allow for granular resource management and deployment
- How ARM Bicep modules improves upon ARM JSON linked templates which require staging artifacts in a location accessible to the Azure Resource Manager

Bicep introduces the concept of *modules*. These are similar to linked templates but are much simpler to work with. When you write a Bicep file you can embed another Bicep file as a module. When your template is transpiled a single ARM template is produced with your module included within it. This is often a much simpler approach than dealing with linked templates.

When templates get big, they become monoliths. They are hard to manage.  By breaking your templates up into smaller modules, you can achieve more flexibility in how you manage your deployments.

In many companies, deployment of cloud infrastructure may be managed by different teams. For example, a common network architecture and its security settings may be maintained by an operations team and shared across multiple application development teams.

The network architecture and security groups are typically stable and do not change frequently. In contrast, application deployments that are deployed on the network may come and go.

## Description

In this challenge you will separate your existing Bicep template deployment into two sets of modules. 

- Separate app service plan in to their own module.
  - Create a parameter for sku in this module. Pass its value from the main template that will call this module.
- Separate app service in to their own module.
  - Create a parameter for appPlanId in this module. The value for this parameter should be passed from the main template that will call this module.
- Create a new Bicep template that deploys each of the new modules.
- Ensure parameters flow through from the new template to each of the modules.

Use the following example to break it up into modules.

```bicep
resource appServicePlan 'Microsoft.Web/serverfarms@2020-12-01' = {
  name: 'auniqueappserviceplan'
  location: 'uksouth'
  sku: {
    name: 'F1'
    capacity: 1
  }
}

resource webApplication 'Microsoft.Web/sites@2018-11-01' = {
  name: 'auniquenameherepm121'
  location: 'uksouth'
 
  properties: {
    serverFarmId: appServicePlan.id
  }
}

```

## Success Criteria

1. Verify that the Bicep CLI does not show any errors and correctly emits an ARM JSON template that includes all of the resources in the Bicep modules.
1. Verify that all resources deploy as before when you had a single Bicep template

## Stretch Goal

Use the example [here](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-bicep?tabs=CLI) and convert this example into using modules 
## Learning Resources

- [Use Bicep modules](https://docs.microsoft.com/en-us/azure/azure-resource-manager/bicep/modules)
- [Using linked and nested ARM Templates with JSON when deploying Azure resources](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/linked-templates) - Read this to appreciate how much Bicep improves upon the complexity of linked templates with ARM Templates with JSON.
