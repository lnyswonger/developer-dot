---
layout: page
title: InvalidParameterValue
number: 306
categories: [AvaTax Error Codes]
disqus: 0
---

## Summary

When adding parameters to your CreateTransactionModel, you must specify a parameter of the correct type.

## Example

    {
      "code": "InvalidParameterValue",
      "target": "Unknown",
      "details": [
        {
          "code": "InvalidParameterValue",
          "number": 306,
          "message": "The parameter '-0-' expects a value of type '-2-'.",
          "description": "You provided the value '-1-', which is not a valid '-2-'.",
          "faultCode": "Client",
          "helpLink": "http://developer.avalara.com/avatax/errors/InvalidParameterValue",
          "severity": "Error"
        }
      ]
    }

## Explanation

You passed a parameter value that was not the correct type.

Parameter types are one of the following:
* Boolean - The only acceptable values are "true" and "false".
* Numeric - Only numeric values may be provided.
* String - Any text value may be provided.

Please check the parameters in your CreateTransactionModel and ensure that each one has a value of the correct data type.