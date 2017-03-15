---
title: "方法: コマンド ラインを使用してプロファイラーを .NET サービスにアタッチし、メモリ データを収集する | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aeac39af-ad99-479f-aa36-4104356ca512
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 方法: コマンド ラインを使用してプロファイラーを .NET サービスにアタッチし、メモリ データを収集する
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ここでは、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイリング ツールのコマンド ライン ツールを使用してプロファイラーを [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] サービスにアタッチし、メモリ データを収集する方法について説明します。  メモリ割り当ての数およびサイズに関するデータだけでなく、メモリ オブジェクトの有効期間に関するデータも収集できます。  
  
> [!NOTE]
>  Windows 8 および Windows Server 2012 の強化されたセキュリティ機能によって、Visual Studio プロファイラーがこれらのプラットフォームでデータを収集する方法に大幅な変更が必要になりました。  Windows ストア アプリにも新しい収集手法が必要です。  「[Windows 8 および Windows Server 2012 アプリケーションのプロファイリング](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)」を参照してください。  
  
> [!NOTE]
>  プロファイリング ツールのコマンド ライン ツールは、[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] インストール ディレクトリの \\Team Tools\\Performance Tools サブディレクトリにあります。  64 ビット コンピューター上では、64 ビット バージョンのツールと 32 ビット バージョンのツールの両方を使用できます。  プロファイラーのコマンド ライン ツールを使用するには、コマンド プロンプト ウィンドウの PATH 環境変数にツールのパスを追加するか、コマンド自体にそれを追加します。  詳細については、「[コマンド ライン ツールへのパスの指定](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)」を参照してください。  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] サービスからメモリ データを収集するには、[VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) ツールを使用して、サービスをホストするコンピューター上で該当する環境変数を初期化する必要があります。  コンピューターをプロファイリング用に構成するには再起動が必要です。  
  
 次に、[VSPerfCmd](../profiling/vsperfcmd.md) ツールを使用してプロファイラーをサービス プロセスにアタッチします。  プロファイラーをサービスにアタッチしている間はデータ収集を一時停止し、完了後に再開できます。  
  
 プロファイル セッションを終了するには、プロファイラーをサービスからデタッチし、プロファイラーを明示的に終了する必要があります。  ほとんどの場合、セッションの最後にプロファイル環境変数を消去することをお勧めします。  
  
## プロファイラーのアタッチ  
  
#### プロファイラーを .NET Framework サービスにアタッチするには  
  
1.  インストールの必要なサービスがあればインストールします。  
  
2.  コマンド プロンプト ウィンドウを開きます。  
  
3.  プロファイル環境変数を初期化します。  Type:  
  
     **VSPerfClrEnv** {**\/globalsamplegc \/globalsamplegclife**}\[**\/samplelineoff**\]  
  
    -   **\/globalsamplegclife** オプションと **\/globalsamplegclife** オプションは、収集するメモリ データの種類を指定します。  次のいずれかのオプションを 1 つのみ指定します。  
  
     **\/globalsamplegc**  
     メモリの割り当てデータを収集できます。  
  
     **\/globalsamplegclife**  
     メモリの割り当てデータとオブジェクトの有効期間データを収集できます。  
  
    -   **\/samplelineoff** オプションを指定すると、ソース コードの行番号データの収集が無効になります。  
  
4.  コンピューターを再起動して、新しい環境構成を設定します。  
  
5.  起動の必要なサービスがあれば起動します。  
  
6.  コマンド プロンプト ウィンドウを開きます。  必要に応じて、プロファイラー パスを PATH 環境変数に追加します。  
  
