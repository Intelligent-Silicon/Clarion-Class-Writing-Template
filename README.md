# Clarion Class Writing Template

## OOP Rules

An INTERFACE declares the required CLASS methods, parameters & return values to be IMPLEMENTed.

An INTERFACE can optionally be IMPLEMENTed in one or more CLASSes.

A CLASS must have a Construct and Deconstruct method when using THREAD (Clarion 6 versions or later).

A CLASS can have additional methods not used in the IMPLEMENTed INTERFACEs.

A CLASS METHOD can call PROCEDURE's and API's from outside of the CLASS.


![AppGen Tree View](https://github.com/Intelligent-Silicon/Clarion-Class-Writing-Template/blob/main/Pics/AppGen-Tree-View.jpg)





# Clarion Class Writing Template

## AppGen Procedure Naming Schema

AppGen procedure names are not case sensitive. The Template is not case sensitive.

| AppGen Procedure Name | RegEx | Examples |
|--|--|--|
| Main Name | ```'^MAIN$'``` | [Main Label], Main |
| Main Procedure Name | ```'^MAIN[\.][a-zA-Z0-9_]+$'``` | [Main Label].[Procedure Label], Main.My1stProcedureName, Main.My_2nd_ProcedureName |
| Interface Name | ```'^INTERFACE[\.][a-zA-Z0-9_]+$'``` | Interface.[Interface Label], Interface.MyFirstInterfaceName, INTERFACE.My_Second_IntName |
| Interface Method Name | ```'^INTERFACE[\.][a-zA-Z0-9_]+[\.][a-zA-Z0-9_]+$'``` | Interface.[Interface Label].[Method Label], Interface.MyFirstInterface.MyIntMethod, INTERFACE.MySecondInt.My_2nd_IntMethod |
| Class Name | ```'^CLASS[\.][a-zA-Z0-9_]+$'``` | Class.[Class Label], Class.AClassName, Class.Another_Class_Name |
| Class Method Name | ```'^CLASS[\.][a-zA-Z0-9_]+[\.][a-zA-Z0-9_]+$'``` | Class.[Class Label].[Method Label], Class.AClassName.My1stMethodName, Class.AnotherClassName.My_2nd_ClassMethod |
| Class Method Construct/Destruct | ```'^CLASS[\.][a-zA-Z0-9_]+[\.]{{CONSTRUCT\|DESTRUCT}$'``` | Class.[Class Label].Construct, Class.AClassName.Construct, Class.AnotherClassName.DESTRUCT |

## Template Rules

The AppGen (First) Procedure called ```MAIN``` is to be used as the parent non class prototype/definition for defining variables outside of a class & non class procedures to be included in the class source file(s).


## Procedure and Method OverLoading

MAIN procedures, Class methods and Interface methods contain the parameter overloading information for building Definitions and Prototypes. Class Construct and Destruct do not overload.



