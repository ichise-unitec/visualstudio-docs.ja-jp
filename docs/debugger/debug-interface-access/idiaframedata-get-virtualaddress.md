---
title: "Idiaframedata::get_virtualaddress |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::get_virtualAddress method
ms.assetid: de137bee-132f-4aae-a067-9578b7a3e6d4
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dfd4260ddb0f9306f68489034e22f1939d79ff12
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idiaframedatagetvirtualaddress"></a>IDiaFrameData::get_virtualAddress
フレームのコードの仮想アドレス (VA) を取得します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT get_virtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]フレームのコードの仮想アドレスを返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`です。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。  
  
## <a name="see-also"></a>参照  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)