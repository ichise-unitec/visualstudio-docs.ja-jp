---
title: "エラー: Web サーバーはロックダウンされているし、DEBUG の動詞がブロックされて |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.webdbg_debug_verb_blocked
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d8d16d8fed99696cbefdb81e761d31d2427a20a7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb"></a>エラー ： Web サーバーが制限され、デバッグの有効化に必要な DEBUG 動詞をブロックしています。
IIS Lockdown ツールが実行され、URLScan がインストールされてアクティブになっているため、Web アプリケーションまたは XML Web サービスのステップ インに失敗しました。 この条件によって、IIS は DEBUG の動詞を受け取ることができません。  
  
 URLScan は IIS Lockdown ツールと連携して動作するセキュリティ ツールです。これによって IIS Web サイト管理者は、不要な機能をオフにしたり、サーバーが処理する HTTP 要求の種類を制限したりできます。 URLScan では、特定の HTTP 要求を遮断することによって、有害な要求がサーバーに到達して損害を与えることを防止できます。  
  
 アプリケーションが Windows Server 2003 上の IIS 6.0 で実行されている場合、IIS Lockdown ツールを実行する必要はありません。IIS 6.0 は、同じ機能を備えているためです。  
  
### <a name="to-enable-debugging-on-a-web-server-with-urlscan-installed"></a>URLScan がインストールされた Web サーバーでデバッグを有効にするには  
  
1.  Urlscan.ini ファイルを探します。 通常は、次のようなディレクトリの下にあります。  
  
     C:\WINNT\System32\Inetsrv\urlscan  
  
2.  ファイルのコピーを作成し、名前**urlscan.old という**です。  
  
3.  メモ帳または任意のテキスト エディターを使って、元の Urlscan.ini ファイルを開きます。  
  
4.  Urlscan.ini で、[AllowVerbs] セクションを探します。 DEBUG を [AllowVerbs] セクションに追加します。 DEBUG が [AllowVerbs] セクションにある場合は、セミコロン (;) を削除して、動詞のコメント アウトを解除します。  
  
5.  [DenyVerbs] セクションを探します。 DEBUG が [DenyVerbs] セクションにある場合は、それを削除します。  
  
6.  ファイルを保存します。  
  
7.  サーバーまたは IIS を再起動します。  
  
## <a name="see-also"></a>参照  
 [Web アプリケーションのデバッグ: エラーとトラブルシューティング](../debugger/debugging-web-applications-errors-and-troubleshooting.md)   
 [エラー : Web サーバーでは要求されたリソースを見つけられませんでした](../debugger/error-the-web-server-could-not-find-the-requested-resource.md)