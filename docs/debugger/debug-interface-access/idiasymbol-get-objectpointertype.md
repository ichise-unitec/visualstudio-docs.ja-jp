---
title: "IDiaSymbol::get_objectPointerType | Microsoft Docs"
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
  - "IDiaSymbol::get_objectPointerType メソッド"
ms.assetid: bce193b9-67b0-4c35-96e5-6a664937322e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_objectPointerType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

クラスのメソッドのオブジェクト ポインターの種類を取得します。  
  
## 構文  
  
```cpp#  
HRESULT get_objectPointerType (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### パラメーター  
 `pRetVal`  
 \[入力\] クラス メソッドにはオブジェクト [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) のポインターを表すオブジェクトを返します。  
  
## 戻り値  
 正常に終了した場合戻り `S_OK`; それ以外の場合戻り `S_FALSE` またはエラー コード。  
  
> [!NOTE]
>  `S_FALSE` の戻り値はプロパティのシンボルで使用できないことを意味します。  
  
## 解説  
 このプロパティは `SymTagFunctionType` の [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md) の型が付いたシンボルにのみ適用されます。  
  
## 参照  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)