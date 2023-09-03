# IoCContainer - Inversion of Control Container in C#

This project contains a simple implementation of an Inversion of Control Container (IoC Container) in C#. The purpose of this wrapper is to allow automatic dependency resolution in an application.

## Use

### Registering types

To use the `IoCContainer`, you must first register the associations between contract and implementation types. You can do it in two ways:

```csharp
usingSystem;
using ReflectionSample;

var container = new IoCContainer();

// Registering generic types
container.Register<IContractType, ImplementationType>();

// Or registering non-generic types
container.Register(typeof(IContractType), typeof(ImplementationType));
```
## Resolving dependencies
Once you have registered the types, you can resolve dependencies by calling the Resolve<TContract>() method:

```csharp
var instance = container.Resolve<IContractType>();
```

The container will search for the corresponding implementation based on the specified contract type and create an instance for you.

## Grades
* The container is capable of handling generic types automatically.
* Make sure implementations are properly registered before attempting to resolve them.

## Usage Example

``` csharp
var container = new IoCContainer();

// Registering types
container.Register<IService, DeployedService>();

// Resolving dependencies
var service = container.Resolve<IService>();

service.DoSomething();
```
