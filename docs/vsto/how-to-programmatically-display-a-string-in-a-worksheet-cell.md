---
title: "方法: プログラムによってワークシートのセルに文字列を表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- text [Office development in Visual Studio], adding to worksheets
- worksheets, displaying text in cells
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4a76d2588ec07c461794381a2edd502d367be274
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-display-a-string-in-a-worksheet-cell"></a>方法: プログラムによってワークシートのセルに文字列を表示する
  この例では、プログラムでのセルにテキストを表示する方法を示します。 セルにテキストを表示、いずれかの操作を使用して、<xref:Microsoft.Office.Tools.Excel.NamedRange>コントロールまたはネイティブな Excel 範囲オブジェクト。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>NamedRange コントロールを使用します。  
 この例では、<xref:Microsoft.Office.Tools.Excel.NamedRange>という名前のコントロール`message`です。 コントロールは、デザイン時にドキュメント レベルのカスタマイズを追加する必要があります。 次のコードではなく、シート クラスに配置する必要があります、`ThisWorkbook`クラスです。  
  
#### <a name="to-display-text-in-a-namedrange-control"></a>NamedRange コントロールにテキストを表示するには  
  
1.  値を設定、<xref:Microsoft.Office.Tools.Excel.NamedRange>に制御を**Hello World**です。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#68)]
     [!code-vb[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#68)]  
  
## <a name="using-a-native-excel-range"></a>ネイティブ Excel 範囲を使用  
 次のコードでは、新しい範囲をプログラムで作成し、値を代入します。  
  
#### <a name="to-display-text-in-an-excel-range"></a>Excel の範囲にテキストを表示するには  
  
1.  セルでの範囲を取得**A1**で`Sheet1`値を設定および**Hello World**です。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#69)]
     [!code-vb[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#69)]  
  
## <a name="see-also"></a>参照  
 [チュートリアル: Windows フォームを使用してデータを収集します。](../vsto/walkthrough-collecting-data-using-a-windows-form.md)   
 [Office ソリューションのトラブルシューティング](../vsto/troubleshooting-office-solutions.md)   
 [NamedRange コントロール](../vsto/namedrange-control.md)   
 [Office プロジェクト内のオブジェクトへのグローバル アクセス](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)  
  
  