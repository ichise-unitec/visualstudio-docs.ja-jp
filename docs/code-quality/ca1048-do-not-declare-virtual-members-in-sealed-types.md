---
title: "Ca 1048: sealed 型の仮想メンバーを宣言しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cb13b2b74ca86101949275e418968e577ca2b7c5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048: Sealed 型の仮想メンバーを宣言しません
|||  
|-|-|  
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|  
|CheckId|CA1048|  
|カテゴリ|Microsoft.Design|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 パブリック型は封印されており、両方であるメソッドを宣言`virtual`(`Overridable` Visual Basic で) と最終されません。 このルールでは、デリゲートの型は、このパターンに従う必要がありますの違反は報告されません。  
  
## <a name="rule-description"></a>規則の説明  
 型でメソッドを仮想と宣言するのは、継承する型が仮想メソッドの実装をオーバーライドできるようにするためです。 定義上には、シールされた型で仮想メソッドを意味のないようにする、シールされた型から継承することはできません。  
  
 Visual Basic .NET と c# コンパイラでは、この規則に違反する型は許可されません。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、非仮想メソッドを作成または、型を継承できるようにします。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告は抑制しないでください。 現在の状態で、型のままメンテナンスの問題が発生することができ、利点は提供されません。  
  
## <a name="example"></a>例  
 次の例は、この規則に違反する型を示しています。  
  
 [!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]