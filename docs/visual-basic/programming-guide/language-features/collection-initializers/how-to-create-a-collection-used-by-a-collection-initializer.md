---
title: "How to: Create a Collection Used by a Collection Initializer (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "collection initializers [Visual Basic]"
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Collection Used by a Collection Initializer (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer. This `Add` method is used to populate the collection with the values from the collection initializer.  
  
## Example  
 The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`. The `Add` method enables you to use the shortened collection initializer syntax.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-a-collecti_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-a-collecti_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-a-collecti_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-a-collecti_4.vb)]  
  
## See Also  
 [Collection Initializers](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)