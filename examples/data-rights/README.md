[ODRL](https://www.w3.org/TR/odrl-model/) is a W3C standard to describe rights and entitlements.
Based on ODRL, data product and dataset publishers can describe policies in a consistent, standard and machine-readable manner. Policies contain permissions and prohibitions on specific actions that are required to be met by stakeholders.

In addition, policies may be limited by constraints (eg. temporal or geographical constraints) and duties (eg. payments) that may be imposed on the permissions.

Policies and their permitted or prohibited actions can be described at different levels, eg. a policy can target a data product, a dataset, a data service or even a column.

Sophisticated engines should interpret and enforce the ODRL policies at the appropriate level eg.:

```turtle
examplePolicyA odrl:targets exampleProduct:ProductA .
examplePolicyB odrl:targets exampleDataset:DatasetA1 .
```

An example of a policy follows, that describes permission to distribute the data only within a specific geographic region:

```json
examplePolicyA odrl:permission
   {
    "action": "odrl:distribute",
    "constraint": [
       {"leftOperand": "spatial",
         "operator": "eq",
        "rightOperator": "region:EMEA"
       }
     ]
    }
 ```

