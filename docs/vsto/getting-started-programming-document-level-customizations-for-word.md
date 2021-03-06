---
title: "Word 用ドキュメント レベル カスタマイズのプログラミング |Microsoft ドキュメント"
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
- Word solutions in Visual Studio
- Word projects [Office development in Visual Studio], getting started
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8ad9195a0ef0274400b4c7c69d23a7f1f94d838d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="getting-started-programming-document-level-customizations-for-word"></a>Word 用のドキュメント レベルのカスタマイズのプログラミングについて
  だけを開始する Visual Studio を使用して Microsoft Office Word 用ドキュメント レベルのカスタマイズを作成する場合に、知っておく次に示します。  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
## <a name="understanding-how-document-level-customizations-for-word-work"></a>Word 作業用のドキュメント レベルのカスタマイズを理解します。  
 作成する各単語のカスタマイズは、1 つのドキュメントに基づいています。 カスタマイズを使用するには、エンドユーザーは、ドキュメントが開きます。 または Word テンプレートからドキュメントを作成します。 たとえば特定の領域にカーソルを移動またはボタンおよびメニュー項目をクリックすると、ドキュメント内のイベントは、アセンブリ内のイベント処理メソッドを呼び出すことができます。 文書が閉じている場合、カスタマイズによって提供される機能は Word では使用できません。  
  
 詳細については、次を参照してください。[ドキュメント レベルのカスタマイズのアーキテクチャ](../vsto/architecture-of-document-level-customizations.md)です。  
  
## <a name="creating-document-level-projects-for-word"></a>Word 用ドキュメント レベルのプロジェクトを作成します。  
 Word 用ドキュメント レベルのカスタマイズを作成する、Word 文書または Word テンプレート プロジェクト テンプレートを使用して、**新しいプロジェクト** ダイアログ ボックス。 これらのテンプレートには必要なアセンブリ参照とプロジェクト ファイルが含まれています。  
  
 Word 用ドキュメント レベルのプロジェクトを作成する方法の詳細については、次を参照してください。[する方法: Visual Studio で Office プロジェクトを作成する](../vsto/how-to-create-office-projects-in-visual-studio.md)です。 プロジェクト テンプレートの詳細については、次を参照してください。 [Office プロジェクト テンプレートの概要](../vsto/office-project-templates-overview.md)です。  
  
## <a name="programming-word-documents-by-using-host-items-host-controls"></a>ホスト項目とホスト コントロールを使用して Word 文書のプログラミング  
 *ホスト項目*と*ホスト コントロール*ドキュメント レベルのカスタマイズのプログラミング モデルを提供するクラスです。  
  
 ホスト項目が、コードのエントリ ポイントを提供し、ホスト コントロールと Windows フォーム コントロールのコンテナーとしても機能できます。 Word 用ドキュメント レベルのプロジェクトでは、ホスト項目で表される、`ThisDocument`クラスです。  
  
 ホスト コントロールは、コンテンツ コントロール、ブックマーク、および XML ノードなど、ネイティブな Word オブジェクトに基づきます。 ホスト コントロールは、ネイティブな Word オブジェクトと同様の機能を提供し、新しいイベント、デザイナー サポート、およびデータ バインディング機能も備えています。 プロジェクト コードでは、IntelliSense で、Word オブジェクト モデルを移動することがなく、コード内で直接特定のオブジェクトを参照するが容易で最上位のオブジェクトとして表示されます。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)  
  
-   [Automating Word by Using Extended Objects](../vsto/automating-word-by-using-extended-objects.md)  
  
-   [ホスト項目とホスト コントロールの概要](../vsto/host-items-and-host-controls-overview.md)  
  
## <a name="customizing-the-user-interface-of-word"></a>Word のユーザー インターフェイスのカスタマイズ  
 ほとんどの Microsoft Office ソリューションでは、ソリューションとの対話をユーザーに対していくつかの方法を提供する、Office アプリケーションのユーザー インターフェイス (UI) を変更します。 ドキュメント レベルのカスタマイズを使用して、Word の UI を変更するには、多くの方法はあります。 たとえば、コントロールを追加するには、リボンと、操作ウィンドウを表示することができます。 詳細については、次を参照してください。 [Office UI のカスタマイズ](../vsto/office-ui-customization.md)です。  
  
 Visual Studio で直接、プロジェクトに関連付けられているドキュメントを開くこともできます。 文書が Visual Studio で開いているときは、Word のユーザー インターフェイスを使用して、ドキュメントを変更できます。 コントロールをドラッグすることにより、デザイン サーフェイスとして、ドキュメントを使用することもできます。 詳細については、次を参照してください。 [Visual Studio 環境における Office プロジェクト](../vsto/office-projects-in-the-visual-studio-environment.md)です。  
  
## <a name="binding-controls-to-data"></a>データへのコントロールのバインディング  
 コンテンツ コントロールと<xref:Microsoft.Office.Tools.Word.Bookmark>コントロールは、の一覧からドラッグできるコントロールの**データソース**ウィンドウです。 コンテンツ コントロールや方法に自動的にこのブックマークを追加するウィンドウを使用して設定するデータ ソースにバインドします。 コードを記述せずには、データベース、サービス、およびビジネス オブジェクトからデータを表示できます。 詳細については、次を参照してください。 [Office ソリューションでのコントロールへのデータ バインディング](../vsto/binding-data-to-controls-in-office-solutions.md)です。  
  
## <a name="next-steps"></a>次の手順  
 Word 用ドキュメント レベルのカスタマイズを作成する方法についてを参照してください。[チュートリアル: を作成する最初のドキュメント レベルのカスタマイズの Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)です。 このチュートリアルでは、Visual Studio と Word のドキュメント レベルのカスタマイズのプログラミング モデルでの Office 開発ツールについて説明します。  
  
 Word プロジェクトの一般的なタスクを解説しているトピックの一覧は、次を参照してください。 [Office プログラミングで一般的なタスク](../vsto/common-tasks-in-office-programming.md)です。  
  
## <a name="see-also"></a>参照  
 [方法: Visual Studio での Office プロジェクトの作成](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [ドキュメント レベルのカスタマイズのプログラミング](../vsto/programming-document-level-customizations.md)   
 [Word ソリューション](../vsto/word-solutions.md)   
 [チュートリアル: 初めての Word 用ドキュメント レベルのカスタマイズの作成](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)   
 [チュートリアルを使用して Word](../vsto/walkthroughs-using-word.md)   
 [Word オブジェクト モデルの概要](../vsto/word-object-model-overview.md)   
 [Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)  
  
  