# Clarion Class Writing Template

## OOP Rules

An INTERFACE declares the required CLASS methods, parameters & return values to be IMPLEMENTed.

An INTERFACE can optionally be IMPLEMENTed in one or more CLASSes.

A CLASS must have a Construct and Deconstruct method when using THREAD (Clarion 6 versions or later).

A CLASS can have additional methods not used in the IMPLEMENTed INTERFACEs.

A CLASS METHOD can call (Main) PROCEDURE's and API's from outside of the CLASS.


![AppGen Tree View](https://github.com/Intelligent-Silicon/Clarion-Class-Writing-Template/blob/main/Pics/AppGen-Tree-View.jpg)





# Clarion Class Writing Template

Status: Final Testing.

C6 or later.

Wishlist: Import class source files (```.INT```, ```.INC```, ```.CLW```) into TXA/TXD format for use in the IDE. 

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

The AppGen (First) Procedure called ```MAIN``` is to be used as the parent non-class/interface prototype/definition for defining variables outside of a class & non class procedures to be included in the class source file(s).


## Procedure and Method OverLoading

MAIN procedures, Class methods and Interface methods contain the parameter overloading information for building Definitions and Prototypes. Class Construct and Destruct do not overload (template restriction currently - not tested with compiler).


## Output files

The code can be written out to 1, 2 or 3 files.

All of the below sections can be written in a single source file.

Main (non-class/interface) procedure prototypes can be written in the ```.INC``` (Module) or ```.CLW``` (Map) file.

Main (non-class/interface) procedure definitions are written in the ```.CLW``` file.

Interface declarations and Interface Method prototypes can be written in the ```.INC``` or ```.INT``` file.

Class declarations are written in the ```.INC``` file.

Class Method prototypes are written in the ```.INC``` file.

Class Method definitions are written in the ```.CLW``` file.


## Data (Variables and Properties )

Dictionary (Dct) file prefixes can be optionally removed from all Dct variables during the final source code generation output to file(s). Your responsibility to avoid name clashes.

Main (non-class) Definition variables can be populated using the Global Dct file, and/or AppGen Global Data, and/or be defined in Embed Code.

Main (non-class) Definition variables will appear as Global Data in the Embed Editor for optional use in all class methods.

Main (non-class) Procedure variables can be populated using a single Dct file in the ```Table Schematic Definition Primary File```, and/or ```Procedure Local Data``` section, and/or be defined in Embed code.


Class Definition & Method Properties can be populated using a single Dct file in the ```Table Schematic Definition Primary File```, and/or ```Procedure Local Data``` section, and/or be defined in Embed code.

Class Definition properties can be included in the  ```Table Schematic Definition Other Files``` for use in individual class methods.

For overloaded Main (non-class) Procedures and Class Methods, Field Options can be used in the Dct and AppGen Local Data to limit the Variable/Property declaration to the corresponding Procedure/Method Overload(s).

This makes Dct file variables & Local Data variables available to use in the Embed editor for added convenience.


### Dct files and AppGen Local Data being used to populate a Class Method.

![AppGen Data](https://github.com/Intelligent-Silicon/Clarion-Class-Writing-Template/blob/main/Pics/AppGen-Data.jpg)


### Dct file limiting variable to a single Class Method overload called Default

![Dct Field User Option](https://github.com/Intelligent-Silicon/Clarion-Class-Writing-Template/blob/main/Pics/Dct-Field-User-Option.jpg)

The Dct file called ```AClass_Method``` is used in a Class Method with two overloads, one called ```Default```, the other called ```Cstring```. ```Default_Outer_Grp``` will only be declared in the overload method using the unique friendly name ```Default```. If no Field option is specified, the variable will be declared in all overloaded methods. The AppGen class method automatically updates the Clarion ini file for use in the Dct editor. 

### AppGen Class Method Overloads

![AppGen Class Method Overloads](https://github.com/Intelligent-Silicon/Clarion-Class-Writing-Template/blob/main/Pics/AppGen-Overload-Methods-Field-Options.jpg)

The unique "Friendly Name" assigned to each Method Overload with the parameters visible. ```Default``` is created automatically when the Class Method AppGen procedure is created and can be changed provided it remains unique to the procedure's method overload list. The "Friendly Name" is used in the Dct and Local field options to optionally limit the property declaration. The Populate Data box lets you choose what data you want to populate in the final class source file(s) regardless of it being specified in the ```Table Schematic Definition``` window or ```Local Data``` section.

### Realtime Embed and Source Code Spacing

![AppGen Realtime Spacing](https://github.com/Intelligent-Silicon/Clarion-Class-Writing-Template/blob/main/Pics/AppGen-Realtime-Embed-Source-Spacing.jpg)

The Template lets you control the spacing of all the code output in realtime WYSYG in the Embed Editor View Source and Source output file(s). Make an alignment change here, go to the AppGen procedure method, right mouse click Embed, click View Source and see the alignment changes made to get perfectly laid out code!
