---
title: "IDebugProgram2::EnumCodeContexts |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::EnumCodeContexts
helpviewer_keywords: IDebugProgram2::EnumCodeContexts
ms.assetid: 478e06a2-07bb-4841-8887-deab0f42ebd0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b1bf8039d9602bee59ff31996d2a424de28ae9bf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2enumcodecontexts"></a>IDebugProgram2::EnumCodeContexts
ソース ファイル内の指定位置にコード コンテキストの一覧を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT EnumCodeContexts(   
   IDebugDocumentPosition2*  pDocPos,  
   IEnumDebugCodeContexts2** ppEnum  
);  
```  
  
```csharp  
int EnumCodeContexts(   
   IDebugDocumentPosition2     pDocPos,  
   out IEnumDebugCodeContexts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pDocPos`  
 [in][IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)を IDE に既知のソース ファイル内の抽象の位置を表すオブジェクト。  
  
 `ppEnum`  
 [out]返します、 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)コード コンテキストの一覧を含むオブジェクトです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 このメソッドにより、セッションのデバッグ マネージャー (SDM) または IDE でコードの位置にソース ファイルの位置をマップします。 ソース コード (たとえば、C++ テンプレート) の複数のブロックを生成する場合は、1 つ以上のコードのコンテキストが返されます。  
  
## <a name="see-also"></a>参照  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)