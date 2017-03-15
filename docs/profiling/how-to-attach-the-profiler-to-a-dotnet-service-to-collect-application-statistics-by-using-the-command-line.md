---
title: "方法: コマンド ラインを使用してプロファイラーを .NET サービスにアタッチし、アプリケーションの統計情報を収集する | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a0046c47-26c8-4bec-96a0-81da05e5104a
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 方法: コマンド ラインを使用してプロファイラーを .NET サービスにアタッチし、アプリケーションの統計情報を収集する
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ここでは、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイリング ツールのコマンド ライン ツールを使用して、プロファイラーを .NET Framework サービスにアタッチし、サンプリング メソッドによってパフォーマンスに関する統計情報を収集する方法について説明します。  
  
> [!NOTE]
>  Windows 8 および Windows Server 2012 の強化されたセキュリティ機能によって、Visual Studio プロファイラーがこれらのプラットフォームでデータを収集する方法に大幅な変更が必要になりました。  Windows ストア アプリにも新しい収集手法が必要です。  「[Windows 8 および Windows Server 2012 アプリケーションのプロファイリング](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)」を参照してください。  
>   
>  プロファイリング ツールのコマンド ライン ツールは、[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] インストール ディレクトリの \\Team Tools\\Performance Tools サブディレクトリにあります。  64 ビット コンピューター上では、64 ビット バージョンのツールと 32 ビット バージョンのツールの両方を使用できます。  プロファイラーのコマンド ライン ツールを使用するには、コマンド プロンプト ウィンドウの PATH 環境変数にツールのパスを追加するか、コマンド自体にそれを追加します。  詳細については、「[コマンド ライン ツールへのパスの指定](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)」を参照してください。  
>   
>  プロファイリングの実行に階層の相互作用データを追加するには、コマンド ライン プロファイリング ツールによる特定の手順が必要です。  「[階層相互作用データの収集](../profiling/adding-tier-interaction-data-from-the-command-line.md)」を参照してください。  
  
 .NET Framework サービスからパフォーマンス データを収集するには、[VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) ツールを使用して該当する環境変数を初期化する必要があります。  次に、サービスをホストするコンピューターを再起動し、そのコンピューターをプロファイリング用に構成します。  続いて、プロファイラーをサービス プロセスにアタッチします。  プロファイラーをサービスにアタッチするときはデータ収集を一時停止し、完了後に再開できます。  
  
 プロファイル セッションを終了するには、プロファイラーをサービスからデタッチし、プロファイラーを明示的に終了する必要があります。  ほとんどの場合、セッションの最後にプロファイル環境変数を消去することをお勧めします。  
  
## プロファイラーのアタッチ  
  
#### プロファイラーを .NET Framework サービスにアタッチするには  
  
1.  サービスをインストールします。  
  
2.  コマンド プロンプト ウィンドウを開きます。  
  
3.  プロファイル環境変数を初期化します。  Type:  
  
     **VSPerfClrEnv \/globalsampleon** \[**\/samplelineoff**\]  
  
    -   **\/globalsampleon** はサンプリングを有効にします。  
  
    -   **\/samplelineoff** は、特定のソース コード行への収集データの割り当てを無効にします。  このオプションを指定すると、データは関数に対してのみ割り当てられます。  
  
4.  コンピューターを再起動します。  
  
5.  コマンド プロンプト ウィンドウを開きます。  
  
6.  プロファイラーを起動します。  Type:  
  
     **VSPerfCmd**  [\/start](../profiling/start.md) **:sample**  [\/output](../profiling/output.md) **:** `OutputFile` \[`Options`\]  
  
    -   **\/start:sample** オプションによってプロファイラーが初期化されます。  
  
    -   **\/start** を使用する場合は **\/output:**`OutputFile` オプションを指定する必要があります。  `OutputFile` には、プロファイル データ \(.vsp\) ファイルの名前と場所を指定します。  
  
     **\/start:sample** オプションを使用する場合は、次のうちいずれかのオプションを指定できます。  
  
    > [!NOTE]
    >  **\/user** オプションと **\/crosssession** オプションは、通常、サービスで必要です。  
  
    |オプション|説明|  
    |-----------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|プロファイリングされたプロセスを所有するアカウントのドメインおよびユーザー名を指定します。  このオプションは、ログオンしているユーザーとは別のユーザーがプロセスを実行している場合にのみ指定する必要があります。  プロセスの所有者は、Windows タスク マネージャーの \[プロセス\] タブの \[ユーザー名\] 列に表示されます。|  
    |[\/crosssession](../profiling/crosssession.md)|他のセッションにおけるプロセスのプロファイリングを有効にします。  このオプションは、サービスが別のセッションで実行されている場合に必要です。  セッション ID は、Windows タスク マネージャーの \[プロセス\] タブの \[セッション ID\] 列に表示されます。  **\/crosssession** の省略形として、**\/CS** を指定することができます。|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|プロファイリング実行中に収集する Windows パフォーマンス カウンターを指定します。|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter** と共にのみ使用します。  Windows パフォーマンス カウンター コレクション イベントの間隔をミリ秒単位で指定します。  既定値は 500 ミリ秒です。|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|プロファイリング実行中に収集する ETW \(Event Tracing for Windows\) イベントを指定します。  ETW イベントは独立した \(.etl\) ファイルに収集されます。|  
  
