---
title: "DA0029: サポートされていない CLR バージョンです | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e11b053b867679f65052af5dea93799e4b356892
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: サポートされていない CLR バージョンです。
|||  
|-|-|  
|規則 ID|DA0029|  
|カテゴリ|プロファイリング ツールの使用|  
|プロファイル方法|コマンド ラインからのプロファイリング|  
|メッセージ|収集時に、サポートされていない CLR バージョンが検出されました。 マネージ シンボルが正しく解決されない可能性があります。|  
|規則の種類|情報。|  
  
## <a name="cause"></a>原因  
 プロファイリング ツールでサポートされていない [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)] を使用するアプリケーションをプロファイリングしようとしています。  
  
## <a name="rule-description"></a>規則の説明  
 アプリケーションで実行されているマネージ コードのシンボルをプロファイリング ツールが解決できないため、この警告が発生します。 プロファイリング ツールは、[!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)] を実行しているアプリケーションのマネージ コード シンボルを解決できません。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 なし。