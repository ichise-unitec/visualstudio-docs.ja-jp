---
title: "プロファイル ツールのコマンド ライン ツールへのパスの指定 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b33ee79d51dfcdb3db9021d3613672c44aef8956
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>プロファイル ツールのコマンド ライン ツールへのパスの指定
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイリング ツールのコマンド ライン ツールのパスは、PATH 環境変数に追加されません。 32 ビット コンピューターでは、これらのツールは単一のディレクトリ内にあります。 64 ビット コンピューターには、32 ビット バージョンと 64 ビット バージョンの両方のプロファイリング ツールがあります。  
  
## <a name="32-bit-computers"></a>32 ビット コンピューター  
 32 ビット コンピューターでの既定のプロファイリング ツール ディレクトリは、*ドライブ*\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools です。  
  
## <a name="64-bit-computers"></a>64 ビット コンピューター  
 64 ビット コンピューターでは、プロファイリングするアプリケーションのターゲット プラットフォームに応じてパスを指定します。  
  
-   32 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。  
  
     *ドライブ*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools  
  
-   64 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。  
  
     *ドライブ*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\x64