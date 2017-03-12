---
title: "How to: Access an Array Element with a Pointer (C# Programming Guide) | Microsoft Docs"
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
  - "pointers [C#], array access"
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# How to: Access an Array Element with a Pointer (C# Programming Guide)
[!INCLUDE[csharpbanner](../../../csharp/includes/csharpbanner.md)]

In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`. The operation p[e] is equivalent to *(p+e). Like C and C++, the pointer element access does not check for out-of-bounds errors.  
  
## Example  
 In this example, 123 memory locations are allocated to a character array, `charPointer`. The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.  
  
 Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.  
  
 [!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#11)]  
  
 [!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#12)]  
  
 **Uppercase letters:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Lowercase letters:**  
**abcdefghijklmnopqrstuvwxyz**   
## See Also  
 [C# Programming Guide](../../../csharp/programming-guide/index.md)   
 [Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Types](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)