7.  起動の必要なサービスがあれば起動します。  
  
8.  プロファイラーをサービスにアタッチします。  Type:  
  
     **VSPerfCmd**  [\/attach](../profiling/attach.md) **:** {`PID`&#124;`ProcName`} \[`Sample Event`\] \[[\/targetclr](../profiling/targetclr.md)**:**`Version`\]  
  
    -   サービスのプロセス ID \(`PID`\) またはプロセス名 \(ProcName\) を指定します。  Windows タスク マネージャーで、実行中のすべてのプロセスのプロセス ID と名前を参照できます。  
  
     既定では、パフォーマンス データはプロセッサのクロック サイクル数 10,000,000 \(停止なし\) ごとにサンプリングされます。  このため、1 GHz のプロセッサにおける 1 秒あたりのサンプリング数は約 100 サンプルです。  次のオプションのいずれかを指定すると、クロック サイクルの間隔の変更や、別のサンプリング イベントの指定ができます。  
  
    |サンプリング イベント|説明|  
    |-----------------|--------|  
    |[\/timer](../profiling/timer.md) **:** `Interval`|サンプリングの間隔を、`Interval` で指定された停止なしのクロック サイクル数に変更します。|  
    |[\/pf](../profiling/pf.md)\[**:**`Interval`\]|サンプリング イベントをページ フォールトに変更します。  `Interval` を指定した場合は、サンプル間のページ フォールト数が設定されます。  既定値は 10 です。|  
    |[\/sys](../profiling/sys-vsperfcmd.md)\[`:``Interval`\]|サンプリング イベントを、プロセスからオペレーティング システムのカーネルへのシステム コール \(syscall\) に変更します。  `Interval` を指定した場合は、サンプル間の呼び出し回数が設定されます。  既定値は 10 です。|  
    |[\/counter](../profiling/counter.md) **:** `Config`|サンプリング イベントと間隔を、プロセッサのパフォーマンス カウンターと、`Config` で指定した間隔に、それぞれ変更します。|  
  
    -   **targetclr:** `Version` には、アプリケーションに複数のバージョンのランタイムが読み込まれている場合に、プロファイリングを行う共通言語ランタイム \(CLR: Common Language Runtime\) のバージョンを指定します。  省略可能。  
  
## データ収集の制御  
 サービスの実行中に、**VSPerfCmd.exe** のオプションを使用して、プロファイラー データ ファイルへのデータ書き込みを開始または停止できます。  データ収集を制御することにより、アプリケーションの起動や終了など、プログラム実行の特定の部分についてのデータ収集を行うことができます。  
  
#### データ収集を開始および停止するには  
  
-   次に示す **VSPerfCmd** のオプションの組み合わせにより、データ収集を開始および停止します。  個別のコマンド ラインで各オプションを指定します。  データ収集のオンとオフは複数回切り替えることができます。  
  
    |オプション|説明|  
    |-----------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|すべてのプロセスのデータ収集を開始 \(**\/globalon**\) または停止 \(**\/globaloff**\) します。|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID`  [\/processoff](../profiling/processon-and-processoff.md) **:** `PID`|プロセス ID \(`PID`\) で指定されたプロセスのデータ収集を開始 \(**\/processon**\) または停止 \(**\/processoff**\) します。|  
    |**\/attach:**{`PID`&#124;`ProcName`} [\/detach](../profiling/detach.md)\[:{`PID`&#124;`ProcName`}\]|**\/attach** は、プロセス ID またはプロセス名で指定したプロセスのデータ収集を開始します。  **\/detach** は、指定されたプロセスのデータ収集を停止します。特定のプロセスが指定されていない場合は、すべてのプロセスのデータ収集を停止します。|  
  
## プロファイル セッションの終了  
 プロファイル セッションを終了するには、プロファイラーをプロファイリング対象のすべてのプロセスからデタッチし、プロファイラーを明示的に終了する必要があります。  サンプリング メソッドでプロファイルを実行したアプリケーションからプロファイラーをデタッチするには、アプリケーションを終了するか、**VSPerfCmd \/detach** オプションを呼び出します。  次に、**VSPerfCmd \/shutdown** オプションを呼び出して、プロファイラーをオフにし、プロファイル データ ファイルを閉じます。  
  
 **VSPerfClrEnv \/globaloff** コマンドによってプロファイル環境変数は消去されますが、コンピューターを再起動するまでシステム構成はリセットされません。  
  
#### プロファイル セッションを終了するには  
  
1.  対象アプリケーションからプロファイラーをデタッチするには、次のいずれかの操作を行います。  
  
    -   サービスを停止します。  
  
         または  
  
    -   「**VSPerfCmd \/detach**」と入力します。  
  
2.  プロファイラーをシャットダウンします。  Type:  
  
     **VSPerfCmd \/shutdown**  
  
3.  \(省略可能\) プロファイル環境変数を削除します。  Type:  
  
     **VSPerfClrEnv \/globaloff**  
  
4.  コンピューターを再起動します。  
  
## 参照  
 [プロファイリング \(サービスの\)](../profiling/command-line-profiling-of-services.md)   
 [サンプリング メソッドのデータ ビュー](../profiling/profiler-sampling-method-data-views.md)