---
title: "Ca 1412: ComSource インターフェイスを IDispatch として |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b2523397f59affa2d7e1e60e69e7ba2047438135
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412: ComSource インターフェイスを IDispatch として設定します
|||  
|-|-|  
|TypeName|MarkComSourceInterfacesAsIDispatch|  
|CheckId|CA1412|  
|カテゴリ|Microsoft.Interoperability|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 型が付いて、<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>属性および指定したインターフェイスを少なくとも 1 つでマークされていない、<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>属性に設定、`InterfaceIsDispatch`値。  
  
## <a name="rule-description"></a>規則の説明  
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>クラスは、コンポーネント オブジェクト モデル (COM) クライアントに公開するイベント インターフェイスの識別に使用します。 としてこれらのインターフェイスを公開する必要があります`InterfaceIsIDispatch`イベント通知を受信する Visual Basic 6 COM クライアントを有効にします。 既定では、インターフェイスが付いていない場合、<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>属性、デュアル インターフェイスとして公開されます。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、追加または変更、<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>属性の値で指定されているすべてのインターフェイスに対して InterfaceIsIDispatch に設定されているように、<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>属性。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告は抑制しないでください。  
  
## <a name="example"></a>例  
 次の例では、規則に違反する場所、インターフェイスのいずれかのクラスを示します。  
  
 [!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/CSharp/ca1412-mark-comsource-interfaces-as-idispatch_1.cs)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/VisualBasic/ca1412-mark-comsource-interfaces-as-idispatch_1.vb)]  
  
## <a name="related-rules"></a>関連規則  
 [CA1408: AutoDual ClassInterfaceType を使用しないでください](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)  
  
## <a name="see-also"></a>参照  
 [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)