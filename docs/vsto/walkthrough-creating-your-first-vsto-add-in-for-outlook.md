---
title: "チュートリアル: 最初の Outlook 用 VSTO の追加で作成 |Microsoft ドキュメント"
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
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- add-ins [Office development in Visual Studio], creating your first project
- Outlook [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3f92c898b6eb8ba0f143e0a2069e35c70cc6e6b2
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-your-first-vsto-add-in-for-outlook"></a>チュートリアル : 初めての Outlook 用 VSTO アドインの作成
  このチュートリアルでは、Microsoft Office Outlook 用の VSTO アドインを作成する方法について説明します。 この種のソリューションに作成した機能は、どの Outlook 項目が開いているかにかかわらず、アプリケーション自体に対して使用できます。 詳細については、次を参照してください。 [Office ソリューション開発の概要 &#40;です。VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 このチュートリアルでは、次の作業について説明します。  
  
-   Outlook 用の Outlook VSTO アドイン プロジェクトを作成する。  
  
-   Outlook のオブジェクト モデルを使用して、新しいメール メッセージの件名と本文にテキストを追加するコードを記述する。  
  
-   プロジェクトをビルドし、実行してテストする。  
  
-   完成したプロジェクトをクリーンアップして、開発用コンピューターでこの VSTO アドインが自動的に実行されないようにする。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Outlook  
  
## <a name="creating-the-project"></a>プロジェクトの作成  
  
#### <a name="to-create-a-new-outlook-project-in-visual-studio"></a>Visual Studio で新しい Outlook プロジェクトを作成するには  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] を起動します。  
  
2.  **[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。  
  
3.  テンプレート ペインで、 **[Visual C#]** または **[Visual Basic]**を展開してから、 **[Office/SharePoint]**を展開します。  
  
4.  展開した **[Office/SharePoint]** ノードの下で、 **[Office Add-ins]** ノードを選択します。  
  
5.  プロジェクト テンプレートの一覧で、Outlook VSTO アドイン プロジェクトを選びます。  
  
6.  **[名前]** ボックスに、「 **FirstOutlookAddIn**」と入力します。  
  
7.  **[OK]**をクリックします。  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] により **FirstOutlookAddIn** プロジェクトが作成され、 **ThisAddIn** コード ファイルがエディターで開かれます。  
  
## <a name="writing-code-that-adds-text-to-each-new-mail-message"></a>新しい各メール メッセージにテキストを追加するコードの記述  
 次に、ThisAddIn コード ファイルにコードを追加します。 この新しいコードでは、Outlook のオブジェクト モデルを使用して、それぞれの新しいメール メッセージにテキストを追加します。 ThisAddIn コード ファイルには、次の生成されたコードが既定で含まれています。  
  
-   `ThisAddIn` クラスの部分定義。 このクラスは、コードのエントリ ポイントを提供し、Outlook のオブジェクト モデルへのアクセスを提供します。 詳細については、「 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)。`ThisAddIn` クラスの残りの部分は、変更することができない非表示のコード ファイルに定義されています。  
  
-   `ThisAddIn_Startup` および `ThisAddIn_Shutdown` イベント ハンドラー。 これらのイベント ハンドラーは、Outlook が VSTO アドインを読み込むときとアンロードするときに呼び出されます。 これらのイベント ハンドラーを使用して、VSTO アドインを読み込むときに初期化し、VSTO アドインがアンロードされるときには使用したリソースをクリーンアップします。 詳細については、「 [Events in Office Projects](../vsto/events-in-office-projects.md)」を参照してください。  
  
#### <a name="to-add-text-to-the-subject-and-body-of-each-new-mail-message"></a>新しい各メール メッセージの件名と本文にテキストを追加するには  
  
1.  ThisAddIn コード ファイルで、 `inspectors` クラスに `ThisAddIn` というフィールドを宣言します。 `inspectors` フィールドは、Outlook の現在のインスタンスに含まれるインスペクター ウィンドウのコレクションへの参照を保持します。 この参照によって、 <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> イベントのイベント ハンドラーが格納されたメモリをガベージ コレクターが解放することを防止できます。  
  
     [!code-vb[Trin_OutlookAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_OutlookAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#1)]  
  
2.  `ThisAddIn_Startup` メソッドを次のコードに置き換えます。 このコードは <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> イベントにイベント ハンドラーをアタッチします。  
  
     [!code-vb[Trin_OutlookAddInTutorial#2](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#2)]
     [!code-csharp[Trin_OutlookAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#2)]  
  
3.  ThisAddIn コード ファイルで、次のコードを `ThisAddIn` クラスに追加します。 このコードは、 <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> イベントのイベント ハンドラーを定義します。  
  
     ユーザーが新しいメール メッセージを作成すると、このイベント ハンドラーにより、メッセージの件名と本文にテキストが追加されます。  
  
     [!code-vb[Trin_OutlookAddInTutorial#3](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#3)]
     [!code-csharp[Trin_OutlookAddInTutorial#3](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#3)]  
  
 新しい各メール メッセージを変更するために、前のコード例では次のオブジェクトを使用しています。  
  
-   `Application` クラスの `ThisAddIn` フィールド。 `Application` フィールドは Outlook の現在のインスタンスを表す <xref:Microsoft.Office.Interop.Outlook.Application> オブジェクトを返します。  
  
-   `Inspector` イベントのイベント ハンドラーの <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> パラメーター。 `Inspector` パラメーターは、新しいメール メッセージのインスペクター ウィンドウを表す <xref:Microsoft.Office.Interop.Outlook.Inspector> オブジェクトです。 詳細については、「 [Outlook Solutions](../vsto/outlook-solutions.md)」を参照してください。  
  
## <a name="testing-the-project"></a>プロジェクトのテスト  
 プロジェクトをビルドして実行し、新しいメール メッセージの件名と本文にテキストが表示されることを確認します。  
  
#### <a name="to-test-the-project"></a>プロジェクトをテストするには  
  
1.  **F5** キーを押して、プロジェクトをビルドおよび実行します。  
  
     プロジェクトをビルドすると、プロジェクトのビルド出力フォルダーに含まれるアセンブリにコードがコンパイルされます。 さらに Visual Studio は、Outlook が VSTO アドインを検出して読み込めるようにする一連のレジストリ エントリを作成し、VSTO アドインを実行できるように開発用コンピューター上のセキュリティを設定します。 詳細については、「 [Office Solution Build Process Overview](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)」を参照してください。  
  
2.  Outlook で、新しいメール メッセージを作成します。  
  
3.  メッセージの件名の行と本文の両方に、次のテキストが追加されることを確認します。  
  
     **This text was added by using code.**  
  
4.  Outlook を閉じます。  
  
## <a name="cleaning-up-the-project"></a>プロジェクトのクリーンアップ  
 プロジェクトの開発が完了したら、VSTO アドイン アセンブリ、レジストリ エントリ、およびセキュリティ設定を開発用コンピューターから削除します。 そうしない場合、開発用コンピューターで Outlook を起動するたびに VSTO アドインが実行されます。  
  
#### <a name="to-clean-up-your-project"></a>プロジェクトをクリーンアップするには  
  
1.  Visual Studio で、 **[ビルド]** メニューの **[ソリューションのクリーン]**をクリックします。  
  
## <a name="next-steps"></a>次の手順  
 これで Outlook 用の基本的な VSTO アドインが作成されました。VSTO アドインの詳しい開発方法について、以下のトピックをご覧ください。  
  
-   Outlook 用 VSTO アドインで実行できる一般的なプログラミング タスク。 詳細については、「 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)。  
  
-   Outlook のオブジェクト モデルの使用。 詳細については、「 [Outlook Solutions](../vsto/outlook-solutions.md)」を参照してください。  
  
-   Outlook のユーザー インターフェイス (UI) のカスタマイズ (リボンへのカスタム タブの追加や独自のカスタム作業ウィンドウの作成など)。 詳細については、次を参照してください。 [Office UI のカスタマイズ](../vsto/office-ui-customization.md)です。  
  
-   Outlook 用 VSTO アドインのビルドとデバッグ。 詳細については、次を参照してください。 [Office ソリューションのビルド](../vsto/building-office-solutions.md)です。  
  
-   Outlook 用 VSTO アドインの配置。 詳細については、次を参照してください。 [Office ソリューションの配置](../vsto/deploying-an-office-solution.md)です。  
  
## <a name="see-also"></a>参照  
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Outlook ソリューション](../vsto/outlook-solutions.md)   
 [Office UI のカスタマイズ](../vsto/office-ui-customization.md)   
 [Office ソリューションのビルド](../vsto/building-office-solutions.md)   
 [Office ソリューションの配置](../vsto/deploying-an-office-solution.md)   
 [Office プロジェクト テンプレートの概要](../vsto/office-project-templates-overview.md)  
  
  