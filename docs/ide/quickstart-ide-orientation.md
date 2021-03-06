---
title: "Visual Studio IDE ツアー | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 49518c7d38ebbec74908123b83b57bf039dda6f8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-first-look-at-the-visual-studio-ide"></a>クイックスタート: Visual Studio IDE の表示の紹介

この 5 - 10 分程度の Visual Studio 統合開発環境 (IDE) の紹介では、ウィンドウやメニューなどの UI 機能の一部を説明します。

## <a name="start-page"></a>スタート ページ

ほとんどの場合、Visual Studio を起動するとまずスタート ページが表示されます。 スタート ページは、必要なコマンドとプロジェクト ファイルを見つけやすくする "ハブ" として設計されています。 **[最近]** セクションには、プロジェクトと最近作業したフォルダーが表示されます。 **[新しいプロジェクト]** の下にあるリンクをクリックすると、[新しいプロジェクト] ダイアログ ボックスが開きます。また、**[開く]** では既存のプロジェクトやコード フォルダーを開くことができます。 右側には、最新の開発者向けニュース フィードが表示されます。

![VS のスタート ページ](media/quickstart-IDE-start-page.png)

スタートページを閉じた後でもう一度表示する場合は、**[ファイル]** メニューで再度開くことができます。

![[ファイル] メニュー](media/quickstart-IDE-file-menu-large.png)

新しいプロジェクトを作成して、IDE の確認を続けましょう。

1. **[スタート ページ]** の **[新しいプロジェクト]** の下にある検索ボックスに「`console`」と入力して、プロジェクトの種類の一覧を絞り込みます。 C# または VB の**[コンソール アプリ (.NET Framework)]** を選択します (C++ や Javascript など他の言語で開発している場合は、それらの言語のプロジェクトを作成してもかまいません。 表示される UI はすべての言語でほぼ同じです)。

1. **[新しいプロジェクト]** ダイアログ ボックスで、既定のプロジェクト名をそのまま使用し、**[OK]** を選択します。

   プロジェクトが作成され、**Program.cs** または **Program.vb** という名前のファイルが **[エディター]** ウィンドウに表示されます。 エディターにファイルの内容が表示されます。Visual Studio でのコード作成作業のほとんどは、このエディターで行います。

## <a name="solution-explorer"></a>ソリューション エクスプローラー

ソリューション エクスプローラーには、プロジェクト、ソリューション、コード フォルダー内のファイルとフォルダーの階層がグラフィカルに表示されます。 ソリューション エクスプローラー内で階層を移動し、ファイルを選択できます。

![ソリューション エクスプローラー](media/quickstart-IDE-solution-explorer.png)

## <a name="menus"></a>メニュー

IDE の上部にあるメニュー バーには、コマンドがカテゴリごとにグループ化されています。 たとえば、**[プロジェクト]** メニューには、作業中のプロジェクトに関連するコマンドが含まれています。 **[ツール]** メニューでは、**[オプション]** を選択して IDE をカスタマイズしたり、**[ツールと機能を取得...]** を選択してインストールへ機能を追加したりできます。

![メニュー バー](media/quickstart-IDE-menu-bar.png)

**[表示]** メニューの **[エラー一覧]** を選択して、[エラー一覧] ウィンドウを開いてみましょう。

## <a name="error-list"></a>エラー一覧

[エラー一覧] ウィンドウには、現在の状態のコードに関するエラー、警告、メッセージが表示されます。 ファイル、あるいはプロジェクト内のどこかにエラー (構文の入力ミスなど) がある場合、このウィンドウに表示されます。

![エラー一覧](media/quickstart-IDE-error-list.png)

## <a name="output-window"></a>[出力] ウィンドウ

[出力] ウィンドウには、ビルドおよびソース管理からの出力メッセージが表示されます。

プロジェクトをビルドして、出力のログを確認してみましょう。 **[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。 自動的に [出力] ウィンドウにフォーカスされ、ビルドが成功したことを示すメッセージが表示されます。

![[出力] ウィンドウ](media/quickstart-IDE-output.png)

## <a name="quick-launch"></a>クイック起動

[クイック起動] ボックスでは、IDE でのほぼすべての操作を素早く簡単に行うことができます。 実行する操作に関連したテキストを入力すると、そのテキストに関係するオプションの一覧が表示されます。 たとえば、ビルドで実際に行われる内容について詳細なログ情報を確認するために、ビルドの出力の詳細レベルを上げるとします。

1. **[クイック起動]** ボックスに「`verbosity`」と入力し、**[オプション]** カテゴリの **[プロジェクトおよびソリューション -> ビルド/実行]** を選択します。

   ![[クイック起動] ボックス](media/quickstart-IDE-quick-launch.png)

   **[オプション]** ダイアログ ボックスが開き、**[ビルド/実行]** オプションのページが表示されます。

1. **[MSBuild プロジェクト ビルドの出力の詳細]** で **[標準]** を選択し、**[OK]** をクリックします。

1. それでは、**ソリューション エクスプローラー**で **[ConsoleApp1]** プロジェクトを右クリックし、コンテキスト メニューで **[リビルド]** を選択して、プロジェクトをもう一度ビルドしましょう。

   今度は、[出力] ウィンドウには、どの場所のどのファイルがコピーされたかなど、ビルド プロセスに関するより詳細なログが表示されます。

## <a name="send-feedback-menu"></a>[フィードバックの送信] メニュー

Visual Studio の使用中に問題が発生した場合、または製品の改善案をお持ちの場合は、IDE 上部の [クイック起動] ボックスの隣にある **[フィードバックの送信]** メニューを使用してください。

![[フィードバックの送信] メニュー](media/quickstart-IDE-send-feedback.png)

## <a name="next-steps"></a>次の手順

ユーザー インターフェイスに慣れるため、Visual Studio IDE の機能をいくつか確認しました。 下記に従って、さらに試してみてください。

- [エラー一覧](../ide/reference/error-list-window.md)、[[出力] ウィンドウ](../ide/reference/output-window.md)、[[プロパティ] ウィンドウ](../ide/reference/properties-window.md)、[[オプション] ダイアログ ボックス](../ide/reference/options-dialog-box-visual-studio.md)など、ウィンドウの詳細について説明した VS ドキュメントの一般的なユーザー インターフェイス要素に関するセクションをご覧ください。

- [Visual Studio IDE の概要](../ide/visual-studio-ide.md)に関するページで、IDE のより詳細なツアーに参加し、デバッグも試してみてください。

## <a name="see-also"></a>関連項目

[クイックスタート: IDE のカスタマイズ](../ide/personalizing-the-visual-studio-ide.md)  
[クイックスタート: エディター内のコーディング](../ide/quickstart-editor.md)  
[クイック スタート: プロジェクトとソリューション](../ide/quickstart-projects-solutions.md)  