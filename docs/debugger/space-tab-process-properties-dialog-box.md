---
title: "[スペース] タブ ([プロセス プロパティ] ダイアログ ボックス) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "プロセス プロパティ (Windows NT の)"
ms.assetid: c4de1866-7447-48f7-aa88-28ad92c0b930
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# [スペース] タブ ([プロセス プロパティ] ダイアログ ボックス)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

\[スペース\] タブを使用すると、プロセスのアドレス空間を調べることができます。  [&#91;プロセス プロパティ&#93; ダイアログ ボックス](../debugger/process-properties-dialog-box.md)を表示するには、[プロセス ビュー](../debugger/processes-view.md) ウィンドウにフォーカスを移動します。  ツリーで任意のプロセス ノードを選択し、\[表示\] メニューの \[プロパティ\] をクリックします。  
  
 \[スペース\] タブには、次の項目があります。  
  
|エントリ|Description|  
|----------|-----------------|  
|**\[サイズを表示\]**|空間のカテゴリ \(イメージ、割り当て済み、予約済み、未割り当て\) を選択するには、このリスト ボックスを使用します。|  
|**\[実行可能サイズ\]**|このプロセスが使用しているすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。  実行可能メモリはプログラムが実行できるメモリですが、読み取りや書き込みを行うことはできません。|  
|**\[実行読み取り専用サイズ\]**|このプロセスが使用している、読み取り専用プロパティで使用中のすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。  実行読み取り専用メモリは、実行でき、読み取ることもできるメモリです。|  
|**\[実行読み書き可能サイズ\]**|このプロセスが使用している、読み書き可能プロパティで使用中のすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。  実行読み書き可能メモリは、プログラムが実行できるメモリです。読み取りと変更も行うことができます。|  
|**\[実行書き込み可能サイズ\]**|プログラムが実行でき、読み取りと書き込みもできるすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。  この種類の保護は、メモリをプロセス間で共有する必要がある場合に使用されます。  共有プロセスでメモリの読み取りだけを行う場合は、同じメモリを使用します。  共有プロセスで書き込みアクセス権が必要な場合は、そのプロセス用にこのメモリのコピーが作成されます。|  
|**\[非アクセス サイズ\]**|プロセスで使用できないすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。  書き込みまたは読み取りが試行されると、アクセス違反が生成されます。|  
|**\[読み取り専用サイズ\]**|実行でき、読み取ることもできるすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。|  
|**\[読み書き可能サイズ\]**|読み取りと書き込みを行うことのできるすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。|  
|**\[書き込み可能サイズ\]**|書き込みではなく読み取りのためにメモリを共有できるすべてのアドレス空間 \(選択したカテゴリに属しているもの\) の合計サイズです。  プロセスがこのメモリを読み取るとき、同じメモリを共有できます。  ただし、共有するプロセスがこの共有メモリへの読み取り\/書き込みアクセス権を必要とする場合は、そのメモリのコピーが書き込み用に作成されます。|