# MapSurfer.NET Expressions

## Introduction

According to [Wikipedia](http://en.wikipedia.org/wiki/Expression_%28computer_science%29), an expression in a programming language is a combination of explicit values, constants, variables, operators, and functions that are interpreted according to the particular rules of precedence and of association for a particular programming language, which computes and then produces (returns, in a stateful environment) another value. 

In MapSurfer.NET, expressions are an incredibly powerful tool that provides great efficiency and flexibility when it comes to work with both geometric and metadata at run time. Expressions are used in:

- data filtering
- labelling 
- symbolizer properties
- geometry transformations

The expression engine is based on a modified version of Microsoft's [System.Linq.Dynamic](https://www.nuget.org/packages/System.Linq.Dynamic) library. For more information about expressions, please refer to [Microsoft's Documentation](https://msdn.microsoft.com/en-us/library/ms173144.aspx).  


## Supported Types

###.NET Default Types

- [Object](https://msdn.microsoft.com/en-us/library/system.object%28v=vs.110%29.aspx)
- [Boolean](https://msdn.microsoft.com/en-us/library/system.boolean%28v=vs.110%29.aspx)
- [Char](https://msdn.microsoft.com/en-us/library/system.char%28v=vs.110%29.aspx)
- [String](https://msdn.microsoft.com/en-us/library/system.string%28v=vs.110%29.aspx)
- [SByte](https://msdn.microsoft.com/en-us/library/system.sbyte%28v=vs.110%29.aspx)
- [Byte](https://msdn.microsoft.com/en-us/library/system.byte%28v=vs.110%29.aspx)
- [Int16](https://msdn.microsoft.com/en-us/library/system.int16%28v=vs.110%29.aspx)
- [UInt16](https://msdn.microsoft.com/en-us/library/system.uint16%28v=vs.110%29.aspx)
- [Int32](https://msdn.microsoft.com/en-us/library/system.int32%28v=vs.110%29.aspx)
- [UInt32](https://msdn.microsoft.com/en-us/library/system.uint32%28v=vs.110%29.aspx)
- [Int64](https://msdn.microsoft.com/en-us/library/system.int64%28v=vs.110%29.aspx)
- [UInt64](https://msdn.microsoft.com/en-us/library/system.uint64%28v=vs.110%29.aspx)
- [Single](https://msdn.microsoft.com/en-us/library/system.single%28v=vs.110%29.aspx)
- [Double](https://msdn.microsoft.com/en-us/library/system.double%28v=vs.110%29.aspx)
- [Decimal](https://msdn.microsoft.com/en-us/library/system.decimal%28v=vs.110%29.aspx)
- [DateTime](https://msdn.microsoft.com/en-us/library/system.datetime%28v=vs.110%29.aspx)
- [TimeSpan](https://msdn.microsoft.com/en-us/library/system.timespan%28v=vs.110%29.aspx)
- [Guid](https://msdn.microsoft.com/en-us/library/system.guid%28v=vs.110%29.aspx)
- **[Math](https://msdn.microsoft.com/en-us/library/system.math%28v=vs.110%29.aspx)**
- **[Convert](https://msdn.microsoft.com/en-us/library/system.convert%28v=vs.110%29.aspx)**
- **[Regex](https://msdn.microsoft.com/en-us/library/system.text.regularexpressions.regex%28v=vs.110%29.aspx)**

### Custom Types

- Envelope
- Geometry
- GeometryTransformations
- **[ColorTranslator](https://msdn.microsoft.com/en-us/library/system.drawing.colortranslator%28v=vs.110%29.aspx)** 
- StringExtensions 
- MathEx
- OSMUtility

Each bold item presents a [static class](https://msdn.microsoft.com/en-us/library/79b3xss3.aspx) which cannot be instantiated. The purpose of a static class is to provide an access to a list of functions that can be used in expressions. For more details, see Functions section. 

MapSurfer.NET framework gives a possibility to extend expressions with custom functions. In order to plug in your extension, you need to create an xml file named **ExpressionTypes.xml** in **..\MyDocuments\MapSurfer.NET\Common** folder. This file should have the following format:
 
```xml
<?xml version="1.0"?>
<Assemblies>
  <AssemblyInfo path = "C:\Program Files\MapSurfer.NET\1.16\Core\MapSurfer.System.dll">
    <Types>
      <Type name="MapSurfer.CharExtensions" />
      <Type name="MapSurfer.IntExtensions" />
    </Types>
  </AssemblyInfo>
  <AssemblyInfo path = "C:\Program Files\MapSurfer.NET\1.16\Core\MapSurfer.Core.dll">
    <Types>
      <Type name="MapSurfer.IDObject" />
    </Types>    
  </AssemblyInfo>
</Assemblies>
```

where each AssemblyInfo element defines an assembly with custom extensions. The attribute **path** determines a path to the assembly. Types element is a list of types that are going to be used in expressions.
        
## Operators

MapSurfer.NET provides a rich set of operators both commonly used in programming languages and SQL queries. The following subsections present an overview of supported operators. 

### Conditional Operators

Operator  | Description | Syntax
------------- | ------------- | -------------
?:  | The conditional operator evaluates an expression (condition), then it returns first value if that expression evaluates to true, and the second value if the expression evaluates as false. | condition ? first_expression : second_expression

### Logical Operators

Operator  | Description | Syntax
------------- | ------------- | -------------
 &#124;&#124;, or  | The operator performs a logical-OR of its bool expressions.  | first_expression || second_expression
 &&, and  | The operator performs a logical-AND of its bool expressions.  | first_expression && second_expression
 !, not | The unary negation operator is a logical operator that negates its operand. | !expression

### Comparison Operators

Operator  | Description | Syntax
------------- | ------------- | -------------
=, ==  | The equality operator returns true if the values of its operands are equal, false otherwise | first_expression == second_expression
!=, <> | The inequality operator returns false if its operands are equal, true otherwise.  | first_expression != second_expression
> | The "greater than" relational operator returns true if the first operand is greater than the second, false otherwise. | first_expression > second_expression
>= | The "greater than or equal" relational operator returns true if the first operand is greater than or equal to the second, false otherwise. | first_expression >= second_expression
< | The "less than" relational operator returns true if the first operand is less than the second, false otherwise. | first_expression < second_expression
<= | The "less than or equal" relational operator returns true if the first operand is less than or equal to the second, false otherwise. | first_expression <= second_expression
in | Determines whether a specified value matches any value in a subquery or a list. |  test_expression IN (value1, value2, value3)
like | Determines whether a specific character string matches a specified pattern. |  match_expression LIKE pattern


### Arithmetic Operators

Operator  | Description | Syntax
------------- | ------------- | -------------
+  | The operator of arithmetic addition. | expression1 + expression2
-  | The operator of arithmetic subtraction. | expression1 - expression2
*  | The operator of arithmetic multiplication. | expression1 * expression2
/  | The operator of arithmetic division. | expression1 / expression2
%  | Returns the remainder of a division of two values. | expression1 % expression2
  

## Other Operators

Operator  | Description | Syntax
------------- | ------------- | -------------
[] | This operator is used to access the value of a field in a data source or to access an element of an array. | [field_name][0]
() | This operator allows specifying the order of operations in an expression. | (expression1 - expression2) * expression3
.  | This operator is used to access the functions of a static class. | Class.Method(expression1, value1)

For example, if you have a static class named DistanceCalc that has a method named Euclidean with four arguments of double type, you can call this method as:

```cs
DistanceCalc.Euclidean(4.12, 12.6, 4.22, 12.8)
```

## Literals

Type  | Description | Example
------------- | ------------- | -------------
String | A regular string literal represents a set of characters enclosed in double quotes.| "Berlin"
Char | A character literal is a single character enclosed in quotes. | 'a'
null | The null literal. | null

## Examples

The following example computes a new value adding 1 to **width** property. 

```cs
[width] + 1
```
