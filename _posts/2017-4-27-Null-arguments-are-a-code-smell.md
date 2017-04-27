---
layout: post
title: Null arguments are a code smell
---

!["Pipes" Chris Smart by ]({{ site.baseurl }}/images/5865519128_224430423c_o.jpg)

Nulls are bad news. Most .NET developers learn to dread them after seeing yet another "Object reference is not set to an instance of an object" error in production. The inventor of the null reference (perhaps not a title with lead with on your resume) has called it a [billion dollar mistake](https://www.infoq.com/presentations/Null-References-The-Billion-Dollar-Mistake-Tony-Hoare). 

Apart from the pain they cause in bringing systems to a halt, I have a particular frustration with them when they are used as data input. Too many boolean parameters are hard to parse when reading code and require the programmer to lean heavily on tooling to make sure they're passing in the right combination:

```
WriteFile(false, true, true, false, 3, true);
```

When you declare a variable and assign an object to it in C#, you're really assigning a reference to the variable. Thus whenever you need to supply a reference type to a function, you can always provide null (barring [special tooling](https://github.com/Fody/NullGuard)). What you should avoid when designing your APIs is to attach meaning to null arguments. A null represents an absence of information, a language feature that shouldn't be explicitly included in the design of your contracts.
