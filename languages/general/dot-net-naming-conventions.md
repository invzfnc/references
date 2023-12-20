**Do not** use underscores for identifier

`PascalCasing` is used for all identifiers except parameter names
`camelCasing` is used only for parameter names

Example:

```csharp
// Namespace
namespace System.Security

//Type
public class StreamReader

//Interface
public interface IEnumerable

//Class
public class Object

//Method
public virtual string ToString()

//Property
public int Length { get; set; }

//Event
public event EventHandler Exited;

//Field
public const Min = 0;

//Enum value
public enum FileMode 
{
	Append,
	...
}

//Parameter 
public static int ToInt32(string value);


```
