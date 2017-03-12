---
title: "How to: Dial Modems Attached to Serial Ports in Visual Basic | Microsoft Docs"
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
  - "modems, dialing"
  - "serial ports, dialing"
  - "My.Computer.Ports object"
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Dial Modems Attached to Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

This topic describes how to use `My.Computer.Ports` to dial a modem in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Typically, the modem is connected to one of the serial ports on the computer. For your application to communicate with the modem, it must send commands to the appropriate serial port.  
  
### To dial a modem  
  
1.  Determine which serial port the modem is connected to. This example assumes the modem is on COM1.  
  
2.  Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port. For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     The `Using` block allows the application to close the serial port even if it generates an exception. All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#28)]  
  
3.  Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#29)]  
  
4.  Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#30)]  
  
## Example  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#27)]  
  
 This code example is also available as an IntelliSense code snippet. In the code snippet picker, it is located in **Connectivity and Networking**. For more information, see [Code Snippets](/visual-studio/ide/code-snippets).  
  
## Compiling the Code  
 This example requires a reference to the <xref:System?displayProperty=fullName> namespace.  
  
## Robust Programming  
 This example assumes the modem is connected to COM1. We recommend that your code allow the user to select the desired serial port from a list of available ports. For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 This example uses a `Using` block to make sure that the application closes the port even if it throws an exception. For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
 In this example, the application disconnects the serial port after it dials the modem. Realistically, you will want to transfer data to and from the modem. For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).  
  
## See Also  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)   
 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)