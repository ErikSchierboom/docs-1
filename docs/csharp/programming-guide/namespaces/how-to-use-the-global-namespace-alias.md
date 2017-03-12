---
title: "How to: Use the Global Namespace Alias (C# Programming Guide) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "aliases [C#]"
  - "namespaces [C#], global namespace qualifier"
  - "global namespace [C#]"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# How to: Use the Global Namespace Alias (C# Programming Guide)
[!INCLUDE[csharpbanner](../../../csharp/includes/csharpbanner.md)]

The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.  
  
 For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/using.cs#1)]  
  
 [!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#1)]  
  
 Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:  
  
 [!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#2)]  
  
 However, you can work around this error by using `global::System.Console`, like this:  
  
 [!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#3)]  
  
 When the left identifier is `global`, the search for the right identifier starts at the global namespace. For example, the following declaration is referencing `TestApp` as a member of the global space.  
  
 [!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#4)]  
  
 Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened. However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another. In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.  
  
## Example  
 In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace. Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=fullName> was created using this alias instead of the namespace.  
  
 [!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#5)]  
  
 **A 1**  
**B 2**  
**C 3**   
## See Also  
 [C# Programming Guide](../../../csharp/programming-guide/index.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)   
 [. Operator](../../../csharp/language-reference/operators/member-access-operator.md)   
 [:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)