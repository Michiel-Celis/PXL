# C# Essentials
## Table of Contents
### Short Table

- [C# Essentials](#c-essentials)
	- [Table of Contents](#table-of-contents)
	- [Data Types](#data-types)
	- [Operators](#operators)
	- [Control Flow](#control-flow)
	- [Naming Conventions](#naming-conventions)
	- [Often used methods](#often-used-methods)
	- [Methods and Parameters](#methods-and-parameters)
	- [Data Grouping](#data-grouping)
- [WPF Essentials](#wpf-essentials)
	- [Event Procedures](#event-procedures)
	- [Event Types](#event-types)
	- [WPF Elements](#wpf-elements)
	- [WPF Panels](#wpf-panels)

<Summary>Full Table</Summary>
<details>

- [C# Essentials](#c-essentials)
	- [Table of Contents](#table-of-contents)
		- [Short Table](#short-table)
	- [Data Types](#data-types)
		- [Variables](#variables)
		- [Constants](#constants)
		- [Types](#types)
		- [Suffixes for Numeric Types](#suffixes-for-numeric-types)
		- [Alphanumeric Types](#alphanumeric-types)
			- [Escape Sequences](#escape-sequences)
			- [Verbatim Strings](#verbatim-strings)
			- [String Interpolation](#string-interpolation)
		- [Declaration](#declaration)
		- [Initialization](#initialization)
		- [Scope and Lifetime](#scope-and-lifetime)
			- [Local Variables](#local-variables)
			- [Global Variables](#global-variables)
		- [Type Conversion](#type-conversion)
			- [String to Numeric Types](#string-to-numeric-types)
			- [String Formatting](#string-formatting)
			- [String \<\> Numeric conversions](#string--numeric-conversions)
			- [Numeric Types to String](#numeric-types-to-string)
			- [Explicit Numeric Conversions](#explicit-numeric-conversions)
			- [Implicit Numeric Conversions](#implicit-numeric-conversions)
			- [Boolean to String and Vice Versa](#boolean-to-string-and-vice-versa)
			- [DateTime Conversions](#datetime-conversions)
	- [Operators](#operators)
		- [Arithmetic Operators](#arithmetic-operators)
		- [Assignment Operators](#assignment-operators)
		- [Comparison Operators](#comparison-operators)
		- [Logical Operators](#logical-operators)
		- [Priority](#priority)
	- [Control Flow](#control-flow)
		- [Nesting](#nesting)
		- [if](#if)
		- [switch](#switch)
		- [while](#while)
		- [do while](#do-while)
		- [for](#for)
		- [foreach](#foreach)
		- [break](#break)
		- [continue](#continue)
		- [return](#return)
	- [Naming Conventions](#naming-conventions)
		- [Pascal Case](#pascal-case)
		- [Camel Case](#camel-case)
		- [Hungarian Notation](#hungarian-notation)
	- [Often used methods](#often-used-methods)
		- [System.Math](#systemmath)
			- [Abs()](#abs)
			- [Ceiling()](#ceiling)
			- [Floor()](#floor)
			- [Max()](#max)
			- [Min()](#min)
			- [Pow()](#pow)
			- [Round()](#round)
			- [Sqrt()](#sqrt)
		- [System.String](#systemstring)
			- [Compare()💚](#compare)
			- [Concat()💚](#concat)
			- [Contains()](#contains)
			- [EndsWith()](#endswith)
			- [Equals()💚](#equals)
			- [IndexOf()💚](#indexof)
			- [Insert()💚](#insert)
			- [Join()](#join)
			- [IndexOf()](#indexof-1)
			- [Length()💚](#length)
			- [PadLeft()💚](#padleft)
			- [PadRight()💚](#padright)
			- [Remove()💚](#remove)
			- [Replace()💚](#replace)
			- [Split()](#split)
			- [StartsWith()](#startswith)
			- [Substring()💚](#substring)
			- [ToLower()](#tolower)
			- [ToUpper()](#toupper)
			- [Trim()](#trim)
			- [TrimEnd()](#trimend)
			- [TrimStart()](#trimstart)
			- [IsNullOrEmpty()](#isnullorempty)
			- [IsNullOrWhiteSpace()](#isnullorwhitespace)
			- [Format()](#format)
			- [Parse()](#parse)
			- [TryParse()](#tryparse)
			- [ToString()](#tostring)
		- [System.Text.StringBuilder](#systemtextstringbuilder)
			- [Append()💚](#append)
			- [AppendLine()💚](#appendline)
			- [AppendFormat()](#appendformat)
			- [Insert()](#insert-1)
			- [Remove()](#remove-1)
			- [Replace()](#replace-1)
			- [ToString()](#tostring-1)
		- [System.Windows.MessageBox (WPF)💚](#systemwindowsmessagebox-wpf)
			- [Show()](#show)
		- [System.Windows.Forms.MessageBox (WinForms)](#systemwindowsformsmessagebox-winforms)
			- [Show()](#show-1)
		- [Microsoft.VisualBasic.Interaction💚](#microsoftvisualbasicinteraction)
			- [InputBox()](#inputbox)
		- [System.DateTime](#systemdatetime)
		- [System.TimeSpan](#systemtimespan)
		- [System.DispathcerTimer (WPF)](#systemdispathcertimer-wpf)
	- [Methods and Parameters](#methods-and-parameters)
		- [Methods](#methods)
		- [Void procedure](#void-procedure)
		- [Function procedure](#function-procedure)
		- [Event procedure](#event-procedure)
		- [Method overloading](#method-overloading)
	- [Data Grouping](#data-grouping)
		- [Arrays 💚](#arrays-)
			- [Array Methods](#array-methods)
				- [Length](#length-1)
				- [IndexOf](#indexof-2)
				- [Sort](#sort)
				- [Reverse](#reverse)
				- [Clear](#clear)
				- [Copy](#copy)
				- [Resize](#resize)
				- [ToList](#tolist)
		- [Multidimensional Arrays](#multidimensional-arrays)
		- [Jagged Arrays](#jagged-arrays)
		- [Lists 💚](#lists-)
			- [List Methods](#list-methods)
				- [Add](#add)
				- [AddRange](#addrange)
				- [Insert](#insert-2)
				- [Remove](#remove-2)
				- [RemoveAt](#removeat)
				- [RemoveRange](#removerange)
				- [Clear](#clear-1)
				- [Contains](#contains-1)
				- [IndexOf](#indexof-3)
				- [Sort](#sort-1)
				- [Reverse](#reverse-1)
				- [ToArray](#toarray)
				- [ToList](#tolist-1)
		- [Dictionaries 💚](#dictionaries-)
			- [Dictionary Methods](#dictionary-methods)
				- [Add](#add-1)
				- [Remove](#remove-3)
				- [Clear](#clear-2)
				- [ContainsKey](#containskey)
				- [ContainsValue](#containsvalue)
				- [TryGetValue](#trygetvalue)
				- [Keys](#keys)
				- [Values](#values)
		- [Enumerations](#enumerations)
			- [Enumeration Methods](#enumeration-methods)
				- [GetNames](#getnames)
				- [GetValues](#getvalues)
				- [Parse](#parse-1)
				- [TryParse](#tryparse-1)
		- [Structs](#structs)
		- [Classes](#classes)
			- [Properties](#properties)
		- [Constructors](#constructors)
		- [Inheritance](#inheritance)
		- [Polymorphism](#polymorphism)
		- [Abstract Classes](#abstract-classes)
		- [Interfaces](#interfaces)
		- [Extension Methods](#extension-methods)
		- [Generics](#generics)
		- [Delegates](#delegates)
		- [Events](#events)
		- [Lambda Expressions](#lambda-expressions)
- [WPF Essentials](#wpf-essentials)
	- [Event Procedures](#event-procedures)
		- [Xaml handler + code-behind](#xaml-handler--code-behind)
		- [Code-behind-only handler](#code-behind-only-handler)
	- [Event Types](#event-types)
		- [Click Events](#click-events)
		- [Key Events](#key-events)
	- [WPF Elements](#wpf-elements)
		- [Image](#image)
		- [TextBlock](#textblock)
		- [TextBox](#textbox)
		- [Button](#button)
		- [CheckBox](#checkbox)
		- [RadioButton](#radiobutton)
		- [ListBox](#listbox)
		- [ComboBox](#combobox)
		- [ProgressBar](#progressbar)
		- [Slider](#slider)
		- [ScrollViewer](#scrollviewer)
	- [WPF Panels](#wpf-panels)
		- [Grid](#grid)
		- [Canvas](#canvas)
		- [StackPanel](#stackpanel)
		- [WrapPanel](#wrappanel)
		- [DockPanel](#dockpanel)
		- [Viewbox](#viewbox)
  
</details>

## Data Types
- Used to store data by referencing a value in memory
- null = no value assigned
- Declared with a **type** and a **name**
### Variables
- **var** = type is inferred from the value
- Read-Write __Can be changed__
### Constants
- **const** = value cannot be changed.
- Read-Only __Cannot be changed__
  
### Types
| Type      | Description               			| Size          |
|-----------|---------------------------------------|---------------|
| int       | integer                   			| 32 bits       |
| float     | decimal                   			| 32 bits       |
| double    | decimal                   			| 64 bits       |
| decimal   | decimal                   			| 128 bits      |
| bool      | boolean                   			| 1 bit         |
| DateTime  | date and time             			| 64 bits       |
| char      | single character          			| 16 bits       |
| string    | text (array of characters)			| 16 bits/char  |
|			|										|				|
| array     | collection of values of the same type | ~ 			|
| object    | collection of values of any type      | ~ 			| 
| class     | Constructor for custom type           | ~ 			| 
| struct    | Constructor for custom type           | ~ 			| 
| enum      | custom type                           | ~ 			| 
| interface | custom type                           | ~ 			| 
| delegate  | custom type                           | ~ 			|
| dynamic   | any type                              | ~ 			| 

### Suffixes for Numeric Types
| Suffix    | Type                                  |
|-----------|---------------------------------------|
| F         | float                                 |
| M         | decimal                               |
| L         | long                                  |
| UL        | ulong                                 |
| U         | uint                                  |
| D         | double                                |

### Alphanumeric Types
#### Escape Sequences
| Escape Sequence | Description                |
|-----------------|----------------------------|
| \n              | New line                   |
| \t              | Tab                        |
| \r              | Carriage return            |
| \b              | Backspace                  |
| \f              | Form feed                  |
| \\'              | Single quote              |
| \\"              | Double quote              |
| \\\              | Backslash                 |
| \uXXXX          | Unicode character          |
| \xXX            | Unicode character          |
| \0              | Null character             |

#### Verbatim Strings
> @ = ignore escape sequences
```csharp
string str = "C:\\Users\\Public\\Documents\\";
string str2 = @"C:\Users\Public\Documents\";
```

#### String Interpolation
> $ = insert variable in string
```csharp
string name = "John";
string str = $"Hello {name}";
```

### Declaration
```csharp
static void Main( string [] args
{
	int			aWholeNumber;
	bool		aTrueOrFalseValue;
}
```
### Initialization
```csharp
static void Main( string [] args
{
	int			aWholeNumber 			= 0;
	float		aFloatingPointNumber 	= 2.5F;
	double		aDoubleIntFloat 		= 0.5;
	decimal 	aFloatWithPrecision 	= 0.5M;
	bool		aTrueOrFalse 			= true;
	char		aSingleCharacter 		= "a";
	string		aText 					= "tekst";
	DateTime	aDateAndTime 			= DateTime.Now;
	DateTime	aDate 					= new DateTime(2020, 1, 1);
}
```
### Scope and Lifetime
- Scope = where the variable is accessible
- Lifetime = how long the variable exists
- Variables declared in a method are only accessible in that method
- Variables declared outside a method are accessible in the whole class
- Variables declared outside a class are accessible in the whole namespace
```csharp	
namespace celis_michiel_c_sherp
{
	public partial class MainWindow : Window
	{
		static int aNumberInNamespace = 0;
		private int	aPrivateNumber 			= 1;
		public int	aPublicNumber 			= 2;

		static void Main( string [] args )
		{
			int		aNumberInMain 			= 3;
		}
		static void AnotherMethod()
		{
			int		aNumberInAnotherMethod 	= 4;

			console.WriteLine(aNumberInNamespace);		// 🟢 Ok: aNumberInNamespace is accessible
			Console.WriteLine(aPrivateNumber);			// 🔴 Error: aPrivateNumber is not accessible
			Console.WriteLine(aPublicNumber);			// 🟢 Ok: aPublicNumber is accessible
			Console.WriteLine(aNumberInMain);			// 🔴 Error: aNumberInMain is not accessible
			Console.WriteLine(aNumberInAnotherMethod);	// 🟢 Ok: aNumberInAnotherMethod is accessible
		}

		console.WriteLine(aNumberInNamespace);			// 🟢 Ok: aNumberInNamespace is accessible
		Console.WriteLine(aPrivateNumber); 				// 🟢 Ok: aPrivateNumber is accessible
		console.WriteLine(aPublicNumber);				// 🟢 Ok: aPublicNumber is accessible
		console.WriteLine(aNumberInAnotherMethod);		// 🔴 Error: aNumberInAnotherMethod is not accessible
	}
}
```
#### Local Variables
- Declared inside a method
- Lifetime = as long as the method is executing
#### Global Variables
- Declared outside a method
- Lifetime = as long as the application is running
- **static** = global variable
- **readonly** = global constant
- **const** = global constant

### Type Conversion
- Implicit = automatic conversion
- Explicit = manual conversion

#### String to Numeric Types
> You can convert a string to various numeric types using 
Convert.ToInt16(123), Convert.ToInt32(12345....), Convert.ToSingle(1.5F), Convert.ToDouble(1.5), Convert.ToDecimal(11.55....), etc.
```csharp
string str = "123";
int num = Convert.ToInt32(str);
```
#### String Formatting
You can format a string using the following syntax:
```csharp
int num = 123;
string str = string.Format("Hello {0}", num);
```
```csharp
int num = 123;
string str = console.WriteLine("Hello {num}");
```
#### String <> Numeric conversions
| Conversion Function | Parse Method           |
|-----------------|----------------------------|
| Convert.ToDecimal()  | decimal.Parse()       |
| Convert.ToDouble()   | double.Parse()        |
| Convert.ToInt32()    | int.Parse()           |
| Convert.ToInt64()    | long.Parse()          |
| Convert.ToSingle()   | float.Parse()         |
| Convert.ToString()   | string.Parse()        |
| Convert.ToBoolean()  | bool.Parse()          |
| Convert.ToDateTime() | DateTime.Parse()      |
> TryParse() = returns true if the conversion was successful, otherwise false
```csharp
string str = "123";
int num;
bool success = int.TryParse(str, out num);
```
#### Numeric Types to String
> You can convert numeric types to a string using the ToString() method.
```csharp
int num = 123;
string str = num.ToString();
```
#### Explicit Numeric Conversions
> Some numeric conversions require an explicit cast. For example, converting a double to an int requires a cast because you might lose data in the conversion.
```csharp
int num = 123;
long longNum = num;
int num2 = (int)longNum;
```
#### Implicit Numeric Conversions
> Some numeric conversions do not require an explicit cast. For example, converting an int to a double does not require a cast because you will not lose data in the conversion.
```csharp
int num = 123;
double num2 = num;
```
#### Boolean to String and Vice Versa
> You can convert a boolean to a string using ToString(), and you can convert a string to a boolean using bool.Parse() or bool.TryParse().
```csharp	
bool b = true;
string str = b.ToString();  // str will be "True"

str = "false";
b = bool.Parse(str);  // b will be false
```
#### DateTime Conversions
> You can convert a string to a DateTime using DateTime.Parse() or DateTime.TryParse(), and you can convert a DateTime to a string using ToString().
```csharp
string dateStr = "2022-01-01";
DateTime date = DateTime.Parse(dateStr);

dateStr = date.ToString("yyyy-MM-dd");
```

## Operators
### Arithmetic Operators
| Operator  | Description                |
|-----------|----------------------------|
| +         | Addition                   |
| >         | Subtraction                |
| *         | Multiplication             |
| /         | Division                   |
| %         | Modulus (remainder)        |
| ++        | Increment                  |
| ->        | Decrement                  |
|           |                            |
| **Operation** | **Description**        |
| +x, -x    | Change sign                |
| x+y, x-y	| Addition Substraction      |
| x*y, x/y	| Multiplication  Division   |
| x%y	   	| Remainder                  |
| x++, X--	| Postfix Increment Decrement|

### Assignment Operators
| Operator  | Description                |
|-----------|----------------------------|
| =         | Assignment                 |
| +=        | Addition assignment        |
| -=        | Subtraction assignment     |
| *=        | Multiplication assignment  |
| /=        | Division assignment        |
| %=        | Modulus assignment         |

### Comparison Operators
| Operator  | Description                |
|-----------|----------------------------|
| ==        | Equal to                   |
| !=        | Not equal to               |
| >         | Greater than               |
| <         | Less than                  |
| >=        | Greater than or equal to   |
| <=        | Less than or equal to      |

### Logical Operators
| Operator  | Description                |
|-----------|----------------------------|
| &&        | Logical AND                |
| \|\|      | Logical OR                 |
| !         | Logical NOT                |
| ^         | Logical XOR                |

### Priority
| Priority  | Operator                   |
|-----------|----------------------------|
| 1         | ()                         |
| 2         | ++, ->                     |
| 3         | *, /, %                    |
| 4         | +, >                       |
| 5         | <, >, <=, >=               |
| 6         | ==, !=                     |
| 7         | &&                         |
| 8         | \|\|                       |
| 9         | =, +=, -=, *=, /=, %=     |

## Control Flow
### Nesting
- Nesting = placing a control flow statement inside another control flow statement
- Nesting is allowed, but not recommended
- Indentation is used to make the code more readable
- Curly braces are used to group statements
- Curly braces are optional if there is only one statement
- Curly braces are required if there are multiple statements
- Curly braces are required if there is no statement

### if
```csharp
if (condition)
{
	// code
}
else if (condition)
{
	// code
}
else
{
	// code
}
```
> Short if notation
```csharp
int a = 1;
int b = 2;
int c = (a > b) ? a : b;
```
### switch
```csharp
switch (variable)
{
	case value1:
		// code
		break;
	case value2:
		// code
		break;
	default:
		// code
		break;
}
```
### while
```csharp
while (condition)
{
	// code
}
```
### do while
```csharp
do
{
	// code
} while (condition);
```
### for
```csharp
for (int i = 0; i < 10; i++)
{
	// code
}
```
### foreach
```csharp
foreach (var item in collection)
{
	// code
}
```
### break
```csharp
while (condition)
{
	if (condition)
	{
		break;
	}
}
```
### continue
```csharp
while (condition)
{
	if (condition)
	{
		continue;
	}
}
```
### return
```csharp
public int MyMethod()
{
	return 0;
}
```

## Naming Conventions
### Pascal Case
- First letter of each word is capitalized
- Used for classes, methods, properties, namespaces, etc.
```csharp
public class MyClass
{
	public void MyMethod()
	{
	}
}
```
### Camel Case
- First letter of each word is capitalized except the first word
- Used for local variables, parameters, etc.
```csharp
public class MyClass
{
	public void MyMethod()
	{
		int myLocalVariable = 0;
	}
}
```
### Hungarian Notation
- Prefixes are used to indicate the type of the variable
- Used for local variables, parameters, etc.
```csharp
public class MyClass
{
	public void MyMethod()
	{
		int iMyLocalVariable = 0;
	}
}
```

## Often used methods
### System.Math
#### Abs()
> Returns the absolute value of a number.
 ```csharp	
int num = -123;
int abs = Math.Abs(num);  // abs will be 123
```
#### Ceiling()
> Returns the smallest integer greater than or equal to the specified number.
 ```csharp
double num = 1.5;
double ceil = Math.Ceiling(num);  // ceil will be 2
```
#### Floor()
> Returns the largest integer less than or equal to the specified number.
 ```csharp
double num = 1.5;
double floor = Math.Floor(num);  // floor will be 1
```
#### Max()
> Returns the larger of two numbers.
 ```csharp
int num1 = 1;
int num2 = 2;
int max = Math.Max(num1, num2);  // max will be 2
```
#### Min()
> Returns the smaller of two numbers.
 ```csharp
int num1 = 1;
int num2 = 2;
int min = Math.Min(num1, num2);  // min will be 1
```
#### Pow()
> Returns a specified number raised to the specified power.
 ```csharp
double num = 2;
double pow = Math.Pow(num, 3);  // pow will be 8
```
#### Round()
> Returns the rounded value of a number.
 ```csharp
double num = 1.5;
double round = Math.Round(num);  // round will be 2
```
#### Sqrt()
> Returns the square root of a number.
 ```csharp
double num = 4;
double sqrt = Math.Sqrt(num);  // sqrt will be 2
```
### System.String
#### Compare()💚
> Compares two strings and returns a value indicating whether one is less than, equal to, or greater than the other.
 ```csharp
string str1 = "abc";
string str2 = "ABC";
int result = string.Compare(str1, str2, true);  // result will be 0
```
#### Concat()💚
> Concatenates two strings.
 ```csharp
string str1 = "abc";
string str2 = "ABC";
string str3 = string.Concat(str1, str2);  // str3 will be "abcABC"
```
#### Contains()
> Returns a value indicating whether a specified substring occurs within this string.
 ```csharp
string str = "abc";
bool contains = str.Contains("b");  // contains will be true
```
#### EndsWith()
> Returns a value indicating whether the specified string occurs at the end of this string.
 ```csharp
string str = "abc";
bool endsWith = str.EndsWith("c");  // endsWith will be true
```
#### Equals()💚
> Determines whether two strings are equal.
 ```csharp
string str1 = "abc";
string str2 = "ABC";
bool equals = str1.Equals(str2, StringComparison.OrdinalIgnoreCase);  // equals will be true
```
#### IndexOf()💚
> Returns the zero-based index of the first occurrence of the specified string in this instance.
 ```csharp
string str = "abc";
int index = str.IndexOf("b");  // index will be 1
```
#### Insert()💚
> Returns a new string in which a specified string is inserted at a specified index position in this instance.
 ```csharp
string str = "abc";
string str2 = str.Insert(1, "d");  // str2 will be "adbc"
```
#### Join()
> Concatenates the elements of an object array, using the specified separator between each element.
 ```csharp
string[] str = { "a", "b", "c" };
string str2 = string.Join(",", str);  // str2 will be "a,b,c"
```
#### IndexOf()
> Returns the zero-based index of the first occurrence of the specified string in this instance.
 ```csharp
string str = "abc";
int index = str.IndexOf("b");  // index will be 1
```
#### Length()💚
> Gets the number of characters in the current String object.
 ```csharp
string str = "abc";
int length = str.Length;  // length will be 3
```
#### PadLeft()💚
> Returns a new string that right-aligns the characters in this instance by padding them on the left with a specified Unicode character, for a specified total length.
 ```csharp
string str = "abc";
string str2 = str.PadLeft(5, '0');  // str2 will be "00abc"
```
#### PadRight()💚
> Returns a new string that left-aligns the characters in this string by padding them on the right with a specified Unicode character, for a specified total length.
 ```csharp
string str = "abc";
string str2 = str.PadRight(5, '0');  // str2 will be "abc00"
```
#### Remove()💚
> Returns a new string in which all the characters in the current instance, beginning at a specified position and continuing through the last position, have been deleted.
 ```csharp
string str = "abc";
string str2 = str.Remove(1);  // str2 will be "a"
```
#### Replace()💚
> Returns a new string in which all occurrences of a specified Unicode character or String in the current string are replaced with another specified Unicode character or String.
 ```csharp
string str = "abc";
string str2 = str.Replace("b", "d");  // str2 will be "adc"
```
#### Split()
> Returns a string array that contains the substrings in this instance that are delimited by elements of a specified string or Unicode character array.
 ```csharp
string str = "a,b,c";
string[] str2 = str.Split(',');  // str2 will be { "a", "b", "c" }
```
#### StartsWith()
> Determines whether the beginning of this string instance matches the specified string.
 ```csharp
string str = "abc";
bool startsWith = str.StartsWith("a");  // startsWith will be true
```
#### Substring()💚
> Retrieves a substring from this instance. The substring starts at a specified character position and has a specified length.
 ```csharp
string str = "abc";
string str2 = str.Substring(1, 2);  // str2 will be "bc"
```
#### ToLower()
> Returns a copy of this string converted to lowercase.
 ```csharp
string str = "ABC";
string str2 = str.ToLower();  // str2 will be "abc"
```
#### ToUpper()
> Returns a copy of this string converted to uppercase.
 ```csharp
string str = "abc";
string str2 = str.ToUpper();  // str2 will be "ABC"
```
#### Trim()
> Removes all leading and trailing white-space characters from the current String object.
 ```csharp
string str = " abc ";
string str2 = str.Trim();  // str2 will be "abc"
```
#### TrimEnd()
> Removes all trailing occurrences of a set of characters specified in an array from the current String object.
 ```csharp
string str = "abc ";
string str2 = str.TrimEnd();  // str2 will be "abc"
```
#### TrimStart()
> Removes all leading occurrences of a set of characters specified in an array from the current String object.
 ```csharp
string str = " abc";
string str2 = str.TrimStart();  // str2 will be "abc"
```
#### IsNullOrEmpty()
> Indicates whether the specified string is null or an Empty string.
 ```csharp
string str = "";
bool isNullOrEmpty = string.IsNullOrEmpty(str);  // isNullOrEmpty will be true
```
#### IsNullOrWhiteSpace()
> Indicates whether a specified string is null, empty, or consists only of white-space characters.
 ```csharp
string str = " ";
bool isNullOrWhiteSpace = string.IsNullOrWhiteSpace(str);  // isNullOrWhiteSpace will be true
```
#### Format()
> Replaces one or more format items in a specified string with the string representation of a specified object.
 ```csharp
string str = string.Format("Hello {0}", "World");  // str will be "Hello World"
```
#### Parse()
> Converts the string representation of a number to its 32-bit signed integer equivalent.
 ```csharp
string str = "123";
int num = int.Parse(str);  // num will be 123
```
#### TryParse()
> Converts the string representation of a number to its 32-bit signed integer equivalent. A return value indicates whether the conversion succeeded or failed.
 ```csharp
string str = "123";
int num;
bool success = int.TryParse(str, out num);  // success will be true
```
#### ToString()
> Returns a string that represents the current object.
 ```csharp
int num = 123;
string str = num.ToString();  // str will be "123"
```
### System.Text.StringBuilder
#### Append()💚
> Appends a copy of the specified string to this instance.
 ```csharp
StringBuilder sb = new StringBuilder();
sb.Append("abc");
```
#### AppendLine()💚
> Appends the default line terminator to the end of the current StringBuilder object.
 ```csharp
StringBuilder sb = new StringBuilder();
sb.AppendLine("abc");
```
#### AppendFormat()
> Replaces one or more format items in this instance with the string representation of a specified object.
 ```csharp
StringBuilder sb = new StringBuilder();
sb.AppendFormat("Hello {0}", "World");
```
#### Insert()
> Inserts the string representation of a specified object into this instance at the specified character position.
 ```csharp
StringBuilder sb = new StringBuilder();
sb.Insert(0, "abc");
```
#### Remove()
> Removes the specified range of characters from this instance.
 ```csharp
StringBuilder sb = new StringBuilder();
sb.Remove(0, 1);
```
#### Replace()
> Replaces all occurrences of a specified character in this instance with another specified character.
 ```csharp
StringBuilder sb = new StringBuilder();
sb.Replace("a", "b");
```
#### ToString()
> Converts the value of this instance to a String.
 ```csharp
StringBuilder sb = new StringBuilder();
string str = sb.ToString();
```
### System.Windows.MessageBox (WPF)💚
#### Show()
> Displays a message box that has a message, title bar caption, button, and icon; and that returns a result.
 ```csharp
MessageBoxResult answer = MessageBox.Show("Hello World?", "Title", MessageBoxButton.YesNo, MessageBoxImage.Question, MessageBoxResult.No);

if (answer == MessageBoxResult.Yes)
{
	// code
}
else
{
	// code
}
```
### System.Windows.Forms.MessageBox (WinForms)
#### Show()
> Displays a message box that has a message, title bar caption, button, and icon; and that returns a result.
 ```csharp
DialogResult answer = MessageBox.Show("Hello World?", "Title", MessageBoxButtons.YesNo, MessageBoxIcon.Question, MessageBoxDefaultButton.Button2);
```
### Microsoft.VisualBasic.Interaction💚
#### InputBox()
> Displays a prompt in a dialog box, waits for the user to input text or click a button, and then returns a string containing the contents of the text box.
 ```csharp
string answer = Interaction.InputBox("Enter a number", "Title", "0");
while (!int.TryParse(answer, out int num))
{
	answer = Interaction.InputBox("Enter a number", "Title", "0");
}
```
### System.DateTime
- DateTime is a data type that represents a date and time
- System.DateTime is a class that contains methods and properties to work with dates and times
```csharp	
DateTime date = DateTime.Now;
```
```csharp	
DateTime date = DateTime.Today;
```
```csharp	
DateTime date = new DateTime(2021, 10, 3);
```
|Prefix		| Property  | Format   				| Description                |
|-----------|-----------|-----------------------|----------------------------|
| datetime.	| Now       | 21/10/2020 0:00:00    | Current date and time      |
| datetime.	| Today     | 21/10/2020 0:00:00    | Current date               |
| date.		| Day       | 1-31     			 	| Day of the month           |
| date.		| DayOfWeek | 0-6      				| Day of the week            |
| date.		| DayOfYear | 1-365    				| Day of the year            |
| date.		| Hour      | 0-23     				| Hour of the day            |
| date.		| Minute    | 0-59     				| Minute of the hour         |
| date.		| Month     | 1-12     				| Month of the year          |
| date.		| Second    | 0-59     				| Second of the minute       |
| date.		| Year      | 1-9999   				| Year                       |
| date.		| Millisecond | 0-999  				| Millisecond of the second  |
| date.		| Ticks     | 0-999999 				| Ticks since 1/1/0001 12:00 |
| date.		| TimeOfDay | 0-23:59  				| Time of the day            |
| date.		| Date      | 1/1/0001 				| Date                       |
|**_** 		| 			 | 						| 					         |
|**Prefix**	| **Method** | 						| **Description**             |
|date.		| AddDays()  | 						| Add days to a date         |
|date.		| AddHours() | 						| Add hours to a date        |
|date.		| AddMinutes() | 					| Add minutes to a date      |
|date.		| AddMonths() | 					| Add months to a date       |
|date.		| AddSeconds() | 					| Add seconds to a date      |
|date.		| Subtract() | 						| Subtract dates             |
|date.		| ToString() | 						| Convert to string          |
|date.		| ToShortDateString() | 			| Convert to short date string |
|date.		| ToLongDateString() | 				| Convert to long date string |
|date.		| ToShortTimeString() | 			| Convert to short time string |
|date.		| ToLongTimeString() | 				| Convert to long time string |
```csharp	
Console.WriteLine(date.DayOfWeek); // Saturday
Console.WriteLine((int)date.DayOfWeek) // 6;
```
### System.TimeSpan
- TimeSpan is a data type that represents a time interval
- System.TimeSpan is a class that contains methods and properties to work with time intervals
```csharp
TimeSpan timeSpan = new TimeSpan(1, 2, 3);
```
|Prefix		| Property  | Format   				| Description                |
|-----------|-----------|-----------------------|----------------------------|
| timespan.	| Days      | 1-9999   				| Days                       |
| timespan.	| Hours     | 0-23     				| Hours                      |
| timespan.	| Minutes   | 0-59     				| Minutes                    |
| timespan.	| Seconds   | 0-59     				| Seconds                    |
| timespan.	| Milliseconds | 0-999  			| Milliseconds           		|
| timespan.	| Ticks     | 0-999999 				| Ticks                      |
| timespan.	| TotalDays | 1-9999   				| Total days                 |
| timespan.	| TotalHours | 0-23     				| Total hours            |
| timespan.	| TotalMinutes | 0-59     			| Total minutes              |
| timespan.	| TotalSeconds | 0-59     			| Total seconds              |
| timespan.	| TotalMilliseconds | 0-999  			| Total milliseconds     |
|**_** 		| 			 | 						| 					         |
|**Prefix**	| **Method** | 						| **Description**             |
|timespan.	| Add()      | 						| Add time to a timespan     |
|timespan.	| Subtract() | 						| Subtract timespans         |
|timespan.	| ToString() | 						| Convert to string          |
```csharp
// constructor
TimeSpan timeSpan = new TimeSpan(1, 2, 3);
Console.WriteLine(timeSpan.ToString()); // 01:02:03

// properties and calculations
TimeSpan timeSpan2 = new TimeSpan(1, 2, 3);
TimeSpan timeSpan3 = new TimeSpan(1, 2, 3);
TimeSpan timeSpan4 = timeSpan2 + timeSpan3;

Console.WriteLine(timeSpan4.ToString()); // 02:04:06
console.WriteLine($"{timeSpan4.Hours}:{timeSpan4.Minutes}:{timeSpan4.Seconds}"); // 2:4:6
```
### System.DispathcerTimer (WPF)
- DispatcherTimer is a class that can be used to execute code at a specified interval
- uses the System.Windows.Threading namespace
```csharp
DispatcherTimer timer = new DispatcherTimer();
timer.Interval = TimeSpan.FromSeconds(1);
timer.Tick += Timer_Tick;
timer.Start();
```
```csharp
private void Timer_Tick(object sender, EventArgs e)
{
	// code
	lblTime.Content = DateTime.Now.ToString("HH:mm:ss");
	lblDate.Content = $"{DateTime.Now.DayOfWeek} {DateTime.Now.Day}/{DateTime.Now.Month}/{DateTime.Now.Year}";
}
```

## Methods and Parameters
### Methods
- private / public
> private = only accessible in the class

> public = accessible in the whole application

- static / non-static
> static = global method

> non-static = local method
- return type / void
> return type = returns a value

> void = does not return a value
- name
- parameters
> input parameters = parameters that are passed to the method

	- By reference
		- ref = the value of the variable is passed to the method
		- out = the value of the variable is passed to the method, but the variable does not have to be initialized

> ref : The parameter passed on, needs to be in the scope of the method where it is passed on, and needs to be initialized

> This allows access to the variable in the method, and the method can change the value of the variable
```csharp	
static void Main( string [] args )
{
	int number = 1;
	WriteMethod(ref number);
	Console.WriteLine(number);  // number will be 2
}
private static void WriteMethod(ref int number)
{
	Console.WriteLine(number);
	number = 2;
}
```
> out : The value of the variable is passed to the method, but the variable does not have to be initialized
```csharp
int number;
private static void WriteMethod(out int number)
{
	Console.WriteLine(1);
	number = 2;
}
```
	- By value
		- the value of the variable is passed to the method
```csharp
int number = 1;
private static void WriteMethod(int number)
{
	Console.WriteLine(number);
	number = 2;
}
```
- body
  
### Void procedure
> method that does not return a value
```csharp	
int numberA = 1;
private static void WriteMethod()
{
	Console.WriteLine(1);
	numberA = 2;
}
```
### Function procedure
> method that returns a value
```csharp
double numberA = 1.5;
roundedNumber = Math.Round(numberA);
```
```csharp
public int AddMethod(int a)
{
	return a + 1;
}
```
### Event procedure
> method that is called when an event occurs
```csharp	
private void Button_Click(object sender, RoutedEventArgs e)
{
	// code
}
```

### Method overloading
> methods with the same name but different parameters
```csharp
public int Add(int a, int b)
{
	return a + b;
}
public int Add(int a, int b, int c)
{
	return a + b + c;
}
```
> methods with the same name and parameters but different return types
```csharp	
public int Add(int a, int b)
{
	return a + b;
}
public int Add(double a, double b)
{
	return a + b;
} double
```

## Data Grouping
### Arrays 💚
- Array = a collection of variables of the same type
- Arrays are zero-based
- Arrays have a fixed size
- Arrays are reference types
- Arrays are declared using square brackets
- Arrays are initialized using curly braces
```csharp
int[] numbers = new int[3]; // { 0, 0, 0 }
```
```csharp
int[] numbers = new int[3] { 1, 2, 3 }; // { 1, 2, 3 }
```
#### Array Methods
##### Length
> Returns the number of elements in the array
```csharp
int[] numbers = new int[3];
int length = numbers.Length; // 3
```
##### IndexOf
> Returns the index of the first occurrence of the specified value in the array
```csharp
int[] numbers = new int[3] { 1, 2, 3 };
int index = Array.IndexOf(numbers, 2); // 1
```
##### Sort
> Sorts the elements in the array
```csharp
int[] numbers = new int[3] { 3, 2, 1 };
Array.Sort(numbers); // { 1, 2, 3 }
```
##### Reverse
> Reverses the order of the elements in the array
```csharp
int[] numbers = new int[3] { 1, 2, 3 };
Array.Reverse(numbers); // { 3, 2, 1 }
```
##### Clear
> Sets a range of elements in the array to zero, false, or null
```csharp
int[] numbers = new int[3] { 1, 2, 3 };
Array.Clear(numbers, 0, 3); // { 0, 0, 0 }
```
##### Copy
> Copies a range of elements from an array starting at the specified source index and pastes them to another array starting at the specified destination index
```csharp
int[] numbers = new int[3] { 1, 2, 3 };
int[] numbers2 = new int[3];
Array.Copy(numbers, numbers2, 3); // { 1, 2, 3 }
```
##### Resize
> Changes the number of elements of a one-dimensional array to the specified new size
```csharp
int[] numbers = new int[3] { 1, 2, 3 };
Array.Resize(ref numbers, 5); // { 1, 2, 3, 0, 0 }
```
##### ToList
> Copies the elements of the array to a new List
```csharp
int[] numbers = new int[3] { 1, 2, 3 };
List<int> numbers2 = numbers.ToList(); // { 1, 2, 3 }
```

### Multidimensional Arrays
- Multidimensional arrays are declared using multiple square brackets
- Multidimensional arrays are initialized using curly braces
```csharp
int[,] numbers = new int[2, 3]; // { { 0, 0, 0 }, { 0, 0, 0 } }
```
```csharp
int[,] numbers = new int[2, 3] { { 1, 2, 3 }, { 4, 5, 6 } }; // { { 1, 2, 3 }, { 4, 5, 6 } }
```
### Jagged Arrays
- Jagged arrays are arrays of arrays
- Jagged arrays are declared using multiple square brackets
```csharp
int[][] numbers = new int[2][];
numbers[0] = new int[3] { 1, 2, 3 };
numbers[1] = new int[3] { 4, 5, 6 };
```
```csharp
int[][] numbers = new int[2][]
{
	new int[3] { 1, 2, 3 },
	new int[3] { 4, 5, 6 }
};
```
### Lists 💚
- List = a collection of variables of the same type
- Lists are zero-based
- Lists have a **dynamic size**
- Lists are reference types
- Lists are declared using angle brackets
- Lists are initialized using curly braces
```csharp
List<int> numbers = new List<int>(); // { }
```
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 }; // { 1, 2, 3 }
```
#### List Methods
##### Add
> Adds an object to the end of the List
```csharp
List<int> numbers = new List<int>();
numbers.Add(1); // { 1 }
```
##### AddRange
> Adds the elements of the specified collection to the end of the List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
numbers.AddRange(new int[] { 4, 5, 6 }); // { 1, 2, 3, 4, 5, 6 }
```
##### Insert
> Inserts an element into the List at the specified index
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
numbers.Insert(0, 4); // { 4, 1, 2, 3 }
```
##### Remove
> Removes the first occurrence of a specific object from the List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
numbers.Remove(2); // { 1, 3 }
```
##### RemoveAt
> Removes the element at the specified index of the List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
numbers.RemoveAt(0); // { 2, 3 }
```
##### RemoveRange
> Removes a range of elements from the List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
numbers.RemoveRange(0, 2); // { 3 }
```
##### Clear
> Removes all elements from the List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
numbers.Clear(); // { }
```
##### Contains
> Determines whether an element is in the List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
bool contains = numbers.Contains(2); // true
```
##### IndexOf
> Searches for the specified object and returns the zero-based index of the first occurrence within the entire List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
int index = numbers.IndexOf(2); // 1
```
##### Sort
> Sorts the elements in the entire List
	
```csharp
List<int> numbers = new List<int>() { 3, 2, 1 };
numbers.Sort(); // { 1, 2, 3 }
```
##### Reverse
> Reverses the order of the elements in the entire List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
numbers.Reverse(); // { 3, 2, 1 }
```
##### ToArray
> Copies the elements of the List to a new array
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
int[] numbers2 = numbers.ToArray(); // { 1, 2, 3 }
```
##### ToList
> Copies the elements of the List to a new List
```csharp
List<int> numbers = new List<int>() { 1, 2, 3 };
List<int> numbers2 = numbers.ToList(); // { 1, 2, 3 }
```
### Dictionaries 💚
- Dictionary = a collection of key-value pairs
- Dictionaries are zero-based
- Dictionaries have a dynamic size
- Dictionaries are reference types
- Dictionaries are declared using angle brackets
- Dictionaries are initialized using curly braces
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>(); // { }
```
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } }; // { { "one", 1 }, { "two", 2 }, { "three", 3 } }
```
#### Dictionary Methods
##### Add
> Adds an element with the specified key and value into the Dictionary
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>();
numbers.Add("one", 1); // { { "one", 1 } }
```
##### Remove
> Removes the element with the specified key from the Dictionary
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } };
numbers.Remove("two"); // { { "one", 1 }, { "three", 3 } }
```
##### Clear
> Removes all elements from the Dictionary
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } };
numbers.Clear(); // { }
```
##### ContainsKey
> Determines whether the Dictionary contains the specified key
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } };
bool containsKey = numbers.ContainsKey("two"); // true
```
##### ContainsValue
> Determines whether the Dictionary contains the specified value
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } };
bool containsValue = numbers.ContainsValue(2); // true
```
##### TryGetValue
> Gets the value associated with the specified key
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } };
int value;
bool success = numbers.TryGetValue("two", out value); // true
```
##### Keys
> Gets a collection containing the keys in the Dictionary
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } };
ICollection<string> keys = numbers.Keys; // { "one", "two", "three" }
```
##### Values
> Gets a collection containing the values in the Dictionary
```csharp
Dictionary<string, int> numbers = new Dictionary<string, int>() { { "one", 1 }, { "two", 2 }, { "three", 3 } };
ICollection<int> values = numbers.Values; // { 1, 2, 3 }
```
### Enumerations
- Enumeration = a set of named constants
- Enumerations are declared using the enum keyword
- Enumerations are declared using Pascal Case
- Enumerations are declared using comma-separated values
```csharp
enum Days { Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday }
```
```csharp
enum Days { Monday = 1, Tuesday = 2, Wednesday = 3, Thursday = 4, Friday = 5, Saturday = 6, Sunday = 7 }
```
#### Enumeration Methods
##### GetNames
> Retrieves an array of the names of the constants in a specified enumeration
```csharp
string[] days = Enum.GetNames(typeof(Days)); // { "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday" }
```
##### GetValues
> Retrieves an array of the values of the constants in a specified enumeration
```csharp
int[] days = (int[])Enum.GetValues(typeof(Days)); // { 1, 2, 3, 4, 5, 6, 7 }
```
##### Parse
> Converts the string representation of the name or numeric value of one or more enumerated constants to an equivalent enumerated object
```csharp
Days day = (Days)Enum.Parse(typeof(Days), "Monday"); // Monday
```
##### TryParse
> Converts the string representation of the name or numeric value of one or more enumerated constants to an equivalent enumerated object
```csharp
Days day;
bool success = Enum.TryParse("Monday", out day); // true
```
### Structs
- Struct = a data type that can contain data members and function members
- Structs are declared using the struct keyword
- Structs are declared using Pascal Case
- Structs are declared using curly braces
```csharp
struct Person
{
	public string Name;
	public int Age;
}
```
```csharp
Person person;
person.Name = "John";
person.Age = 18;
```
### Classes
- Class = a data type that can contain data members and function members
- Classes are declared using the class keyword
- Classes are declared using Pascal Case
- Classes are declared using curly braces
```csharp
class Person
{
	public string Name;
	public int Age;
}
```
```csharp
Person person = new Person();
person.Name = "John";
person.Age = 18;
```
#### Properties
- Property = a member that provides a flexible mechanism to read, write, or compute the value of a private field
- Properties are declared using Pascal Case
- Properties are declared using curly braces
```csharp
class Person
{
	private string _name;
	public string Name
	{
		get { return _name; }
		set { _name = value; }
	}
}
```
```csharp
Person person = new Person();
person.Name = "John";
```
### Constructors
- Constructor = a method that is called when an object is created
- Constructors are declared using the same name as the class
- Constructors are declared using Pascal Case
- Constructors are declared using curly braces
```csharp
class Person
{
	public string Name;
	public int Age;

	public Person(string name, int age)
	{
		Name = name;
		Age = age;
	}
}
```
```csharp
Person person = new Person("John", 18);
```
### Inheritance
- Inheritance = a mechanism in which one class acquires the properties and methods of another class
- Inheritance is declared using the : symbol
```csharp
class Person
{
	public string Name;
	public int Age;
}
class Student : Person
{
	public int StudentNumber;
}
```
```csharp
Student student = new Student();
student.Name = "John";
student.Age = 18;
student.StudentNumber = 123456;
```
### Polymorphism
- Polymorphism = a mechanism in which a subclass can override a method of its superclass
- Polymorphism is declared using the virtual and override keywords
```csharp
class Person
{
	public virtual void Write()
	{
		Console.WriteLine("Person");
	}
}
class Student : Person
{
	public override void Write()
	{
		Console.WriteLine("Student");
	}
}
```
```csharp
Person person = new Person();
person.Write(); // Person
Student student = new Student();
student.Write(); // Student
```
### Abstract Classes
- Abstract class = a class that cannot be instantiated
- Abstract classes are declared using the abstract keyword
- Abstract classes are declared using the same syntax as classes
```csharp
abstract class Person
{
	public string Name;
	public int Age;
}
```
### Interfaces
- Interface = a contract that specifies the members that a class must implement
- Interfaces are declared using the interface keyword
- Interfaces are declared using Pascal Case
- Interfaces are declared using curly braces
```csharp
interface IPerson
{
	string Name { get; set; }
	int Age { get; set; }
}
```
```csharp
class Person : IPerson
{
	public string Name { get; set; }
	public int Age { get; set; }
}
```
### Extension Methods
- Extension method = a method that adds functionality to an existing type
- Extension methods are declared using the static keyword
- Extension methods are declared using the this keyword
```csharp
static class StringExtensions
{
	public static string ToTitleCase(this string str)
	{
		return CultureInfo.CurrentCulture.TextInfo.ToTitleCase(str);
	}
}
```
```csharp
string str = "hello world";
string str2 = str.ToTitleCase(); // Hello World
```
### Generics
- Generic = a class or method that can work with any data type
- Generics are declared using angle brackets
```csharp
class Person<T>
{
	public T Name;
	public T Age;
}
```
```csharp
Person<string> person = new Person<string>();
person.Name = "John";
person.Age = "18";
```
### Delegates
- Delegate = a type that represents references to methods with a particular parameter list and return type
- Delegates are declared using the delegate keyword
- Delegates are declared using Pascal Case
- Delegates are declared using curly braces
```csharp
delegate void WriteDelegate(string str);
```
```csharp
class Person
{
	public string Name;
	public int Age;

	public void Write(string str)
	{
		Console.WriteLine(str);
	}
}
```
```csharp
Person person = new Person();
WriteDelegate writeDelegate = person.Write;
writeDelegate("Hello World"); // Hello World
```
### Events
- Event = a mechanism that enables a class or object to notify other classes or objects when something of interest occurs
- Events are declared using the event keyword
- Events are declared using Pascal Case
- Events are declared using curly braces
```csharp
class Person
{
	public string Name;
	public int Age;

	public event EventHandler<EventArgs> WriteEvent;

	public void Write(string str)
	{
		WriteEvent?.Invoke(this, EventArgs.Empty);
	}
}
```
```csharp
Person person = new Person();
person.WriteEvent += Person_WriteEvent;
person.Write("Hello World");
```
```csharp	
private void Person_WriteEvent(object sender, EventArgs e)
{
	Console.WriteLine("Event");
}
```
### Lambda Expressions
- Lambda expression = an anonymous function that can contain expressions and statements
- Lambda expressions are declared using the => symbol
```csharp
delegate void WriteDelegate(string str);
WriteDelegate writeDelegate = (str) => Console.WriteLine(str);
```
```csharp
class Person
{
	public string Name;
	public int Age;

	public event EventHandler<EventArgs> WriteEvent;

	public void Write(string str)
	{
		WriteEvent?.Invoke(this, EventArgs.Empty);
	}
}
```
```csharp
Person person = new Person();
person.WriteEvent += (sender, e) => Console.WriteLine("Event");

person.Write("Hello World");
```	
### LINQ
- LINQ = a set of features that extend powerful query capabilities to the language syntax of C#
- LINQ is declared using the from, where, select, and orderby keywords
```csharp
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
IEnumerable<int> numbers2 = from number in numbers
							where number > 2
							select number;
```
```csharp
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
IEnumerable<int> numbers2 = numbers.Where(number => number > 2);
```
```csharp
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
IEnumerable<int> numbers2 = numbers.Where(number => number > 2).OrderBy(number => number);
```
```csharp
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
IEnumerable<int> numbers2 = from number in numbers
							where number > 2
							orderby number
							select number;
```

# WPF Essentials
## Event Procedures
- Event procedure = method that is called when an event occurs
- Event handlers _can_ but **don't need to be** declared in the XAML file
- Event procedures are declared in the code-behind file

### Xaml handler + code-behind
```html	
<Button Click="Button_Click" />
```
```csharp
private void Button_Click(object sender, RoutedEventArgs e)
{
	// code
}
```
### Code-behind-only handler
```html	
<Button x:Name="Button1" />
<Button x:Name="Button2" />
```
```csharp
public MainWindow()
{
	InitializeComponent();

	Button1.Click += Button_Click;
	Button2.Click += Button_Click;
	// Attach the event handler to other buttons as needed
}

private void Button_Click(object sender, RoutedEventArgs e)
{
	Button clickedButton = sender as Button;
	if (clickedButton != null)
	{
		// Use the button's Name, Content, or another property to identify it
		MessageBox.Show("Button clicked: " + clickedButton.Name);
	}
}
```

## Event Types
### Click Events
- MouseDown
- MouseUp
- Click
```html
<Button Click="Button_Click" />
```
```csharp
private void Button_Click(object sender, RoutedEventArgs e)
{
	// code
}
```
### Key Events
- KeyDown
- KeyUp
- KeyPress
```html
<TextBox KeyDown="TextBox_KeyDown" />
```
```csharp
TxtResult.Text = "";
private void TextBox_KeyDown(object sender, KeyEventArgs e)
{
	if (e.Key >= Key.NumPad0 && e.Key <= Key.NumPad9)
	{
		// Test for numeric keys on the numeric keypad.
		TxtResult.Text = $"Numeriek {e.Key}";
	}
	else if (e.Key == Key.K)
	{
		TxtResult.Text = "k or K";
	}
	else
	{
		TxtResult.Text = "Not a numeric key";
		e.Handled = true;
	}
}
```
> Some common keys
```csharp
e.Key.A 		<> e.Key.Z
e.Key.D0 		<> e.Key.D9
e.key.Numpad0 	<> e.key.Numpad9
e.key.F1 		<> e.key.F24
e.key.Enter, 	e.key.Return, 	e.key.Space, 	e.key.Tab
e.key.Escape, 	e.key.Back, 	e.key.Delete, 	e.key.Insert
e.key.Home, 	e.key.End, 		e.key.PageUp, 	e.key.PageDown
e.key.Up, 		e.key.Down, 	e.key.Right, 	e.key.Left
```
> Key modifiers
> 
💚 AltGr is a combination of the Alt and Control keys
```csharp
e.KeyboardDevice.Modifiers == ModifierKeys.Alt
e.KeyboardDevice.Modifiers == ModifierKeys.Control
e.KeyboardDevice.Modifiers == ModifierKeys.Shift
e.KeyboardDevice.Modifiers == ModifierKeys.Windows
``` 

## WPF Elements
### Image
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Source    | Gets or sets the image source. |
| Width     | Gets or sets the width of the Image. |
| Height    | Gets or sets the height of the Image. |
| Stretch   | Gets or sets a value that describes how an Image should be stretched to fill the destination rectangle. |
| Visibility | Gets or sets the user interface (UI) visibility of this element. |
| Opacity   | Gets or sets the opacity factor applied to the entire Image when it is rendered in the user interface (UI). |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<Image x:Name="ImgLogo" Source="Images/Logo.png" Width="100" Height="100" Stretch="Fill" Visibility="Visible" Opacity="1" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### TextBlock
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Text      | Gets or sets the text contents of a TextBlock. |
| TextWrapping | Gets or sets how the TextBlock should wrap text. |
| TextAlignment | Gets or sets the horizontal alignment of the text content. |
| FontSize  | Gets or sets the font size for the TextBlock. |
| FontWeight | Gets or sets the top-level font weight to select from the font family for the TextBlock. |
| FontStyle | Gets or sets the font style for the TextBlock. |
| FontFamily | Gets or sets the font family for the TextBlock. |
| Foreground | Gets or sets the Brush to apply to the text contents of the TextBlock. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<TextBlock x:Name="TxtTitle" Text="Title" TextWrapping="Wrap" TextAlignment="Center" FontSize="20" FontWeight="Bold" FontStyle="Normal" FontFamily="Arial" Foreground="Black" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### TextBox
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Text      | Gets or sets the text contents of a TextBox. |
| TextWrapping | Gets or sets how the TextBox should wrap text. |
| TextAlignment | Gets or sets the horizontal alignment of the text content. |
| FontSize  | Gets or sets the font size for the TextBox. |
| FontWeight | Gets or sets the top-level font weight to select from the font family for the TextBox. |
| FontStyle | Gets or sets the font style for the TextBox. |
| FontFamily | Gets or sets the font family for the TextBox. |
| Foreground | Gets or sets the Brush to apply to the text contents of the TextBox. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<TextBox x:Name="TxtInput" Text="Input" TextWrapping="Wrap" TextAlignment="Center" FontSize="20" FontWeight="Bold" FontStyle="Normal" FontFamily="Arial" Foreground="Black" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### Button
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Content   | Gets or sets the content of a ContentControl. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<Button x:Name="BtnButton" Content="Button" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### CheckBox
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Content   | Gets or sets the content of a ContentControl. |
| IsChecked | Gets or sets whether the CheckBox is checked. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<CheckBox x:Name="ChkCheckBox" Content="CheckBox" IsChecked="False" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### RadioButton
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Content   | Gets or sets the content of a ContentControl. |
| IsChecked | Gets or sets whether the RadioButton is checked. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<RadioButton x:Name="RdbRadioButton" Content="RadioButton" IsChecked="False" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### ListBox
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| ItemsSource | Gets or sets a collection used to generate the content of the ListBox. |
| SelectedItem | Gets or sets the first item in the current selection or returns null if the selection is empty. |
| SelectedIndex | Gets or sets the index of the first item in the current selection or returns negative one (-1) if the selection is empty. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<ListBox x:Name="LstListBox" ItemsSource="{Binding}" SelectedItem="{Binding}" SelectedIndex="-1" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### ComboBox
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| ItemsSource | Gets or sets a collection used to generate the content of the ComboBox. |
| SelectedItem | Gets or sets the first item in the current selection or returns null if the selection is empty. |
| SelectedIndex | Gets or sets the index of the first item in the current selection or returns negative one (-1) if the selection is empty. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<ComboBox x:Name="CmbComboBox" ItemsSource="{Binding}" SelectedItem="{Binding}" SelectedIndex="-1" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### ProgressBar
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Value     | Gets or sets the current position of the ProgressBar. |
| Minimum   | Gets or sets the minimum possible Value of the ProgressBar. |
| Maximum   | Gets or sets the maximum possible Value of the ProgressBar. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |
</details>

```html
<ProgressBar x:Name="PgbProgressBar" Value="0" Minimum="0" Maximum="100" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### Slider
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Value     | Gets or sets the current position of the Slider. |
| Minimum   | Gets or sets the minimum possible Value of the Slider. |
| Maximum   | Gets or sets the maximum possible Value of the Slider. |
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<Slider x:Name="SldSlider" Value="0" Minimum="0" Maximum="100" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```

### ScrollViewer
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalScrollBarVisibility | Gets or sets a value that indicates whether a horizontal ScrollBar should be displayed. |
| VerticalScrollBarVisibility | Gets or sets a value that indicates whether a vertical ScrollBar should be displayed. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<ScrollViewer x:Name="ScvScrollViewer" Margin="0" HorizontalScrollBarVisibility="Auto" VerticalScrollBarVisibility="Auto" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```
## WPF Panels
### Grid
- Grid = a layout panel that arranges child elements in rows and columns

<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<Grid x:Name="GrdGrid" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True">
	<Grid.RowDefinitions>
		<RowDefini
	</Grid.RowDefinitions>
	<Grid.ColumnDefinitions>
		<ColumnDefinition Width="Auto" />
		<ColumnDefinition Width="*" />
	</Grid.ColumnDefinitions>
</Grid>
```
<details>
  <summary>Properties</summary>

| Property | Description |
| --- | --- |
| Grid.Row | Gets or sets the row number of a child element in a Grid. |
| Grid.Column | Gets or sets the column number of a child element in a Grid. |
| Grid.RowSpan | Gets or sets a value that indicates the number of rows that a child element spans within a Grid. |
| Grid.ColumnSpan | Gets or sets a value that indicates the number of columns that a child element spans within a Grid. |
| Grid.RowDefinitions | Gets a RowDefinitionCollection defined on this instance of Grid. |
| Grid.ColumnDefinitions | Gets a ColumnDefinitionCollection defined on this instance of Grid. |
| Grid.IsSharedSizeScope | Gets or sets a value that indicates whether this Grid is the root element where column sizing properties are honored. |
| Grid.ShowGridLines | Gets or sets a value that indicates whether grid lines are visible within this Grid. |
| Grid.Background | Gets or sets a brush that provides the background of the control. |

</details>

```html
<Grid x:Name="GrdGrid" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True">
	<Grid.RowDefinitions>
		<RowDefinition Height="Auto" />
		<RowDefinition Height="*" />
	</Grid.RowDefinitions>
	<Grid.ColumnDefinitions>
		<ColumnDefinition Width="Auto" />
		<ColumnDefinition Width="*" />
	</Grid.ColumnDefinitions>
	<Label Grid.Row="0" Grid.Column="0" Content="Label" />
	<TextBox Grid.Row="0" Grid.Column="1" Text="TextBox" />
	<Button Grid.Row="1" Grid.Column="0" Grid.ColumnSpan="2" Content="Button" />
</Grid>
```
### Canvas
- Canvas = a layout panel that arranges child elements by coordinates relative to each other

<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Margin    | Gets or sets the outer margin of an element. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<Canvas x:Name="CnvCanvas" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```
<details>
  <summary>Properties</summary>

| Property | Description |
| --- | --- |
| Canvas.Left | Gets or sets the distance between the left side of an element and the left side of its parent Canvas. |
| Canvas.Top | Gets or sets the distance between the top of an element and the top of its parent Canvas. |
| Canvas.Right | Gets or sets the distance between the right side of an element and the right side of its parent Canvas. |
| Canvas.Bottom | Gets or sets the distance between the bottom of an element and the bottom of its parent Canvas. |
| Canvas.ZIndex | Gets or sets a value that represents the order on the z-plane in which an element appears. |
| Canvas.Background | Gets or sets a brush that provides the background of the control. |

</details>

```html
<Canvas x:Name="CnvCanvas" Margin="0" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True">
	<Label Canvas.Left="0" Canvas.Top="0" Content="Label" />
	<TextBox Canvas.Left="100" Canvas.Top="0" Text="TextBox" />
	<Button Canvas.Left="0" Canvas.Top="100" Content="Button" />
</Canvas>
```

### StackPanel
- StackPanel = a layout panel that arranges child elements into a single line that can be oriented horizontally or vertically

<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Margin    | Gets or sets the outer margin of an element. |
| Orientation | Gets or sets a value that indicates the dimension by which child elements are stacked. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<StackPanel x:Name="StpStackPanel" Margin="0" Orientation="Vertical" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```
<details>
  <summary>Properties</summary>

| Property | Description |
| --- | --- |
| StackPanel.Background | Gets or sets a brush that provides the background of the control. |

</details>

```html
<StackPanel x:Name="StpStackPanel" Margin="0" Orientation="Vertical" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True">
	<Label Content="Label" />
	<TextBox Text="TextBox" />
	<Button Content="Button" />
</StackPanel>
```

### WrapPanel
- WrapPanel = a layout panel that arranges child elements into a single line that can be oriented horizontally or vertically and wraps child elements to the next line when there is no space available

<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Margin    | Gets or sets the outer margin of an element. |
| Orientation | Gets or sets a value that indicates the dimension by which child elements are stacked. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<WrapPanel x:Name="WrpWrapPanel" Margin="0" Orientation="Vertical" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```
<details>
  <summary>Properties</summary>

| Property | Description |
| --- | --- |
| WrapPanel.Background | Gets or sets a brush that provides the background of the control. |

</details>

```html
<WrapPanel x:Name="WrpWrapPanel" Margin="0" Orientation="Vertical" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True">
	<Label Content="Label" />
	<TextBox Text="TextBox" />
	<Button Content="Button" />
</WrapPanel>
```

### DockPanel
- DockPanel = a layout panel that arranges child elements relative to each other, either horizontally or vertically, based on the value of an attached Dock property
  
<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Margin    | Gets or sets the outer margin of an element. |
| LastChildFill | Gets or sets a value that indicates whether the last child element within a DockPanel stretches to fill the remaining available space. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<DockPanel x:Name="DckDockPanel" Margin="0" LastChildFill="True" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```
<details>
  <summary>Properties</summary>

| Property | Description |
| --- | --- |
| DockPanel.Background | Gets or sets a brush that provides the background of the control. |

</details>

```html
<DockPanel x:Name="DckDockPanel" Margin="0" LastChildFill="True" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True">
	<Label DockPanel.Dock="Top" Content="Label" />
	<TextBox DockPanel.Dock="Top" Text="TextBox" />
	<Button DockPanel.Dock="Top" Content="Button" />
</DockPanel>
```

### Viewbox
- Viewbox = a layout control that stretches or shrinks its content to fit the available space

<details>
  <summary>Properties</summary>

| Property  | Description                |
|-----------|----------------------------|
| Margin    | Gets or sets the outer margin of an element. |
| Stretch | Gets or sets a value that describes how a Viewbox stretches its child to fill the available space. |
| StretchDirection | Gets or sets a value that indicates the dimension by which child elements are stretched. |
| HorizontalAlignment | Gets or sets the horizontal alignment characteristics applied to this element when it is composed within a parent element, such as a panel or items control. |
| VerticalAlignment | Gets or sets the vertical alignment characteristics applied to this element when it is composed within a parent element such as a panel or items control. |
| IsEnabled | Gets or sets a value indicating whether this element is enabled in the user interface (UI). |

</details>

```html
<Viewbox x:Name="VbxViewbox" Margin="0" Stretch="Uniform" StretchDirection="Both" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True" />
```
<details>
  <summary>Properties</summary>

| Property | Description |
| --- | --- |
| Viewbox.Background | Gets or sets a brush that provides the background of the control. |

</details>

```html
<Viewbox x:Name="VbxViewbox" Margin="0" Stretch="Uniform" StretchDirection="Both" HorizontalAlignment="Left" VerticalAlignment="Top" IsEnabled="True">
	<Label Content="Label" />
	<TextBox Text="TextBox" />
	<Button Content="Button" />
</Viewbox>
```



