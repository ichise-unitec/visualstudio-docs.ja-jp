---
title: "IDebugCoreServer2::GetPort |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer2::GetPort
helpviewer_keywords: IDebugCoreServer2::GetPort
ms.assetid: 3f5ea4a8-6085-4600-980a-9e48f8b5be56
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a51eefc5defb02f1affbbad8822296150186e060
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver2getport"></a>IDebugCoreServer2::GetPort
特定のポートを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetPort(   
   REFGUID       guidPort,  
   IDebugPort2** ppPort  
);  
```  
  
```csharp  
int GetPort(   
   ref Guid        guidPort,  
   out IDebugPort2 ppPort  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guidPort`  
 [in]取得するポートの GUID です。  
  
 `ppPort`  
 [out]返します、 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)目的のポートを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。 返します`E_PORTSUPPLIER_NO_PORT`場合は、指定された識別子のポートはありません。  
  
## <a name="see-also"></a>参照  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)