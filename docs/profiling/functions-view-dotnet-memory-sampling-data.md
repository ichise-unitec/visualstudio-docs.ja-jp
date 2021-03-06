---
title: "関数ビュー - .NET メモリ サンプリング データ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 92d2df0182f976af36e9182d080ef6b51130c826
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="functions-view---net-memory-sampling-data"></a>関数ビュー - .NET メモリ サンプリング データ
サンプリング メソッドを使用して収集された .NET メモリの割り当てプロファイル データの関数ビューには、プロファイル実行中にメモリを割り当てた関数が一覧表示され、割り当てのサイズと数が報告されます。  
  
|Column|説明|  
|------------|-----------------|  
|**プロセス ID**|プロファイリング実行のプロセス ID (PID) です。|  
|**プロセス名**|プロセスの名前です。|  
|**モジュール名**|関数を含むモジュールの名前です。|  
|**モジュール パス**|関数を含むモジュールのパスです。|  
|**ソース ファイル**|この関数の定義を含むソース ファイルです。|  
|**関数名**|関数の完全修飾名です。|  
|**関数行番号**|ソース ファイルでのこの関数の開始行番号です。|  
|**関数アドレス**|関数のアドレス。|  
|**割り当て数 (子を含む)**|この関数とその子関数で割り当てられたオブジェクトの総数。|  
|**割り当て % (子を含む)**|プロファイル実行で割り当てられたすべてのオブジェクトに対する、この関数の包括的割り当てであったオブジェクトの割合。|  
|**割り当て数 (関数のみ)**|その関数が呼び出し履歴の最上位で直接実行されたときに作成されたオブジェクトの数。 この数には、子関数で作成されたオブジェクトが含まれません。|  
|**割り当て % (関数のみ)**|プロファイル実行で割り当てられたすべてのオブジェクトに対する、この関数の排他的割り当てであったオブジェクトの割合。|  
|**割り当てバイト数 (子を含む)**|この関数とその子関数で割り当てられたメモリのバイト数。|  
|**割り当てバイト数 % (子を含む)**|プロファイル実行で割り当てられたすべてのメモリのバイト数に対する、この関数の包括バイトであったバイト数の割合。|  
|**割り当てバイト数 (関数のみ)**|この関数によって割り当てられたメモリのバイト数。その子関数によるものは含まれません。|  
|**割り当てバイト数 % (関数のみ)**|プロファイル実行で割り当てられたすべてのメモリのバイト数に対する、この関数の排他バイトであったバイト数の割合。|  
  
## <a name="see-also"></a>参照  
 [関数ビュー - インストルメンテーション](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [関数ビュー](../profiling/functions-view-sampling-data.md)   
 [関数 ビュー](../profiling/functions-view-instrumentation-data.md)