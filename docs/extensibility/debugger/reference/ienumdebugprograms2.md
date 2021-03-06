---
title: "IEnumDebugPrograms2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPrograms2
helpviewer_keywords: IEnumDebugPrograms2
ms.assetid: 7fbb8fb7-db64-4546-a364-dc668430c8af
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b52c4f28f1f027648674f2be561fc11d7117b6f4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugprograms2"></a>IEnumDebugPrograms2
このインターフェイスは、現在のデバッグ セッションで実行するプログラムを列挙します。  
  
## <a name="syntax"></a>構文  
  
```  
IEnumDebugPrograms2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デバッグ エンジン (DE) は、DE、デバッグ中のプログラムの一覧を提供するには、このインターフェイスを実装します。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 Visual Studio 呼び出し[EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)このインターフェイスを取得します。 [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md) Visual Studio では使用されません。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IEnumDebugPrograms2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[次へ](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)|列挙のシーケンスで、プログラムの指定した数を取得します。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprograms2-skip.md)|列挙のシーケンスの プログラムの指定した数をスキップします。|  
|[リセット](../../../extensibility/debugger/reference/ienumdebugprograms2-reset.md)|列挙のシーケンスを先頭にリセットします。|  
|[複製](../../../extensibility/debugger/reference/ienumdebugprograms2-clone.md)|現在の列挙子と同じ列挙の状態を含む列挙子を作成します。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprograms2-getcount.md)|列挙子では、プログラムの数を取得します。|  
  
## <a name="remarks"></a>コメント  
 Visual Studio では、このインターフェイスを使用します。  
  
-   追加、**モジュール**ウィンドウ (を呼び出して[EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)し、呼び出す[EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)プログラムごとに)。  
  
-   追加、**プロセスにアタッチする**リスト (を呼び出して`IDebugProcess2::EnumPrograms`し、呼び出す[QueryInterface](/cpp/atl/queryinterface)各[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) を取得するインターフェイス[IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)インターフェイス)。  
  
-   プロセスの各プログラムをデバッグできます DEs の一覧を生成 (を使用して[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md))。  
  
-   各プログラムに編集と続行 (ENC) の更新プログラムを適用 (IDebugProcess2::EnumPrograms を呼び出しを呼び出すことで、 [GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md))。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>参照  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)