---
title: "IDebugParsedExpression::EvaluateSync |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugParsedExpression::EvaluateSync
helpviewer_keywords: IDebugParsedExpression::EvaluateSync method
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 261359ae3dc82f8544d0f48cf0e8f1103ccedd5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idebugparsedexpressionevaluatesync"></a>IDebugParsedExpression::EvaluateSync
このメソッドは、解析された式を評価し、必要に応じて別のデータ型に結果をキャストします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT EvaluateSync(   
   DWORD                 dwEvalFlags,  
   DWORD                 dwTimeout,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BSTR                  bstrResultType,  
   IDebugProperty2**     ppResult  
);  
```  
  
```csharp  
int EvaluateSync(  
   uint                 dwEvalFlags,   
   uint                 dwTimeout,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   string               bstrResultType,   
   out IDebugProperty2  ppResult  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwEvalFlags`  
 [in]組み合わせた[EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)定数式が評価される方法を制御します。  
  
 `dwTimeout`  
 [in]このメソッドから戻る前に待機するミリ秒単位で最大の時間を指定します。 使用して`INFINITE`無制限に待機します。  
  
 `pSymbolProvider`  
 [in]として表現される、シンボル プロバイダー、 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)インターフェイスです。  
  
 `pAddress`  
 [in]表される、メソッド内の現在の実行場所、 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)インターフェイスです。  
  
 `pBinder`  
 [in]として表現される、バインダー、 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)インターフェイスです。  
  
 `bstrResultType`  
 [in]結果の型にキャストする必要があります。 この引数は、null 値を指定できます。  
  
 `ppResult`  
 [out]返します、 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)評価の結果を表すインターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 式の評価コンテキストを指定した`pAddress`式内のシンボルの値を決定するルールの使用言語のスコープ、格納方法を決定できるようになります。  
  
## <a name="see-also"></a>参照  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)