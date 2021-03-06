---
title: "Worksheet ホスト項目 |Microsoft ドキュメント"
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
- host items [Office development in Visual Studio], Worksheet
- Excel [Office development in Visual Studio], worksheets
- Worksheet host items
- worksheets, events
- Worksheet host items, events
- Excel worksheets
- worksheets, Excel
- worksheets
- events [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: af372b261b5d8527600d672c9017d7235385c170
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="worksheet-host-item"></a>Worksheet ホスト項目
  <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目は、Excel のプライマリ相互運用機能アセンブリの <xref:Microsoft.Office.Interop.Excel.Worksheet> 型を拡張する型です。 <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目は <xref:Microsoft.Office.Interop.Excel.Worksheet> オブジェクトと同一のプロパティ、メソッド、イベントをすべて提供します。また、追加のイベントも公開し、ホスト コントロールおよび Windows フォーム コントロールのコンテナーとしても機能します。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ドキュメント レベルのプロジェクトでは、デザイン時に <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目をプロジェクトに追加できます。 VSTO アドイン プロジェクトでは、実行時に <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目を生成できます。  
  
## <a name="understanding-worksheet-host-items-in-document-level-projects"></a>ドキュメント レベルのプロジェクトでのワークシートのホスト項目について  
 Excel のドキュメント レベルのプロジェクトを作成すると、Visual Studio によって 3 つの <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目がプロジェクト内に自動的に作成されます。 これらのワークシートの既定の名前は、 `Sheet1`、 `Sheet2`、 `Sheet3`です。 既存のブックに基づいてプロジェクトを作成する場合は、そのブック内のワークシートの数に応じてホスト項目の数が決まります。  
  
 これらのワークシート クラスによって、 <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目のメンバーにアクセスし、ワークシートのコンテンツを変更するなど、カスタマイズの基本的なタスクを実行できます。 また、ワークシートにコントロールを追加するには、これらのクラスを使用できます。 さまざまな種類のコントロールを組み合わせ、コードを記述すると、コントロールをデータにバインドしたり、ユーザーから情報を収集したり、ユーザーの操作に応答したりできます。 詳細については、「 [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)」を参照してください。  
  
 ワークシート クラスには、プロジェクトでコードの記述を開始できる場所が用意されています。 このクラスには、Excel のプライマリ相互運用機能アセンブリの <xref:Microsoft.Office.Interop.Excel.Worksheet> オブジェクトと同じプロパティ、メソッド、イベントがすべて用意されているため、これらのクラスを使用して Excel のオブジェクト モデルにアクセスすることもできます。 詳細については、「 [Excel Object Model Overview](../vsto/excel-object-model-overview.md)」を参照してください。  
  
 ドキュメント レベルのプロジェクトの場合は、デザイナーで新しいワークシートをブックに追加すると、デザイン時に追加の <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目をプロジェクトに追加できます。  
  
### <a name="renaming-worksheets"></a>ワークシートの名前変更  
 ドキュメント レベルのプロジェクトでは、Visual Studio デザイナーでワークシートの名前を変更できますが、この場合はワークシートの表示名だけが変わります。 ワークシートのプログラム上の名前は既定の名前のままです。 **[プロパティ]** ウィンドウでワークシートの名前を変更すると、プログラム上の名前だけが変更されます。  
  
### <a name="limitations-of-the-worksheet-host-item-in-document-level-projects"></a>ドキュメント レベルのプロジェクトでのワークシートのホスト項目の制限  
 ドキュメント レベルのプロジェクトでは、実行時に新しい <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目を作成することはできません。 実行時に新しい Excel ワークシートを作成すると、そのワークシートは <xref:Microsoft.Office.Interop.Excel.Worksheet>型になります。 これはホスト項目ではないため、ホスト コントロールや Windows フォーム コントロールを含めることはできません。 実行時にドキュメントの作成の詳細については、次を参照してください。[する方法: プログラムによって追加新しいワークシートをブックに](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)です。  
  
## <a name="understanding-worksheet-host-items-in-vsto-add-in-projects"></a>VSTO アドイン プロジェクトでのワークシートのホスト項目について  
 アプリケーション レベルのプロジェクトでは、Excel で開いている任意のワークシートの <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目を実行時に生成できます。 <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目を使用して、関連付けられたワークシートにコントロールを追加したり、 <xref:Microsoft.Office.Interop.Excel.Worksheet> オブジェクトで使用できないイベントを処理したりできます。  
  
 生成する、<xref:Microsoft.Office.Tools.Excel.Worksheet>ホスト項目、GetVstoObject メソッドを使用します。 詳細については、「 [Extending Word Documents and Excel Workbooks in VSTO Add-ins at Run Time](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [Office 開発のサンプルとチュートリアル](../vsto/office-development-samples-and-walkthroughs.md)   
 [実行時の Word 文書と VSTO アドイン内の Excel ブックの拡張](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office ドキュメントのコントロール](../vsto/controls-on-office-documents.md)   
 [実行時に Office ドキュメントにコントロールを追加します。](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Workbook ホスト項目](../vsto/workbook-host-item.md)   
 [拡張オブジェクトによる Excel の自動化](../vsto/automating-excel-by-using-extended-objects.md)   
 [ホスト項目およびホスト コントロールのプログラム上の制限事項](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  