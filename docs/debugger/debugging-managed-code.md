---
title: "マネージ コードのデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
ms.assetid: fa3aff01-c271-4aa7-b5b1-def560471c84
caps.latest.revision: "34"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: fc083adc600b7de2538abf1ada468f3d626b7ba6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-managed-code"></a>マネージ コードのデバッグ
ここでは、マネージ アプリケーションに共通するデバッグの問題と手法について説明します。マネージ アプリケーションは、Visual Basic、C#、C++ など、共通言語ランタイムをターゲットにした言語で記述されたアプリケーションです。 ここでは、高度な手法について説明します。 詳細については、次を参照してください。[デバッガーを使用して](../debugger/debugger-basics.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [出力ウィンドウの診断メッセージ](../debugger/diagnostic-messages-in-the-output-window.md)  
 について説明します、<xref:System.Diagnostics.Debug>と<xref:System.Diagnostics.Trace>クラスを実行時のメッセージを記述できます、**出力**ウィンドウです。 Debug クラスと Trace クラスに含まれている出力メソッドを使用すると、実行の中断を伴わない情報出力、および指定した条件が満たされなかった場合に実行の中断を伴う情報出力ができます。  
  
 [マネージ コードのアサーション](../debugger/assertions-in-managed-code.md)  
 マネージ コードのアサーションについて説明し、`Assert` メソッドの引数として指定された条件をテストします。 ここでは、サンプル コード、<xref:System.Diagnostics.Debug> クラスと <xref:System.Diagnostics.Trace> クラスのメソッドの使用に関する情報、デバッグ バージョンとリリース バージョンのコードの注意事項、副作用、アサートの引数、アサートの動作のカスタマイズ、および構成ファイルについても説明します。  
  
 [Visual Basic の Stop ステートメント](../debugger/stop-statements-in-visual-basic.md)  
 ブレークポイントの設定の代わりに使用できる `Stop` ステートメントについて説明します。 サンプル コードを示し、`Stop` ステートメントと `End` ステートメントの比較、および `Stop` ステートメントと `Assert` ステートメントの比較を行います。  
  
 [チュートリアル : Windows フォームのデバッグ](../debugger/walkthrough-debugging-a-windows-form.md)  
 Windows フォームを作成し、そのフォームをデバッグする方法を順をおって説明します。 マネージ Windows アプリケーションの標準コンポーネントである Windows フォームは、最も一般的なマネージ アプリケーションの 1 つです。 このチュートリアルでは Visual C# と Visual Basic を使用しますが、C++ を使って Windows フォームを作成する場合と方法は似ています。  
  
 [OnStart メソッドのデバッグ](../debugger/how-to-debug-the-onstart-method.md)  
 マネージ Windows サービスの `OnStart` メソッドのデバッグに使用できるコード例を紹介します。 Windows サービスの `OnStart` メソッドをデバッグするには、サービスをシミュレートする数行のコードを追加する必要があります。  
  
 [混合モードのデバッグ](../debugger/debugging-mixed-mode-applications.md)  
 混合モード アプリケーションのデバッグについて説明します。 これは、ネイティブ コードとマネージ コードを組み合わせたアプリケーションです。  
  
 [エラー: システム上でカーネル デバッガーが有効になっているため、デバッグできません](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)  
 マネージ コードをデバッグしようとする場合に発生するエラー メッセージについて説明、 [!INCLUDE[win7](../debugger/includes/win7_md.md)]、 [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)]、 [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)]、 [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)]、またはデバッグ モードで開始された Windows NT システムです。  
  
 [JIT の最適化とデバッグ](../debugger/jit-optimization-and-debugging.md)  
 デバッグでの JIT 最適化の効果について説明します。  
  
 [LINQ および DLINQ のデバッグ](../debugger/debugging-linq.md)  
 LINQ クエリのデバッグ手法について説明します。  
  
 [チュートリアル: 並行アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-parallel-application.md)  
 使用する方法について説明します、**並列タスク**と**並列スタック**ツール ウィンドウを並行アプリケーションをデバッグします。  
  
## <a name="related-sections"></a>関連項目  
 [IntelliTrace](../debugger/intellitrace.md)  
 IntelliTrace でアプリの実行履歴を記録することにより、すばやく簡単にバグを検索します。 記録されたイベントと呼び出しを前後にステップ実行して重要な時点でのアプリの状態を調べます。 多くのブレークポイントを設定することも、アプリを頻繁に再起動することもなく、コードをデバッグします。 Visual Studio Ultimate が必要です。  
  
 [アプリケーションのトレースとインストルメント](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
 アプリケーションの実行を監視するトレース、およびコードの重要な位置にトレース ステートメントを挿入するインストルメントについて説明します。 ここでは、ステートメントのインストルメンテーションとトレース、トレース スイッチ、トレース リスナー、アプリケーション コードのトレース、アプリケーション コードへのトレース ステートメントの追加、<xref:System.Diagnostics.Debug> と <xref:System.Diagnostics.Trace> を使った条件付きコンパイルの説明へのリンクを提供します。  
  
 [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute)  
 追加するリンカー オプションについて説明します<xref:System.Diagnostics.DebuggableAttribute>C++ で記述されたコードにします。 この属性は、C++ によるアタッチなどのデバッグ機能を使用するときに必要です。  
  
 [Windows サービス アプリケーションのデバッグ](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)  
 Windows サービス アプリケーションのデバッグに関する注意事項を示します。セットアップ、プロセスとのアタッチ、サービスの `OnStart` メソッドと Main メソッドのコードのデバッグ、ブレークポイントの設定、サービス コントロール マネージャーを使用したサービスの開始、停止、一時中断、継続などが含まれます。  
  
 [デバッグとプロファイリング](/dotnet/framework/debug-trace-profile/index)  
 .NET Framework アプリケーションのデバッグと構成要件について説明します。  
  
 [スクリプトと Web アプリケーションのデバッグ](../debugger/debugging-web-applications-and-script.md)  
 スクリプトおよび Web アプリケーションのデバッグ時に発生する一般的な問題、およびデバッグの手法について説明します。  
  
 [Visual Studio 2015 のデバッガーの新機能します。](../debugger/what-s-new-for-the-debugger-in-visual-studio.md)  
 このリリースの [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] で追加された新しいデバッグ機能について説明します。  
  
 [ホーム ページのデバッグ](../debugger/debugger-feature-tour.md)  
 デバッグに関連するドキュメントのより広範囲なリンクを提供します。 これらのリンクでは、デバッガーの新機能、設定と準備、ブレークポイント、例外処理、エディット コンティニュ、マネージ コードのデバッグ、Visual C++ プロジェクトのデバッグ、COM および ActiveX のデバッグ、DLL のデバッグ、SQL のデバッグ、ユーザー インターフェイス リファレンスなどの情報が示されます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル : カスタム Windows フォーム コントロールのデザイン時のデバッグ](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)   
 [デバッガーのセキュリティ](../debugger/debugger-security.md)  
 [Visual Studio でデバッグ](../debugger/index.md)[デバッガーの機能のツアー](../debugger/debugger-feature-tour.md)