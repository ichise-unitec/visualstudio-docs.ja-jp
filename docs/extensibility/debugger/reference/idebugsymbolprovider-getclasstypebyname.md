---
title: "IDebugSymbolProvider::GetClassTypeByName |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugSymbolProvider::GetClassTypeByName
helpviewer_keywords: IDebugSymbolProvider::GetClassTypeByName method
ms.assetid: 2c748909-51dc-49b7-b193-19f96fca1138
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4af89a2086e92c01aa677ddcda4a22e6f5e40098
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idebugsymbolprovidergetclasstypebyname"></a>IDebugSymbolProvider::GetClassTypeByName
このメソッドは、完全修飾クラス名を表すクラスのフィールドの型を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetClassTypeByName(   
   LPCOLESTR          pszClassName,  
   NAME_MATCH         nameMatch,  
   IDebugClassField** ppField  
);  
```  
  
```csharp  
int GetClassTypeByName(  
   string               pszClassName,   
   NAME_MATCH           nameMatch,   
   out IDebugClassField ppField  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszClassName`  
 [in]クラス名。  
  
 `nameMatch`  
 [in]たとえば、一致の大文字小文字を区別の種類を選択します。 値、 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)列挙します。  
  
 `ppField`  
 [out]によって表されるクラス型を返します、 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)インターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>参照  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)