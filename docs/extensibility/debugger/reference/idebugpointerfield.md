---
title: "IDebugPointerField |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPointerField
helpviewer_keywords: IDebugPointerField interface
ms.assetid: d51bd5b2-f18e-4e27-b4fb-e6f652fbf635
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1a4f110308ead7fde00528ed0404becd802069f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpointerfield"></a>IDebugPointerField
このインターフェイスは、ポインター型を表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugPointerField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 シンボル プロバイダーでは、ポインターを表すためには、このインターフェイスを実装します。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 使用して[QueryInterface](/cpp/atl/queryinterface)からこのインターフェイスを取得、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスの場合[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)返します`FIELD_TYPE_POINTER`です。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 メソッドだけでなく、`IDebugField`と`IDebugContainerField`インターフェイス、このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetDereferencedField](../../../extensibility/debugger/reference/idebugpointerfield-getdereferencedfield.md)|返します、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)ポインターのターゲットを記述します。|  
  
## <a name="remarks"></a>コメント  
 C および C++ でポインターは配列表記と共に使用した場合にコンテナーを指定できます。 例として、 `char *pString`、`pString`へのポインターの型を持つ`char`します。 `pString[3]`ポインターであるコンテナーの型を持つ`char`そのコンテナーの 4 番目の要素を参照します。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>参照  
 [シンボル プロバイダー インターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)