---
title: "方法: プログラムによって印刷プレビューで文書を表示 |Microsoft ドキュメント"
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
- Word [Office development in Visual Studio], displaying documents in print preview
- documents [Office development in Visual Studio], displaying in print preview
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c4da179b2ead999634f77d8c53f32e458326e961
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-display-documents-in-print-preview"></a>方法: プログラムによって印刷プレビューで文書を表示する
  レポートを生成するソリューションでは、印刷プレビュー モードでユーザーにレポートを表示する必要がある場合があります。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="procedures-for-document-level-customizations"></a>ドキュメント レベルのカスタマイズ用の手順  
  
#### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>PrintPreview メソッドを呼び出して印刷プレビューで文書を表示するには  
  
1.  <xref:Microsoft.Office.Tools.Word.Document.PrintPreview%2A> クラスの <xref:Microsoft.Office.Tools.Word.Document> メソッドを呼び出します。 このコード例を使用するには、プロジェクトの `ThisDocument` クラスからコードを実行します。  
  
     [!code-vb[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#13)]  
  
#### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>PrintPreview プロパティを設定して印刷プレビューで文書を表示するには  
  
1.  設定、<xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A>のプロパティ、<xref:Microsoft.Office.Interop.Word.Application>オブジェクトを**true**です。  
  
     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]  
  
## <a name="procedures-for-vsto-add-ins"></a>VSTO アドイン用の手順  
  
#### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>PrintPreview メソッドを呼び出して印刷プレビューで文書を表示するには  
  
1.  プレビューする <xref:Microsoft.Office.Interop.Word._Document.PrintPreview%2A> の <xref:Microsoft.Office.Interop.Word.Document> メソッドを呼び出します。 このコード例を使用するには、プロジェクトの `ThisAddIn` クラスからコードを実行します。  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#13)]  
  
#### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>PrintPreview プロパティを設定して印刷プレビューで文書を表示するには  
  
1.  設定、<xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A>のプロパティ、<xref:Microsoft.Office.Interop.Word.Application>オブジェクトを**true**です。  
  
     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]  
  
## <a name="see-also"></a>参照  
 [方法: プログラムによって文書を印刷します。](../vsto/how-to-programmatically-print-documents.md)   
 [方法: プログラムによって既存のドキュメントを開く](../vsto/how-to-programmatically-open-existing-documents.md)   
 [方法: プログラムによって新しい文書を作成する](../vsto/how-to-programmatically-create-new-documents.md)  
  
  