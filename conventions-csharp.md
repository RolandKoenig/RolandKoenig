# Coding Conventions C#
## Intro
This document describes the coding conventions, I'm using as a default on my projects. 
Details may change from project to project or from customer to customer, depending on their individual requirements. 

## Baseline
My Coding conventions are based on the official C# Coding Conventions from microsoft, see https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions. I do not change these. All following conventions should be seen as an extension.

# Naming
## Abbreviation
Abbreviations always use the normal casing. For pascal case this meens that the first letter ist big and all following letters are small. This does also apply for short abbreviations like Db or Id.

Example
```csharp
class DummyClass
{
    private string _dummyId;
    private string _dbConnectionString;

    //...
}
```

## Constants
Constants are written in big letters, words separated by underscore. Take THIS_IS_A_CONSTANT for example.  
The same convention for constant-alike static readonly fields. 

Example
```csharp
class DummyClass
{
    private const string THIS_IS_A_CONSTANT = "dummy value";
    private static readonly Encoding THIS_IS_ANOTHER_CONSTANT = Encoding.UTF8;

    //...
}
```

## Private field prefix
Private fields should always have a prefix _ like _dummyField

Example
```csharp
class DummyClass
{
    private string _dummyString;

    //...
}
```

# Project
## Treat warnings as erros
