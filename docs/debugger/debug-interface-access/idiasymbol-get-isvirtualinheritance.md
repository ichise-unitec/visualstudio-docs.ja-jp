---
title: "IDiaSymbol::get_isVirtualInheritance |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 72906b92-dd4a-42e3-9b24-b77628fa48c1
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 58dc51cb22bf2974d02742bf33df5feaef16edd9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetisvirtualinheritance"></a>IDiaSymbol::get_isVirtualInheritance
指定するかどうか、`this`仮想継承を持つデータ メンバーを指すポインターです。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT get_isVirtualInheritance(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]ポインター、`BOOL`を指定するかどうか、`this`仮想継承を持つデータ メンバーを指すポインターです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外を返します`S_FALSE`またはエラー コード。  
  
## <a name="see-also"></a>参照  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)