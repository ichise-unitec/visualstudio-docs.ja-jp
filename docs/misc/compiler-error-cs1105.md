---
title: "コンパイラ エラー CS1105 | Microsoft Docs"
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
  - "CS1105"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1105"
ms.assetid: fcbd91ad-a76a-4b22-868d-16824fa96f85
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# コンパイラ エラー CS1105
拡張メソッドは静的でなければなりません。  
  
 拡張メソッドは、非ジェネリックの静的クラスで静的メソッドとして宣言する必要があります。  
  
## 使用例  
 次の例では、`Test` が静的でないため、CS1105 が生成されます。  
  
```  
// cs1105.cs // Compile with: /target:library public class Extensions { // Single type parameter. public void Test<T>(this System.String s) {} //CS1105 }  
```  
  
## 参照  
 [拡張メソッド](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)   
 [static](/dotnet/csharp/language-reference/keywords/static)