---
title: "Ca 2228: 未公開のリソース形式を出荷しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dcbd6627e17a4dfe179f485a2439aaf04c1a01ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: 未公開のリソース形式を出荷しません
|||  
|-|-|  
|TypeName|DoNotShipUnreleasedResourceFormats|  
|CheckId|CA2228|  
|カテゴリ|Microsoft.Usage|  
|互換性に影響する変更点|中断なし|  
  
## <a name="cause"></a>原因  
 リソース ファイルは、のバージョンを使用して構築された、[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]現在サポートされていません。  
  
## <a name="rule-description"></a>規則の説明  
 プレリリース バージョンを使用してビルドされたリソース ファイル、[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]サポートされる .NET Framework のバージョンで使用できない可能性があります。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、ビルドのサポートされているバージョンを使用して、リソース、 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]k です。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告は抑制しないでください。