---
title: "プロファイラー サンプリング メソッドを使用したサービスのアプリケーション統計情報の収集 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 07840ab2-3a92-4744-ac87-48b19e0ceecd
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# プロファイラー サンプリング メソッドを使用したサービスのアプリケーション統計情報の収集
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ここでは、コマンド ラインからサンプリング メソッドを使用して Windows サービスのパフォーマンス統計情報を収集する手順とオプションについて説明します。  
  
> [!NOTE]
>  Windows 8 および Windows Server 2012 の強化されたセキュリティ機能によって、Visual Studio プロファイラーがこれらのプラットフォームでデータを収集する方法に大幅な変更が必要になりました。  Windows ストア アプリにも新しい収集手法が必要です。  「[Windows 8 および Windows Server 2012 アプリケーションのプロファイリング](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)」を参照してください。  
  
## 一般的なタスク  
  
|タスク|関連するコンテンツ|  
|---------|---------------|  
|**プロファイラーを .NET サービスにアタッチする**|-   [方法: プロファイラーを .NET サービスにアタッチし、アプリケーションの統計情報を収集する](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)|  
|**階層相互作用データを追加する**|-   [階層相互作用データの収集](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**プロファイラーを C\/C\+\+ サービスにアタッチする**|-   [方法: プロファイラーをネイティブ サービスにアタッチし、アプリケーションの統計情報を収集する](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## 関連するタスク  
  
### Windows サービスのプロファイリング  
  
|タスク|関連するコンテンツ|  
|---------|---------------|  
|**インストルメンテーション メソッドを使用してプロファイリングする**|-   [インストルメンテーションを使用した詳細なタイミング データの収集](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**.NET メモリ割り当ておよびガベージ コレクションをプロファイリングする**|-   [.NET メモリ データの収集](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**リソースの競合およびスレッド アクティビティをプロファイリングする**|-   [同時実行データの収集](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
  
### サンプリング方式を使用したプロファイリング  
  
|タスク|関連するコンテンツ|  
|---------|---------------|  
|**スタンドアロン \(クライアント\) アプリケーションをプロファイリングする**|-   [サンプリングを使用したアプリケーション統計情報の収集](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**ASP.NET Web アプリケーションをプロファイリングする**|-   [サンプリングを使用したアプリケーション統計情報の収集](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
  
### サンプリング データ ビューおよびレポートの分析  
 [サンプリング メソッドのデータ ビュー](../profiling/profiler-sampling-method-data-views.md)