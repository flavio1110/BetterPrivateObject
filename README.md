# BetterPrivateObject

[![Build status](https://ci.appveyor.com/api/projects/status/nux5awembyvfan6b?svg=true)](https://ci.appveyor.com/project/douglasaguiar/betterprivateobject)
[![Nuget count](http://img.shields.io/nuget/v/BetterPrivateObject.svg)](https://www.nuget.org/packages/BetterPrivateObject/)
[![Nuget downloads](http://img.shields.io/nuget/dt/BetterPrivateObject.svg)](https://www.nuget.org/packages/BetterPrivateObject/)
[![Issues open](http://img.shields.io/github/issues-raw/douglasaguiar/BetterPrivateObject.svg)](https://github.com/douglasaguiar/BetterPrivateObject/issues)

Better private object, using dynamic object. Yes, it's very cool!

If you want to test a private method like this:

```csharp
public class Subject
{
	private int annoyingPrivateSum(int num1, int num2) { return num1+num2; }
	private static int annoyingPrivateStaticSum(int num1, int num2) { return num1+num2; }
}
```

You just have to do this:

```csharp
[TestMethod]
public void TestPrivateMethod()
{
	dynamic subjectPO = new PrivateObject<Subject>();

	int result = subjectPO.annoyingPrivateSum(1, 1);

	Assert.AreEqual(2, result);
}

[TestMethod]
public void TestPrivateStaticMethod()
{
	dynamic subjectPO = new PrivateType<Subject>();

	int result = subjectPO.annoyingPrivateStaticSum(1, 1);

	Assert.AreEqual(2, result);
}
```

Nice!?
