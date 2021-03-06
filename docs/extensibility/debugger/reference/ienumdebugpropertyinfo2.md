---
title: "IEnumDebugPropertyInfo2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPropertyInfo2
helpviewer_keywords: IEnumDebugPropertyInfo2
ms.assetid: fdea8262-40b8-473e-88ba-639e4c4648e6
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 578418c1afa831120cf77fd5a1da48d84126ec8f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugpropertyinfo2"></a>IEnumDebugPropertyInfo2
このインターフェイスの列挙[DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)構造体。  
  
## <a name="syntax"></a>構文  
  
```  
IEnumDebugPropertyInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デバッグ エンジン (DE) では、特定のプロパティの情報を表すには、このインターフェイスを実装します。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出す[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)特定のプロパティの子を表す、このインターフェイスを取得します。 呼び出す[EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)特定のスタック フレームのプロパティを表す、このインターフェイスを取得します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IEnumDebugPropertyInfo2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[次へ](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md)|指定した数を取得[DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)列挙のシーケンス内の構造体。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-skip.md)|指定した数のスキップ[DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)列挙のシーケンス内の構造体。|  
|[リセット](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-reset.md)|列挙のシーケンスを先頭にリセットします。|  
|[複製](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-clone.md)|現在の列挙子と同じ列挙の状態を含む列挙子を作成します。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)|数を取得[DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)構造体、列挙子にします。|  
  
## <a name="remarks"></a>コメント  
 一般に、プロパティは、関連付けられているプロパティ オブジェクトまたはスタック フレームに適したその他の情報だけでなく、名前、値、アドレス、および種類を含めることができる情報の階層です。 参照してください[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)詳細についてはします。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>参照  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)