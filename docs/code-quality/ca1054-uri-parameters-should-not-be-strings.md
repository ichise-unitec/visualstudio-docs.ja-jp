---
title: "Ca 1054: URI パラメーターを文字列にする必要があることはできません |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 61f3f42e8a873f4be2873798f9137fbc22feb8fb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054: URI パラメーターを文字列にすることはできません
|||  
|-|-|  
|TypeName|UriParametersShouldNotBeStrings|  
|CheckId|CA1054|  
|カテゴリ|Microsoft.Design|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 型は名前が"uri"、"Uri"、"urn"、"Urn"、"url"または"Url"を含む文字列パラメーターを持つメソッドを宣言し、型に対応するオーバー ロードを宣言しません、<xref:System.Uri?displayProperty=fullName>パラメーター。  
  
## <a name="rule-description"></a>規則の説明  
 このルールは、パラメーター名は camel 形式の組み合わせに基づいて、トークンに分割し、各トークンが"uri"、"Uri"、"urn"、"Urn"、"url"または"Url"に等しいかどうかを確認します。 一致がある場合は、パラメーターが表す uniform resource identifier (URI)、ルールが前提とします。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 対応するオーバー ロードで、メソッドは、URI の文字列形式を使用する場合のインスタンスを使用する場合があります、<xref:System.Uri>と、セキュリティで保護された方法でこれらのサービスを提供するクラス。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、パラメーターを変更、<xref:System.Uri>入力です。 これは、互換性に影響する変更です。 受け取るメソッドのオーバー ロードを代わりに、提供、<xref:System.Uri>パラメーターです。 これは、互換性に影響しない変更です。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 パラメーターが URI を表していない場合はこの規則による警告を抑制しても安全です。  
  
## <a name="example"></a>例  
 次の例は、型`ErrorProne`、この規則と、型に違反する`SaferWay`規則に適合します。  
  
 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]  
  
## <a name="related-rules"></a>関連規則  
 [CA1056: URI プロパティを文字列にすることはできません](../code-quality/ca1056-uri-properties-should-not-be-strings.md)  
  
 [CA1055: URI 戻り値を文字列にすることはできません](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)  
  
 [CA2234: 文字列の代わりに System.Uri オブジェクトを渡します](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)  
  
 [CA1057: 文字列 URI オーバーロードが、System.Uri オーバーロードを呼び出します](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)