7.  プロファイラーを起動します。  Type:  
  
     **VSPerfCmd**  [\/start](../profiling/start.md) **:sample**  [\/output](../profiling/output.md) **:** `OutputFile` \[`Options`\]  
  
    -   **\/start:sample** オプションによってプロファイラーが初期化されます。  
  
    -   **\/start** を使用する場合は **\/output:**`OutputFile` オプションを指定する必要があります。  `OutputFile` には、プロファイル データ \(.vsp\) ファイルの名前と場所を指定します。  
  
     **\/start:sample** オプションを使用する場合は、次の 1 つ以上のオプションを指定できます。  
  
    > [!NOTE]
    >  **\/user** オプションと **\/crosssession** オプションは、通常、サービスで必要です。  
  
    |オプション|説明|  
    |-----------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|プロセスを所有するアカウントのドメインおよびユーザー名を指定します。  このオプションは、ログオンしているユーザーとは別のユーザーがプロセスを実行している場合に指定する必要があります。  プロセスの所有者は、Windows タスク マネージャーの \[プロセス\] タブの \[ユーザー名\] 列に表示されます。|  
    |[\/crosssession](../profiling/crosssession.md)|他のログオン セッションにおけるプロセスのプロファイリングを有効にします。  このオプションは、ASP.NET アプリケーションが別のセッションで実行されている場合に必要です。  セッション ID は、Windows タスク マネージャーの \[プロセス\] タブの \[セッション ID\] 列に表示されます。  **\/crosssession** の省略形として、**\/CS** を指定することができます。|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|サービスが実行されるログオン アカウントのドメインおよびユーザー名を指定します \(省略可能\)。  ログオン アカウントは、Windows サービス コントロール マネージャーのサービスの \[ログオン方法\] 列に表示されます。|  
    |[\/crosssession&#124;cs](../profiling/crosssession.md)|他のログオン セッションにおけるプロセスのプロファイリングを有効にします。|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|プロファイリング実行中に収集する Windows パフォーマンス カウンターを指定します。|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter** と共にのみ使用します。  Windows パフォーマンス カウンター コレクション イベントの間隔をミリ秒単位で指定します。  既定値は 500 ミリ秒です。|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|プロファイリング実行中に収集する ETW \(Event Tracing for Windows\) イベントを指定します。  ETW イベントは独立した \(.etl\) ファイルに収集されます。|  
  
8.  プロファイラーをサービスにアタッチします。  Type:  
  
     **VSPerfCmd**  [\/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} \[[\/targetclr](../profiling/targetclr.md)**:**`Version`\]  
  
    -   サービスのプロセス ID またはプロセス名を指定します。  Windows タスク マネージャーで、実行中のすべてのプロセスのプロセス ID と名前を参照できます。  
  
    -   **targetclr:** `Version` には、アプリケーションに複数のバージョンのランタイムが読み込まれている場合に、プロファイリングを行う共通言語ランタイム \(CLR: Common Language Runtime\) のバージョンを指定します。  省略可能。  
  
## データ収集の制御  
 サービスの実行中に、**VSPerfCmd.exe** のオプションを使用して、プロファイラー データ ファイルへのデータ書き込みを停止または開始できます。  データ収集を制御することにより、アプリケーションの起動や終了など、プログラム実行の特定の部分についてのデータ収集を行うことができます。  
  
#### データ収集を開始および停止するには  
  
-   次に示す **VSPerfCmd** のオプションの組み合わせにより、データ収集を開始および停止します。  個別のコマンド ラインで各オプションを指定します。  データ収集のオンとオフは複数回切り替えることができます。  
  
    |オプション|説明|  
    |-----------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|すべてのプロセスのデータ収集を開始 \(**\/globalon**\) または停止 \(**\/globaloff**\) します。|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID`  [\/processoff](../profiling/processon-and-processoff.md) **:** `PID`|プロセス ID \(`PID`\) で指定されたプロセスのデータ収集を開始 \(**\/processon**\) または停止 \(**\/processoff**\) します。|  
    |**\/attach:**{`PID`&#124;`ProcName`} [\/detach](../profiling/detach.md)\[:{`PID`&#124;`ProcName`}\]|**\/attach** は、プロセス ID またはプロセス名で指定したプロセスのデータ収集を開始します。  **\/detach** は、指定されたプロセスのデータ収集を停止します。特定のプロセスが指定されていない場合は、すべてのプロセスのデータ収集を停止します。|  
  
## プロファイル セッションの終了  
 プロファイル セッションを終了するには、プロファイラーがデータ収集を停止している必要があります。  サービスを停止するか **VSPerfCmd \/detach** オプションを呼び出すことによって、サンプリング メソッドを使用してプロファイリングが実行されているアプリケーションからのデータ収集を停止できます。  次に、**VSPerfCmd** [\/shutdown](../profiling/shutdown.md) オプションを呼び出して、プロファイラーをオフにし、プロファイル データ ファイルを閉じます。  **VSPerfClrEnv \/globaloff** コマンドによってプロファイル環境変数は消去されますが、コンピューターを再起動するまでシステム構成はリセットされません。  
  
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
 [.NET メモリのデータ ビュー](../profiling/dotnet-memory-data-views.md)