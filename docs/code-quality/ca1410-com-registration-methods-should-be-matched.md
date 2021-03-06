---
title: "Ca 1410: COM 登録メソッドは一致する必要があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 660524e4198a06eb6a7e3d627e28acaa721bf8c2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: COM 登録メソッドは一致しなければなりません
|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldBeMatched|  
|CheckId|CA1410|  
|カテゴリ|Microsoft.Interoperability|  
|互換性に影響する変更点|なし|  
  
## <a name="cause"></a>原因  
 マークされているメソッドを宣言する型、<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>属性でマークされているメソッドを宣言しません、<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>属性、またはその逆です。  
  
## <a name="rule-description"></a>規則の説明  
 コンポーネント オブジェクト モデル (COM) クライアントを作成する、[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]型、型は最初に登録されている必要があります。 可能な場合でマークされているメソッド、<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>属性は、ユーザー指定のコードを実行する登録プロセス中に呼び出されます。 マークされている対応するメソッド、<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>属性が、解除プロセス登録メソッドの操作中に呼び出されます。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、対応する登録または登録解除メソッドを追加します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告は抑制しないでください。  
  
## <a name="example"></a>例  
 次の例は、規則に違反する型を示しています。 コード内のコメントは、違反の修正方法を示します。  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]  
  
## <a name="related-rules"></a>関連規則  
 [CA1411: COM 登録メソッドは参照可能であることはできません](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)  
  
## <a name="see-also"></a>参照  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [COM へのアセンブリの登録](/dotnet/framework/interop/registering-assemblies-with-com)   
 [Regasm.exe (アセンブリ登録ツール)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)