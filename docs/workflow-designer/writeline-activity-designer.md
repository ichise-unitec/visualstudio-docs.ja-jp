---
title: "WriteLine アクティビティ デザイナー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 3f531539737389938a7ff0a757235d8c5c2af263
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="writeline-activity-designer"></a>WriteLine アクティビティ デザイナー
**WriteLine**アクティビティ デザイナーを使用して作成し、構成、<xref:System.Activities.Statements.WriteLine>アクティビティ。  
  
## <a name="the-writeline-activity"></a>WriteLine アクティビティ  
 <xref:System.Activities.Statements.WriteLine> アクティビティは、指定された <xref:System.IO.TextWriter> オブジェクトにテキストを書き込みます。 <xref:System.IO.TextWriter> を指定しない場合、<xref:System.Activities.Statements.WriteLine> はテキストをコンソールに書き込みます。  
  
### <a name="using-the-writeline-activity-designer"></a>WriteLine アクティビティ デザイナーの使用  
 **WriteLine**アクティビティ デザイナーは含まれて、**プリミティブ**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス**のタブ、 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (または、選択**ツールバー**から、**ビュー**メニューのまたは CTRL + ALT + X です)。  
  
 **WriteLine**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**に、[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]サーフェス任意の場所、アクティビティを通常配置など内、<xref:System.Activities.Statements.Sequence>です。 この操作により、WriteLine という既定の <xref:System.Activities.Statements.WriteLine> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 <xref:System.Activities.Activity.DisplayName%2A>のヘッダーで編集できる、 **WriteLine**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。  
  
### <a name="the-writeline-properties"></a>WriteLine プロパティ  
 次の表に、<xref:System.Activities.Statements.WriteLine> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドで編集できます。また、一部のプロパティは、[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]のデザイナー画面で編集できます。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.WriteLine> アクティビティの表示名。 既定値は WriteLine です。 <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|  
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|書き込むテキスト。 プロパティを設定するには、Visual Basic の式を入力、**テキスト**ボックスに、 **WriteLine**アクティビティ デザイナーまたはプロパティ グリッドでします。|  
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter> による <xref:System.Activities.Statements.WriteLine> の書き込み先の <xref:System.Activities.Statements.WriteLine.Text%2A>。 既定はコンソールです。|  
  
## <a name="see-also"></a>参照  
 [プリミティブ](../workflow-designer/primitives-activity-designers.md)   
 [割り当てる](../workflow-designer/assign-activity-designer.md)   
 [遅延](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)