# Coding Conventions C#
## Contents
 - [Intro](#intro)
 - [Naming and code style](#naming-and-code-style)
 - [Project (.csproj)](#project-csproj)

## Intro
This document describes the coding conventions, I'm using as a default on my projects. 
Details may change from project to project or from customer to customer, depending on their individual requirements. 

My Coding conventions are based on the official C# Coding Conventions from microsoft, see https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions. I do not change these. All following conventions should be seen as an extension.

## Naming and code style
### Abbreviations
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

### Constants
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

### Private field prefixes
Private fields should always have a prefix _ like _dummyField.
Static private fields should always have a prefix s_ like s_dummyStaticField

Example
```csharp
class DummyClass
{
    private static string s_dummyStaticField;
    private string _dummyString;
    //...
}
```

### Naming for event handlers
Event handling methods should be named like the following pattern
On[ElementName]_[EventName]

Examples are
 - OnCmdAdd_Click
 - OnGridView_ItemsSelected

### Don't use #region
Not much to write on that

### Try to avoid nested types
Normally each type should live in an own file. If nested types are used, they 
should be at least private to the type, in which they are defined.

## Project (.csproj)
### Treat warnings as erros
Treat warnings as errors should always be active. If GenerateDocumentationFile is set to true, we may
also need to suppress warnings [CS1591](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-messages/cs1591) and
[CS1712](https://learn.microsoft.com/en-us/dotnet/csharp/misc/cs1712). These warnings would pop up, if
we forget to set a xml documentation on any member or type.
```xml
<PropertyGroup>
    <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
    <WarningsAsErrors />
    <NoWarn>1591,1712</NoWarn>
</PropertyGroup>
```

### Enable NRT (Nullable Reference Types)
Nullable Reference Types is a feature which helps to avoid NullReferenceExceptions

```xml
<PropertyGroup>
    <Nullable>enable</Nullable>
</PropertyGroup>
```