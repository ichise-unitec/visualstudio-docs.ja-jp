---
title: "Event Tracing for Windows (ETW) レポート | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7fb851cbeed74bf34768a930297477f54eacf7f1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="event-tracing-for-windows-etw-report"></a>ETW (Event Tracing for Windows) レポート
Windows イベント トレーシング (ETW) レポートには、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイル ツールのパフォーマンス セッションで記録された ETW イベントが一覧表示されます。 ETW データはバイナリ (.etl) ファイルで収集されます。  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] インターフェイスでは ETW レポートを表示できません。  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] インターフェイスのプロファイル ツールを利用して ETW データを収集する方法については、「[方法: ETW (Event Tracing for Windows) データを収集する](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)」を参照してください。  
  
-   [VSPerfCmd](../profiling/vsperfcmd.md) コマンド ライン ツールを利用して ETW データを収集する方法については、「[Events](../profiling/events-vsperfcmd.md)」を参照してください。  
  
-   ETW レポートは **VSReport/Summary:ETW** コマンドを利用して生成します。 詳細については、「[VSPerfReport](../profiling/vsperfreport.md)」を参照してください。  
  
|Column|説明|  
|------------|-----------------|  
|**タイムスタンプ**|イベントが発生した日時を識別します。|  
|**プロセス ID**|イベントを生成したプロセスを識別します。|  
|**スレッド ID**|イベントを生成したスレッドを識別します。|  
|**説明**|イベント プロバイダーを識別します。|  
|**Type**|イベントの種類を識別します。|  
|**プロパティ**|イベントのプロパティ。 各イベントは角かっこで囲まれた名前と値のペアになり、コンマで区切られます。|