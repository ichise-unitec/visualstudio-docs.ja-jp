---
title: "Idiareadexeatrvacallback::readexecutableatrva |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 71dd19f15d631c58e99a826ab1ff274b993afd5e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
指定した数の指定された相対仮想アドレス (RVA) 実行可能ファイルからで始まるバイトを読み取ります。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT ReadExecutableAtRVA (   
   DWORD  relativeVirtualAddress,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `relativeVirtualAddress`  
 [in]読み取りを開始する実行可能ファイルの RVA です。  
  
 `cbData`  
 [in]読み取るバイト数。  
  
 `pcbData`  
 [out]読み取られたバイト数を返します。  
  
 `data[]`  
 [入力、出力].ファイルから読み取られたバイトに設定している配列。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、DIA サポート コード相対仮想アドレスを使用して実行可能ファイルからデータのバイト数を読み込めません。 サポートにこのメソッドは、 [idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドです。  
  
## <a name="see-also"></a>参照  
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)