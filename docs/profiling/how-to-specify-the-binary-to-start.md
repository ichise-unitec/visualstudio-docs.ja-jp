---
title: "方法: 開始するバイナリを指定する | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
ms.assetid: ba77fcf4-8d78-49f1-b8f3-7dd0acf84306
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5d17c59c44dc64b2e3fa3e53553a65ee9998b7ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-binary-to-start"></a>方法 : 開始するバイナリを指定する
DLL などのバイナリをプロファイルするには、**[\<Target> プロパティ ページ]** ダイアログ ボックスに情報を入力する必要があります。 この情報は、DLL プロジェクトの呼び出し元アプリケーションの場所を示します。  
  
 **必要条件**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)]、 [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]、 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
### <a name="to-specify-the-executable-to-start"></a>開始する実行可能ファイルを指定するには  
  
1.  **パフォーマンス エクスプローラー**で、対象のバイナリを右クリックし、**[プロパティ]** をクリックします。  
  
2.  **[プロパティ ページ]** ダイアログ ボックスで、**[起動]** プロパティをクリックします。  
  
3.  **[プロジェクト プロパティの上書き]** チェック ボックスを選択します。  
  
4.  **[起動する実行可能ファイル]** テキスト ボックスで、ファイルの場所を指定します。  
  
5.  **[引数]** テキスト ボックスで、アプリケーションを起動するのに必要な引数を指定します。  
  
6.  **[作業ディレクトリ]** テキスト ボックスで、ディレクトリの場所を指定します。  
  
7.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [パフォーマンス セッションの構成](../profiling/configuring-performance-sessions.md)