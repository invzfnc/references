Declaration
```csharp
public static delegate MathDelegate(int a, int b);
```

Defining delegate variable
```csharp
MathDelegate mathDelegate = Add;
// Or MathDelegate mathDelegate = new MathDelegate(Add);
// Add is a method that has the same signature as MathDelegate
```

Under the hood, delegate is a class, which means that it could be:
- Assigned `null`
- Defined anywhere a class can be defined

Using the delegate
```csharp
mathDelegate(1, 2);
mathDelegate.Invoke(1, 2);  // Same as above, but more explicit
```

`Action<>` Delegate
For methods with void returnt type (that does something)
```csharp
public delegate void Action<T>(T arg);
public delegate void Action<T1, T2>(T1 arg1, T2 arg2);
public delegate void Action<T1, T2, T3>(T1 arg1, T2 arg2, T3 arg3);
... // Up to 16 args
```

`Func<>` Delegate
For methods with return types
```csharp 
public delegate TResult Func<TResult>();
public delegate TResult Func<TResult, T>(T arg);
public delegate TResult Func<TResult, T1, T2>(T1 arg, T2 arg);
... // Up to 16 args
	```