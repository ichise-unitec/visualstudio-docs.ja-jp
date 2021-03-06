---
title: "While アクティビティ デザイナー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: f232d8e6c4a1dab9000b8f0e0f3037d083acbbef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="while-activity-designer"></a>While アクティビティ デザイナー
<xref:System.Activities.Statements.While>に含まれているアクティビティを実行、<xref:System.Activities.Statements.While.Body%2A>中に、指定した<xref:System.Activities.Statements.While.Condition%2A>に評価される**true**です。 場合によっては、含まれているアクティビティが実行されない可能性があります。 含まれているアクティビティを少なくとも 1 回は実行する必要がある場合は、<xref:System.Activities.Statements.DoWhile> アクティビティを代わりに使用します。  
  
## <a name="while-properties-in-workflow-designer"></a>ワークフロー デザイナーでの While のプロパティ  
 次の表に、最も役に立つ <xref:System.Activities.Statements.While> アクティビティのプロパティと、デザイナーでのその使用方法を示します。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|ヘッダーの <xref:System.Activities.Statements.While> アクティビティ デザイナーの表示名を指定します。 既定値は While です。 値を編集できます、**プロパティ**ウィンドウ アクティビティ デザイナーのヘッダーで直接またはします。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|  
|<xref:System.Activities.Statements.While.Body%2A>|False|実行するアクティビティを含む中に、<xref:System.Activities.Statements.While.Condition%2A>に評価される**true**です。|  
|<xref:System.Activities.Statements.While.Condition%2A>|True|[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] に含まれるアクティビティを実行するかどうかを決定するために評価される <xref:System.Activities.Statements.While.Body%2A> の式が含まれます。|  
  
## <a name="see-also"></a>参照  
 [制御フロー](../workflow-designer/control-flow-activity-designers.md)   
 [DoWhile](../workflow-designer/dowhile-activity-designer.md)