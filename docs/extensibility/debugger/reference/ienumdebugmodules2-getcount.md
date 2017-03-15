---
title: "IEnumDebugModules2::GetCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugModules2::GetCount"
helpviewer_keywords: 
  - "IEnumDebugModules2::GetCount"
ms.assetid: f4def3d2-7cc9-4cd2-9649-3b7e00a76220
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IEnumDebugModules2::GetCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

列挙体の要素数を返します。  
  
## 構文  
  
```cpp#  
HRESULT GetCount(  
   ULONG* pcelt  
);  
```  
  
```c#  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### パラメーター  
 `pcelt`  
 \[入力\] 列挙体の要素数を返します。  
  
## 戻り値  
 正常に終了した場合戻り `S_OK`; それ以外の場合はエラー コード。  
  
## 解説  
 このメソッドは `Next``Clone``Skip` と `Reset` のメソッドに実行する必要があることを指定する通常の COM 列挙インターフェイスの一部ではありません。  
  
## 参照  
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)