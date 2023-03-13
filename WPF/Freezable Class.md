What is Freezable class?
> A base class in WPF that provides a way to create objects that can be made **immutable** after they have been initialized.
> when Freezable objects are frozen, its properties can no longer to be modified.

Scenerio to be used:
- *Where you want to create **a large number of identical objects** and then **reuse** them throughout the application.(by freezing the objects, we can ovoid the overhead of creating new objects each time they are needed)*

Code snippet:
```
public class MyFreezable : Freezable
{
    public static readonly DependencyProperty MyPropertyProperty = DependencyProperty.Register(
        "MyProperty", typeof(int), typeof(MyFreezable), new PropertyMetadata(default(int)));

    public int MyProperty
    {
        get => (int)GetValue(MyPropertyProperty);
        set => SetValue(MyPropertyProperty, value);
    }

    protected override Freezable CreateInstanceCore()
    {
        return new MyFreezable();
    }
}

var myFreezable = new MyFreezable();
myFreezable.MyProperty = 42;
myFreezable.Freeze();

// You can now use the myFreezable object as a resource in your application
// For example, you can use it as the DataContext of a control
myControl.DataContext = myFreezable;
```
