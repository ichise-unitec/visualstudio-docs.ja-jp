---
title: "CA2111: ポインターが表示されない |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 31ae25892b6b5a153a0a4d1e52047eb5be2368d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111: ポインターは参照可能にすることはできません
|||  
|-|-|  
|TypeName|PointersShouldNotBeVisible|  
|CheckId|CA2111|  
|カテゴリ|Microsoft.Security|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 パブリックまたはプロテクト a<xref:System.IntPtr?displayProperty=fullName>または<xref:System.UIntPtr?displayProperty=fullName>フィールドは読み取り専用ではありません。  
  
## <a name="rule-description"></a>規則の説明  
 <xref:System.IntPtr>および<xref:System.UIntPtr>はポインター型でアンマネージ メモリにアクセスするために使用します。 ポインターが private、internal、または読み取り専用ではない場合、悪意のあるコードは、可能性のあるメモリ内の任意の場所へのアクセスを許可するか、アプリケーションやシステムの障害の原因で、ポインターの値を変更できます。  
  
 ポインターのフィールドを含む型に安全にアクセスする場合を参照してください。 [ca 2112: セキュリティで保護された型はフィールドを公開する必要があります](../code-quality/ca2112-secured-types-should-not-expose-fields.md)です。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 読み取り専用で、内部、またはプライベートにすることで、ポインターを保護します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告を抑制する場合は、ポインターの値に依存しないでください。  
  
## <a name="example"></a>例  
 次のコードでは、ポインターに違反して、規則を満たしていることを示します。 プライベートでないポインターも、規則に違反することに注意してください[ca 1051: 参照できるインスタンス フィールドを宣言しない](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)です。  
  
 [!code-csharp[FxCop.Security.PointersArePrivate#1](../code-quality/codesnippet/CSharp/ca2111-pointers-should-not-be-visible_1.cs)]  
  
## <a name="related-rules"></a>関連規則  
 [CA2112: セキュリティで保護された型はフィールドを公開してはなりません](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA1051: 参照できるインスタンス フィールドを宣言しないでください](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>参照  
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>