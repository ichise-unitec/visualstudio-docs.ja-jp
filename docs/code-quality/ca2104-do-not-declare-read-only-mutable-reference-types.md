---
title: "Ca 2104: 読み取りのみ変更可能な参照型を宣言しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bbd12d09c95f1ec93c7232901270cfbece311693
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: 読み取り専用の変更可能な参照型を宣言しません
|||  
|-|-|  
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|  
|CheckId|CA2104|  
|カテゴリ|Microsoft.Security|  
|互換性に影響する変更点|なし|  
  
## <a name="cause"></a>原因  
 外部から参照できる型に、変更可能な参照型である、外部から参照可能な読み取り専用のフィールドがあります。  
  
## <a name="rule-description"></a>規則の説明  
 変更可能な型とは、インスタンス データを変更できる型です。 <xref:System.Text.StringBuilder?displayProperty=fullName>クラスが変更可能な参照型の例を示します。 クラスのインスタンスの値を変更できるメンバーが含まれています。 変更不可の参照型の例は、<xref:System.String?displayProperty=fullName>クラスです。 インスタンス化された後にその値を変更できません。  
  
 読み取り専用の修飾子 ([readonly](/dotnet/csharp/language-reference/keywords/readonly) 、C# の場合は、[読み取り専用](/dotnet/visual-basic/language-reference/modifiers/readonly)で[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]、および[const](/cpp/cpp/const-cpp) C++ で)、参照型のフィールド (C++ でのポインター) により、フィールドを防止参照型の別のインスタンスに置換されます。 ただし、修飾子は、参照型を使った変更から、フィールドのインスタンス データを妨げません。  
  
 読み取り専用配列フィールドは、この規則から除外されますが、違反が発生する代わりに、 [ca 2105: 配列フィールドを読み込まないでのみ](../code-quality/ca2105-array-fields-should-not-be-read-only.md)ルール。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、読み取り専用の修飾子を削除するか、重大な変更が許容される場合は、変更不可の型とフィールドを置き換えます。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告を抑制するフィールドの種類が変更可能でない場合にも安全です。  
  
## <a name="example"></a>例  
 次の例は、この規則違反の原因となるフィールドの宣言を示しています。  
  
 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]