---
title: "コンパイラ エラー CS0525 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0525"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0525"
ms.assetid: fcecfd4f-221f-41e6-a95c-1685be78926e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# コンパイラ エラー CS0525
インターフェイスにフィールドを含めることはできません。  
  
 [インターフェイス](/dotnet/csharp/language-reference/keywords/interface)にはメソッドとプロパティを含めることができますが、フィールドを含めることはできません。  
  
 次の例では CS0525 が生成されます。  
  
```  
// CS0525.cs namespace x { public interface clx { public int i;   // CS0525 } }  
```