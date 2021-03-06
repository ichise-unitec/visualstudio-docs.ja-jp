---
title: "デバッガーでは、Visual Studio でのコード内を移動 |Microsoft ドキュメント"
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.execution
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 759072ba-4aaa-447e-8e51-0dd1456fe896
caps.latest.revision: "42"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2c45f6cfa37ee8593da08d59071d8244b08feac7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="navigate-code-with-the-visual-studio-debugger"></a>Visual Studio デバッガーでコード内を移動します。
デバッガーでコードを移動するには、コマンドおよびショートカットについて理解し、使用することでより高速で簡単に見つけ、アプリケーションの問題を解決します。 デバッガーでコードを移動するときに、アプリの状態を検査またはの詳細については、その実行フローできます。  
  
## <a name="start-debugging"></a>[デバッグ開始]  
 使用してデバッグ セッションを開始する多くの場合、 **f5 キーを押して**(**デバッグ** > **デバッグの開始**)。 このコマンドは、アタッチされたデバッガーで、アプリを開始します。  
  
 緑色の矢印もデバッガーを起動します (同じ**f5 キーを押して**)。  
  
 ![DBG &#95;です。基本 &#95;です。デバッグの開始日と #95;](../debugger/media/dbg_basics_start_debugging.png "DBG_Basics_Start_Debugging")  
  
 アタッチされたデバッガーでアプリを起動できる他のいくつかの方法を含める**F11** ([コードにステップ イン](#BKMK_Step_into__over__or_out_of_the_code))、 **F10** ([コードをステップ](#BKMK_Step_over_Step_out))、または使用して**カーソルまで実行**です。  これらのオプションの機能には、その他のセクションでは、情報は、このトピックを参照してください。  
  
 デバッグすると、黄色の行に次に実行されるコードが表示されます。  
  
 ![DBG &#95;です。基本 &#95;です。中断 &#95;です。モード](../debugger/media/dbg_basics_break_mode.png "DBG_Basics_Break_Mode")  
  
 デバッグ中と同様に、コマンド間で切り替えることができます**f5 キーを押して**、 **F11**で検索するコードをすばやく表示するようなブレークポイント) には、このトピックで説明するその他の機能を使用するとします。  
  
 [ローカル] ウィンドウで変数の値の表示や [ウォッチ] ウィンドウで式の評価など、ほとんどのデバッガー機能は、デバッガーが一時停止中にのみ、使用可能な (とも呼ばれる*中断モード*)。 デバッガーを一時停止すると、ときに、関数、変数、中に、アプリの状態が中断され、オブジェクトはメモリに残ります。 中断モードでは、要素の位置と状態を確認して違反やバグを調査できます。 プロジェクトの種類によって行うことも中断モードでアプリを調整します。 これらの機能を示すビデオを見るには、次を参照してください。[デバッガーの使用を開始する](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6)です。
  
##  <a name="BKMK_Step_into__over__or_out_of_the_code"></a>コードにステップ イン、1 行ずつ  
 デバッグ中にコード (ステートメントごと) の行ごとに停止する、 **F11**キーボード ショートカット (または**デバッグ** > **ステップ イン**メニュー)。  
  
> [!TIP]
>  その値を表示または使用する変数をポイントするとコードの各行を実行すると、[ローカル](../debugger/autos-and-locals-windows.md)と[ウォッチ](../debugger/autos-and-locals-windows.md)その値の変更を監視する windows です。  
  
 ここでは、動作に関するいくつかの詳細**ステップ イン**:  
  
-   入れ子になった関数呼び出しの場合は、 **[ステップ イン]** をクリックすると、一番内側にある入れ子になった関数にステップ インします。 **のような呼び出しに** [ステップ イン] `Func1(Func2())`を使用すると、デバッガーは関数 `Func2`にステップ インします。  
  
-   デバッガーは実際、物理的な行ではなくコード ステートメントをステップ実行します。 たとえば、 `if` 句は 1 行で記述できます。  
  
    ```CSharp  
    int x = 42;  
    string s = "Not answered";  
    if( int x == 42) s = "Answered!";  
    ```  
  
    ```VB  
    Dim x As Integer = 42  
    Dim s As String = "Not answered"  
    If x = 42 Then s = "Answered!"  
    ```  
  
     この行にステップ インすると、デバッガーは条件を 1 つのステップとして、結果を別のステップとして扱います (この例では条件は true)。  
  
 関数にステップ イン中に、呼び出し履歴を視覚的にトレースするを参照してください。[デバッグ中に、呼び出し履歴に対するメソッドのマップ](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)です。  
  
##  <a name="BKMK_Step_over_Step_out"></a>関数をスキップしています。 コードをステップ実行  
 デバッガーでコードを実行するときに多くの場合を実感、特定の関数の動作を確認する必要はありません (必要ないか、または知っている十分にテストされたライブラリ コードと同様に動作、)。 これらのコマンドを使用してコードをスキップする (関数は、まだ実行もちろん、ものの、デバッガーがスキップします)。  
  
|キーボード コマンド|メニュー コマンド|説明|  
|----------------------|------------------|-----------------|  
|**F10 キー**|**[ステップ オーバー]**|現在の行に関数呼び出しが含まれている場合**ステップ オーバー**コードを実行し、呼び出された関数が返された後に、コードの最初の行で実行を中断します。|  
|**Shift + F11**|**[ステップ アウト]**|**ステップ アウト**コードの実行が続けられ、現在の関数には、(現在の関数を通じたデバッガー スキップ) が返されるときに実行を中断します。|  
  
> [!TIP]
>  アプリ内のエントリ ポイントを検索する必要がある場合が始まる**F10**または**F11**です。 これらのコマンドは、アプリの状態を検査したり、実行フローの詳細を検索しようとするときに多くの場合、便利です。  
  
##  <a name="BKMK_Break_into_code_by_using_breakpoints_or_Break_All"></a>特定の位置または関数まで実行するには  
 多くの場合、コードのデバッグの方法が推奨これらのメソッドは便利です、検査するどのようなコードだけがわかっている場合またはデバッグを開始するを把握するには、少なくともです。  
  
-   **コードにブレークポイントを設定する**  
  
     コードに単純なブレークポイントを設定するには、Visual Studio エディターでソース ファイルを開きます。 実行を中断し、コンテキスト メニューを表示して、コード ウィンドウ内を右クリックする場所でコードの行にカーソルを設定**ブレークポイント > ブレークポイントの挿入**(またはキーを押して**F9**)。 デバッガーは、行が実行される前に、右側の実行を中断します。  
  
     ![ブレークポイントを設定する](../debugger/media/dbg_basics_setbreakpoint.png "DBG_Basics_SetBreakpoint")  
  
     Visual Studio でのブレークポイントには、条件付きブレークポイントやトレースポイントなど、さまざまな追加の機能が用意されています。 参照してください[ブレークポイントを使用する](../debugger/using-breakpoints.md)です。  
  
-   **カーソル位置まで実行する**  
  
     カーソル位置まで実行するには、ソース ウィンドウで実行可能なコード行にカーソルを置きます。 エディターのコンテキスト メニュー (エディターで右クリック) の順にクリックして**カーソルまで実行**です。 これは、一時的なブレークポイントの設定に似ています。

-   **実行する をクリックします** 

    実行するには、デバッガーで一時停止中に、コード内のポイントを選択して、**ここまで実行**緑色の矢印アイコン (アイコンが表示、コード行にポインターを置いたときに)。 これにより、一時的なブレークポイントを設定する必要があります。

    ![デバッガーの実行 をクリックを](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

    > [!NOTE]
    > **クリックして実行**の[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]します。
  
-   **コードを手動で中断する**  
  
     実行中のアプリで次に実行されるコード行で実行を中断するには、 **[デバッグ]**、 **[すべて中断]** の順にクリックします (キーボード: **Ctrl+Alt+Break**)。 
  
     対応付けられたソースまたはシンボル (.pdb) ファイルがないため、コードの実行が中断された場合は、デバッガーによって **[ソース ファイルが見つかりません]** または **[シンボルが見つかりません]** ページが表示され、該当するファイルを見つけるために役立ちます。 参照してください[シンボル (.pdb) を指定して、ソース ファイル](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)です。 それらのサポート ファイルにアクセスできない場合は、[逆アセンブル] ウィンドウでアセンブリ命令をデバッグできます。  
  
-   **呼び出し履歴の関数まで実行する**  
  
     **呼び出し履歴**ウィンドウ (デバッグ中に使用可能)、関数の選択を右クリックして**カーソルまで実行**です。 呼び出し履歴を視覚的にトレースするを参照してください。[デバッグ中に、呼び出し履歴に対するメソッドのマップ](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)です。  
  
-   **名前で指定した関数まで実行する**  
  
     ようにデバッガーを指定された関数に達するまで、アプリケーションを実行することができます。 関数は名前で指定することも、呼び出し履歴から選択することもできます。  
  
     名前で関数を指定するには、 **[デバッグ]**、 **[ブレークポイントの作成]**、 **[関数でブレーク]**の順にクリックし、関数の名前などの識別情報を入力します。  
  
     ![[ブレークポイント] ダイアログ ボックス](../debugger/media/dbg_execution_newbreakpoint.png "DBG_Execution_NewBreakpoint")  
  
     関数がオーバーロードされるか、複数の名前空間にある場合は、 **[ブレークポイントの選択]** ダイアログ ボックスで目的の関数を選択できます。  
  
     ![[ブレークポイント] ダイアログ ボックスを選択して](../debugger/media/dbg_execution_overloadedbreakpoints.png "DBG_Execution_OverloadedBreakpoints")  
  
##  <a name="BKMK_Set_the_next_statement_to_execute"></a>実行フローを変更するポインターを移動します。  
 デバッガーが一時停止中には、コードを実行するは、次のステートメントを設定する命令ポインターを移動することができます。 ソース ウィンドウまたは [逆アセンブル] ウィンドウのマージンに表示される黄色の矢印は、次に実行されるステートメントの位置を示します。 この矢印を移動すると、コードの一部をスキップしたり、前に実行した行に戻ったりできます。 既知のバグを含むコードのセクションをスキップするなどの場合に利用できます。  
  
 ![ポインターを移動](../debugger/media/dbg_basics_example3.gif "DBG_Basics_Example3")
  
 次に実行されるステートメントを設定するには、次のいずれかの手順を使用します。  
  
-   ソース ウィンドウで、同じソース ファイル内の次に実行されるステートメントを設定する位置に黄色の矢印をドラッグします。  
  
-   ソース ウィンドウで、次に実行を右クリックして選択する行にカーソルを設定します**次のステートメントの設定**です。  
  
-   [逆アセンブル] ウィンドウで、次に実行を右クリックするアセンブリ命令にカーソルを設定を選択し、**次のステートメントの設定**です。  
  
> [!CAUTION]
>  次に実行するステートメントを設定すると、プログラム カウンターは新しい位置に直接ジャンプします。 このコマンドは慎重に使用する必要があります。  
>   
>  -   前の実行ポイントから新しい実行ポイントまでの間の命令は実行されません。  
> -   実行ポイントを後方に移動すると、その間の命令が実行されます。  
> -   次に実行するステートメントを別の関数やスコープに移動すると、一般に呼び出し履歴が破損し、実行時エラーや例外が発生する原因になります。 次に実行するステートメントを別のスコープに移動しようとすると、デバッガーの警告ダイアログ ボックスが表示され、操作をキャンセルできます。 Visual Basic では、次に実行するステートメントを別のスコープや関数に移動できません。  
> -   ネイティブ C++ でランタイム チェックを有効にしている場合、次に実行されるステートメントを設定すると、実行がメソッドの最後に到達したときに例外がスローされる可能性があります。  
> -   エディット コンティニュが有効になっている場合、エディット コンティニュが即座にマップし直すことができない編集が行われると、 **[次のステートメントの設定]** でエラーが発生します。 これは、たとえば、catch ブロック内でコードを編集している場合に発生します。 この場合、サポートする操作ではないことを示すエラー メッセージが表示されます。  
  
> [!NOTE]
>  マネージ コードでは、次に実行するステートメントは、以下の場合に移動できません。  
>   
>  -   次のステートメントが現在のステートメントとは別のメソッドに含まれている場合。  
> -   デバッグが、Just-In-Time デバッグを使用して開始された場合。  
> -   呼び出し履歴のアンワインドが行われている場合。  
> -   System.StackOverflowException 例外または System.Threading.ThreadAbortException 例外がスローされた場合。  
  
 アプリケーションの実行中は、次のステートメントを設定できません。 次に実行するステートメントの設定は、デバッガーの中断モード時に行う必要があります。  
  
## <a name="BKMK_Restrict_stepping_to_Just_My_Code"></a>非ユーザー コードにステップ イン  
 既定では、デバッガーしようとするコードのみを表示、アプリケーション、デバッグ中に設定と呼ばれるデバッガーによって決定される*マイ コードのみ*です。 (を参照してください[マイ コードのみ](../debugger/just-my-code.md)を別のプロジェクトの種類と言語のしくみし、動作をカスタマイズする方法を参照してください)。ただし、デバッグしている間にも可能性があるフレームワーク コード、サードパーティ製ライブラリ コード、または呼び出しを見て、オペレーティング システム (システム呼び出し) にします。  
  
 マイ コードのみをオフに移動して**ツール** > **オプション** > **デバッグ**をオフにし、 **マイ コードのみ**チェック ボックスをオンします。  
  
 マイ コードのみを無効にすると、デバッガーが非ユーザー コードにステップ インでき、非ユーザー コードがデバッガー ウィンドウに表示されます。  
  
> [!NOTE]
>  "マイ コードのみ" デバッグは、デバイス プロジェクトではサポートされません。  
  
 **システム コールにステップ インする**  
  
 システム コードのデバッグ シンボルを読み込んだマイ コードのみが有効になっていない場合は、他の呼び出しと同様にシステム コールにステップできます。  
  
 Microsoft シンボル ファイルにアクセスするを参照してください。[シンボル サーバーを使用してローカル コンピューター上にないシンボル ファイルを検索](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Use_symbol_servers_to_find_symbol_files_not_on_your_local_machine)で、[指定シンボル (.pdb) とソース ファイル](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)トピックです。  
  
 デバッグ中に特定のシステム コンポーネントのシンボルを読み込むには:  
  
1.  [モジュール] ウィンドウを開きます (キーボード: **Ctrl + Alt + U**)。  
  
2.  シンボルを読み込むモジュールを選択します。  
  
     **[シンボルの状態]** 列により、シンボルが読み込まれたモジュールを確認できます。  
  
3.  コンテキスト メニューの **[シンボルの読み込み]** をクリックします。  
  
##  <a name="BKMK_Step_into_properties_and_operators_in_managed_code"></a> マネージ コード内のプロパティと演算子にステップ インする  
 デバッガーは既定ではマネージ コード内のプロパティと演算子をステップ オーバーします。 ほとんどの場合、これにより正しくデバッグを実行できます。 プロパティと演算子にステップ インを有効にするには選択**デバッグ** > **オプション**です。 **デバッグ** > **全般** ページで、クリア、**プロパティおよび演算子 (マネージのみ) をステップ オーバー**  チェック ボックス