---
title: "GPU アクティビティ (他のプロセス) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bd39910631ce67693e1e039307813a5ded13e326
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="gpu-activity-other-processes"></a>GPU アクティビティ (他のプロセス)
同時実行ビジュアライザーのスレッド ビューの **[GPU アクティビティ (他のプロセス)]** セグメントは、GPU がシステム上の他のプロセスのために要求を処理していた時間を示します。 これらの要求はダイレクト メモリ アクセス (DMA) パケットとして GPU に送信されます。  セグメントの長さは GPU でパケットが処理されていた時間を表します。  
  
 このようなセグメントを選択した場合、**[現在]** タブのレポートには処理されたパケットの情報が表示されます。  情報には、パケットが DirectX に関連するハードウェア キューで待機していた時間、パケットを送信したプロセス、パケットの処理に要した時間が含まれます。