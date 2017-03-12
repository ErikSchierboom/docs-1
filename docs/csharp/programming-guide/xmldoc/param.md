---
title: "&lt;param&gt; (C# Programming Guide) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "param"
  - "<param>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<param> C# XML tag"
  - "param C# XML tag"
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;param&gt; (C# Programming Guide)
[!INCLUDE[csharpbanner](../../../csharp/includes/csharpbanner.md)]

## Syntax  
  
```  
<param name="name">description</param>  
```  
  
#### Parameters  
 `name`  
 The name of a method parameter. Enclose the name in double quotation marks (" ").  
  
 `description`  
 A description for the parameter.  
  
## Remarks  
 The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method. To document multiple parameters, use multiple \<param> tags.  
  
 The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.  
  
 Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-csharp-compiler-options.md) to process documentation comments to a file.  
  
## Example  
 [!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/param_1.cs)]  
  
## See Also  
 [C# Programming Guide](../../../csharp/programming-guide/index.md)   
 [Recommended Tags for Documentation Comments](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)