# Unity Study Guide

## Programming

### Unity's component basics

A gameobject is the root object for anything in the scene graph.

Components are attached onto gameobjects.

All gameobjects start with a default component of Transform, which records the Position, Rotation, and Scale of gameobject.

`gameobject.AddComponent<T>()` and `gameobject.GetComponent<T>()` are the most common methods for adding and modifying gameobject behaviors.

You can create custom components easily by creaing new scripts.

### Unity's Lifecycle

`Awake()` : runs before `Start()`

`Start()` : Runs at the start of the game. This is where you would initialize... anything.

`Update()` : Runs every frame. This is where you make things uh... update.

`OnDestroy()` : Runs before the game object is destroyed. This is where you clean things up.

There are more lifecycle hooks, but these are the common ones.

### Package management

Unity's built-in package management is poor.

To create a .unitypackage simply converts a folder. Not a lot of info tracked. To import a .unitypackage is just putting that folder somewhere in the project.

The best management _at this moment_ is Git Submodule. It allows for much better version management, and keeps the project repo separate from its dependencies.

> Another option is Nuget and I've heard good things but haven't tried.

That being said unity is making strides with their package manager for internal plugins. It may extend to items in the asset store and any 3rd-party packages very soon, and become the de facto method.

### C\# Data Structures

the native C\# **Array** is usually used with a fixed size. It can be resized, but **List** is better designed for working with array sizes that changes.

When pairs of information is needed, use Dictionary, which stores Key and Value pairs.

### C\# Types

Common Bulit-in types of C\# are:

```text
bool, string, float, int
```

Other C\# types \(**TODO** learn more about them\):

```text
byte, sbyte, char, decimal, double, uint, long, ulong, short, ushort
```

Finally the type `object` is the root of all types, and is special.

To convert a type from one to another, use `(targetType)variable` syntax.

```text
string aString = (string)aFloat;
```

### C\# Accessibility Levels

* public: accessible by other classes. Also creates UI in Unity Editor _\*_
* private: accessible only within the class itself.
* protected: accessible by the class and its derivative classes.
* internal: "Access is limited to the current assembly.". I don't really get this one or how it should be used.
* protected internal: ???
* private protected: ???

\*Normally Unity Editor would only create UI for public fields of a class, via a process called "serializing". However you can add the attribute `[SerializeField]` to a private field, to force serialization and create editor UI. [Read more here](https://docs.unity3d.com/ScriptReference/SerializeField.html).

### Networking

HTTP is available in .NET

WebSocket requires 3rd party library

### C\# Garbage Collection

It's automatic, usually there's no need to free memory manually.

### Performance enhancement

The [Unity Profiler](https://unity3d.com/cn/learn/tutorials/temas/performance-optimization/diagnosing-performance-problems-using-profiler-window) is essential to identifying memory leaks and performance problems.

Watch out for initialization; too much would cause memory problem. Try not to initialize inside the update loop.

**Pooling**, or initializing a pool of elements up-front and reusing them, can help with memory issue involving large number of elements. e.g. Particles.

### Producing a build

Two places to pay attention to.

**Build Setting**

This is where you choose which platform you'd build for. Remember to click "Switch Platform" after selecting one, because Unity UI is very intuitive.

**Player Setting**

This is where you configure things like executable icon, name, resolution, splash image, and more. VR / AR settings are also found here.

### Prefabs

Prefab stands for prefabrication. They are templates to duplicate gameobject, or gameobject groups.

Anything in the scene graph can be turned into a prefab, by dragging them into the project folder. This creates a .prefab file.

The component values would be stored in the prefab. Unity Editor offers some UI for highlighting values changed between the prefab and its instance, as well as buttons for reverting to the prefab's value, or applying instance's value back to the prefab.

`Instantiate()` is a common method of initializing instances of prefab.

### Scriptable Objects

Scriptable objects are assets that represents some custom block of data, that can be shared between instances...??? **TODO** need to learn more.

I hear they are neat for [organizing and iterating UI styles](https://www.youtube.com/watch?v=HkUSmI7F304).

## Assets

### Images

Unity supports the common image formats out there.

### Videos

Unity's VideoPlayer used to have a bad reputation, but has gotten better recently.

That being said, [AVPro Video](http://renderheads.com/product/avpro-video/) is still the industry standard for video playback with more performance, control, features, and platform support.

### 3D Assets

To display a 3D object in Unity \(or any 3D engine\), you need: A mesh \(model\). A material.

The material needs: A shader. And often, the shader uses textures.

If the 3D object comes with animation, there are additional assets needed.

#### 3D Animations

Incomplete.

#### Rigging

Incomplete.

### Fonts

Incomplete.

### Audio

Incomplete.

## Considerations for VR

### Post Processing Stack

Post Processing Stack is essential to an aesthetic experience. Special considerations need to be taken when we apply them to a VR experience, however.

**Bad Post Processing FX:**

* Ambient Occlusion: can get expensive computing-wise, because of VR's double camera.
* Depth of Field: VR already allows user natural depth of field. Having artificial ones mess with the brain.
* Motion Blur: This will make people throw up. Don't do it!

**Good Post Processing FX:**

* Eye adaption: fast computation
* Bloom: fast; plus it allows us to utilize glowing objects for indication in VR.
* Color Grading: fast, and great for a e s t h e t i c

### Locomotion

Locomotion in VR has to solve two problems:

* How to move the VR player while player's room for movement is limited
* How to avoid inducing motion sickness, as a result of perceived motion and bodily motion mismatch

The most accepted way of locomotion now is teleporting: point to a spot, screen fades to black, then lits back up, and you are there.

There are many other novel ways of movements out there. Often it is context-dependent. This is an area worthy of further research.

