---
title: "CancellationScope アクティビティ デザイナー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: c6e9206eff3eaaeb3b5a79bb8457738c21af05c7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="cancellationscope-activity-designer"></a>CancellationScope アクティビティ デザイナー
**CancellationScope**アクティビティ デザイナーを使用して作成し、構成、<xref:System.Activities.Statements.CancellationScope>アクティビティ。  
  
## <a name="the-cancellationscope-activity"></a>CancellationScope アクティビティ  
 <xref:System.Activities.Statements.CancellationScope> アクティビティを使用すると、実行のアクティビティと、そのアクティビティの取り消しロジックを指定できます。  
  
### <a name="using-the-cancellationscope-activity-designer"></a>CancellationScope アクティビティ デザイナーの使用  
 **CancellationScope**アクティビティ デザイナーは含まれて、**トランザクション**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス**のタブ、 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (または、選択**ツールバー**から、**ビュー**メニューのまたは CTRL + ALT + X です)。  
  
 **CancellationScope**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**に、[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]サーフェス任意の場所、アクティビティを通常配置など内、<xref:System.Activities.Statements.Sequence>です。 この操作により、CancellationScope という既定の <xref:System.Activities.Statements.CancellationScope> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 <xref:System.Activities.Activity.DisplayName%2A>ヘッダーの値を編集できます、 **CancellationScope**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。  
  
### <a name="the-cancellationscope-properties"></a>CancellationScope プロパティ  
 次の表に、<xref:System.Activities.Statements.CancellationScope> のプロパティと、デザイナーでのその使用方法を示します。 <xref:System.Activities.Activity.DisplayName%2A> プロパティはプロパティ グリッドで編集できますが、それ以外のプロパティは[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]画面で編集する必要があります。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.CancellationScope> アクティビティの省略可能な表示名。 既定では、CancellationScope です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|  
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|True|取り消しロジックの対象となるアクティビティを指定します。 追加する、<xref:System.Activities.Statements.CancellationScope.Body%2A>アクティビティ、アクティビティをドロップ、**ツールボックス**に、**本文**ボックスに、 **CancellationScope** "ドロップというヒント テキストを含むアクティビティ デザイナーここにアクティビティ"です。|  
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|True|取り消しの際に実行されるアクティビティを指定します。 追加する、<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>アクティビティ、アクティビティをドロップ、**ツールボックス**に、 **CancellationHandler**ボックスに、 **CancellationScope**アクティビティ デザイナーのヒントテキスト「ドロップここにアクティビティ」です。|  
  
## <a name="see-also"></a>参照  
 [トランザクション](../workflow-designer/transaction-activity-designers.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [補正](../workflow-designer/compensate-activity-designer.md)   
 [確認します。](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)