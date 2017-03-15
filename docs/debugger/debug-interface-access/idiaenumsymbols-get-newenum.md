---
title: "IDiaEnumSymbols::get__NewEnum | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaEnumSymbols::get__NewEnum メソッド"
ms.assetid: 879609ea-8e5a-4fa3-afa6-d24870fb4392
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSymbols::get__NewEnum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

この列挙子の <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> のバージョンを取得します。  
  
## 構文  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### パラメーター  
 pRetVal  
 \[出力\] この列挙子の <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> のバージョンを表す `IUnknown` のインターフェイスを返します。  
  
## 戻り値  
 正常に終了した場合戻り `S_OK`; それ以外の場合はエラー コード。  
  
## 参照  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)