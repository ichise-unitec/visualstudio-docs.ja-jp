---
title: "方法: ワークシートのコメント プログラムで追加および削除 |Microsoft ドキュメント"
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
- ranges, comments
- worksheets, comments
- comments, worksheets
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9351dd018c2db4832db20a4abbdaa050f060793e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-add-and-delete-worksheet-comments"></a>方法: ワークシートのコメントをプログラムによって追加および削除する
  Microsoft Office Excel ワークシート内のコメントは、プログラムを使用して追加、削除できます。 コメントは、1 つのセルにのみ追加でき、複数のセル範囲には追加できません。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="adding-and-deleting-a-comment-in-a-document-level-project"></a>ドキュメント レベルのプロジェクト内でのコメントの追加と削除  
 次の例では、 <xref:Microsoft.Office.Tools.Excel.NamedRange> という名前のワークシートに、 `dateComment` というシングルセル `Sheet1`コントロールがあることを想定しています。  
  
#### <a name="to-add-a-new-comment-to-a-named-range"></a>名前付き範囲に新しいコメントを追加するには  
  
1.  <xref:Microsoft.Office.Tools.Excel.NamedRange.AddComment%2A> コントロールの <xref:Microsoft.Office.Tools.Excel.NamedRange> メソッドを呼び出し、コメントのテキストを入力します。 このコードは、 `Sheet1` クラスに配置する必要があります。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#30)]  
  
#### <a name="to-delete-a-comment-from-a-named-range"></a>名前付き範囲からコメントを削除するには  
  
1.  コメントがその範囲に存在することを確認し、それを削除します。 このコードは、 `Sheet1` クラスに配置する必要があります。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#29)]  
  
## <a name="adding-and-deleting-a-comment-in-an-vsto-add-in-project"></a>VSTO アドイン プロジェクト内でのコメントの追加と削除  
 次の例では、作業中のワークシートに、 <xref:Microsoft.Office.Interop.Excel.Range> というシングルセル `dateComment` コントロールがあることを想定しています。  
  
#### <a name="to-add-a-new-comment-to-an-excel-range"></a>Excel 範囲に新しいコメントを追加するには  
  
1.  <xref:Microsoft.Office.Interop.Excel.Range.AddComment%2A> の <xref:Microsoft.Office.Interop.Excel.Range> メソッドを呼び出し、コメントのテキストを入力します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#20)]  
  
#### <a name="to-delete-a-comment-from-an-excel-range"></a>Excel 範囲からコメントを削除するには  
  
1.  コメントがその範囲に存在することを確認し、それを削除します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#19)]  
  
## <a name="see-also"></a>参照  
 [ワークシートの操作](../vsto/working-with-worksheets.md)   
 [方法: プログラムによってワークシートのコメントを表示](../vsto/how-to-programmatically-display-worksheet-comments.md)   
 [NamedRange コントロール](../vsto/namedrange-control.md)  
  
  