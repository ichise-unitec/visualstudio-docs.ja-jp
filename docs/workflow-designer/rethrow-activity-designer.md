---
title: "Rethrow アクティビティ デザイナー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 93315ed4028ba4ded598fd07373df43150b70aa3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="rethrow-activity-designer"></a>Rethrow アクティビティ デザイナー
**Rethrow**アクティビティ デザイナーを使用して作成し、構成、<xref:System.Activities.Statements.Rethrow>アクティビティ。  
  
## <a name="the-rethrow-activity"></a>Rethrow アクティビティ  
 <xref:System.Activities.Statements.Rethrow> アクティビティでは、以前にスローされた例外をスローします。 このアクティビティは、<xref:System.Activities.Statements.Catch> アクティビティの <xref:System.Activities.Statements.TryCatch> ハンドラーでのみ使用できます。  
  
### <a name="using-the-rethrow-activity-designer"></a>ReThrow アクティビティ デザイナーの使用  
 **Rethrow**アクティビティ デザイナーは含まれて、 **Error Handling**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス** タブの左側にある、 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (または、選択**ツールバー**から、**ビュー**メニューまたは CTRL + ALT + X です)。  
  
 **Rethrow**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**に、[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]サーフェス任意の場所、アクティビティを通常配置など内、<xref:System.Activities.Statements.Sequence>です。 これを作成、 <xref:System.Activities.Statements.Rethrow> 、既定値を持つアクティビティ**DisplayName** Throw のです。 <xref:System.Activities.Activity.DisplayName%2A>ヘッダーの値を編集できます、 **Rethrow**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。  
  
### <a name="the-rethrow-properties"></a>Rethrow のプロパティ  
 次の表に、<xref:System.Activities.Statements.Rethrow> のプロパティと、デザイナーでのその使用方法を示します。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Rethrow> アクティビティの表示名を指定します (省略可能)。 既定値は Rethrow です。|  
  
## <a name="see-also"></a>参照  
 [コレクション](../workflow-designer/collection-activity-designers.md)   
 [スローします。](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)