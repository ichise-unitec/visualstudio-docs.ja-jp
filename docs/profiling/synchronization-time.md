---
title: "同期時間 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.synchronization
helpviewer_keywords: Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8252bc569ef17725570b5222afa12a59c387c278
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="synchronization-time"></a>同期時間
タイムライン内のこれらのセグメントは、同期として分類されたブロック時間に関連付けられています。 同期でスレッドにブロックされたマークが付いている場合、次のいずれかを示しています。  
  
-   スレッドの実行が、`EnterCriticalSection()` または `WaitForSingleObject()` などの既知のスレッド同期 API を呼び出す結果になった可能性がある。  
  
-   API 照合アルゴリズムが全体として包括的にならず、そのために他のカテゴリにマップされている可能性がある一部の API も同期として表示されている可能性がある。呼び出し履歴内のフレームの最終的な到達先が、このカテゴリにマップされた、基になるカーネルをブロックしている基本要素である場合にこの状態になります。  
  
 スレッド ブロック イベントの根本的な原因を理解するために、ブロック呼び出し履歴とプロファイル レポートをよく調べてください。  
  
## <a name="see-also"></a>参照  
 [スレッド ビュー](../profiling/threads-view-parallel-performance.md)