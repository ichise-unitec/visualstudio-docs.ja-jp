---
title: "割り当てフック関数と C ランタイムのメモリ割り当て |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], hook functions
- memory allocation, troubleshooting allocation hooks
- allocation hooks
- hooks, allocation
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b123e0e03f33f54e6d4fe82313c9a017e3baafff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>割り当てフック関数と C ランタイムのメモリ割り当て
メモリ割り当て用のフック関数には重要な制限事項があります。それは、メモリを内部的に割り当てるタイプの C ランタイム ライブラリ関数をフック関数から呼び出す場合、`_CRT_BLOCK` 型のブロック (C ランタイム ライブラリ関数によって内部的に割り当てられるメモリ) を明示的に無視する必要があることです。 割り当て用のフック関数の先頭に次のようなコードを追加すると、`_CRT_BLOCK` 型のブロックを無視できます。  
  
```  
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 割り当て用のフック関数で `_CRT_BLOCK` 型のブロックを無視しないと、このフック関数から C ランタイム ライブラリ関数を呼び出した場合に、プログラムが無限ループに陥ることがあります。 たとえば、`printf` は内部的にメモリを割り当てます。 フック コードを呼び出す場合`printf`、その結果の割り当てのフック関数を再度呼び出せるが発生し、 **printf** 、もう一度、スタック オーバーフローが発生するまでです。 `_CRT_BLOCK` 型の割り当て処理をレポートする必要がある場合は、この制限事項を回避するために、C ランタイム関数ではなく Windows API 関数を使用して書式設定や出力を行う方法があります。 Windows API は C ランタイム ライブラリのヒープを使用しないため、割り当て用のフック関数を使用しても無限ループに陥る心配はありません。  
  
 ランタイム ライブラリのソース ファイルを確認する場合は表示されます、既定の割り当てフック関数、 **CrtDefaultAllocHook** (を単に返す**TRUE**)、独自の別のファイルにあります。DBGHOOK です。C. 場合はするに呼び出せるは、アプリケーションの前に実行するランタイム スタートアップ コードが行われた割り当ての場合も、割り当てフック関数**メイン**関数、ユーザーの代わりに、独自のいずれかで、この既定の関数に置き換えることができます使用して[_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook)です。  
  
## <a name="see-also"></a>参照  
 [デバッグ用フック関数の作成](../debugger/debug-hook-function-writing.md)   
