```csharp
public event EventHandler PointChanged;
// public event DELEGATE EventName/What has changed;
```

`EventHandler` delegate
Pre-defined delegate made for simple events
Signature: 
```csharp
public delegate void System.EventHandler(object sender, System.EventArgs e);
```

Example:
Property changed -> Setter in property calls `OnChanged` method
`OnChanged` method:
Invoke the delegates if the event is not null (No method is attached to event if event is null)

```csharp
public class Point
    {
        public event EventHandler PointChanged;
		// public event Delegate SomethingChanged;

        private int x;
        private int y;

        public int X
        { 
            get { return x; }
            set
            {
                x = value;
                OnPointChanged();  // Calls the OnChanged method

            }
        }
        public int Y
        { 
            get { return y; }
            set 
            { 
                y = value;
                OnPointChanged();
            }
        }

        public Point(string name, int x, int y)
        {
            Name = name;
            X = x;
            Y = y;
        }

        private void OnPointChanged()
        {
            if (PointChanged != null)  // If there is method attached to it
                PointChanged.Invoke(this, EventArgs.Empty);
        }
```

```csharp
// Same signature as EventHandler (part of definition of PointChanged event)
private static void HandlePointChanged(object sender, EventArgs e)
{
	Console.WriteLine("Point changed!");
}

public static void NotMain(string[] args)
{
	Point point = new Point(1, 2);
	point.PointChanged += HandlePointChanged;
	point.X = 5;  // HandlePointChanged is called; Prints "Point Changed!"
}
```