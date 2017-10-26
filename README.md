# GeoJson.NET for Unity
GeoJSON.Net is a .NET library for the [RFC 7946 The GeoJSON Format](https://tools.ietf.org/html/rfc7946) and it uses and provides [Newtonsoft Json.NET](http://json.codeplex.com) converters for serialization and deserialization of GeoJSON data.

## Why is a port needed?
Unity has historically used .NET 3.5 which limited C# programmers to C# 3.0 language features. As of [Unity 2017](https://blogs.unity3d.com/2017/07/11/introducing-unity-2017/), an experimental .NET 4.6 Runtime version has been introduced allowing C# 6.0 features. However, because GeoJson.NET is written with the latest language features, it is still incompatible with Unity. This project will serve as a continuous backport of GeoJson.NET to .NET 4.6 while preserving features and bug-fixes.


## Installation & Usage

Download and import the .unitypackage to your project.

### Serialization

```csharp
Position position = new Position(51.899523, -2.124156);
Point point = new Point(position);

string json = JsonConvert.SerializeObject(point);
```

### Deserialization

```csharp
string json = "{\"coordinates\":[-2.124156,51.899523],\"type\":\"Point\"}";

Point point = JsonConvert.DeserializeObject<Point>(json);
```

See the [Tests](https://github.com/GeoJSON-Net/GeoJSON.Net/tree/master/src/GeoJSON.Net.Tests) for more examples.
