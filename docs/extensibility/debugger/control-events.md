---
title: "コントロール イベントの |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 15f9eff023fa875499881eb05a0795b0eaa83842
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="control-events"></a>コントロールのイベント
プログラムの制御された実行中にイベントを送信する必要があります。 使用して送信されるすべてのイベントは、 [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md)インターフェイスし、属性を実装する必要がありますが、 [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md)メソッドです。  
  
## <a name="additional-methods"></a>追加のメソッド  
 一部のイベントには、次のような追加のメソッドの実装が必要。  
  
-   送信する、 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) (DE) のデバッグ エンジンが初期化されたときに、インターフェイスでは、実装する必要があります、 [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)メソッドです。  
  
-   実行の制御などのコントロール イベントの実装が必要です、 [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md)と[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)インターフェイスです。 **IDebugBreakEvent2**非同期区切りでのみ必要です。  
  
-   実装を必要と関数にステップ イン、 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)インターフェイスとそのメソッドです。  
  
 ブレークポイントから派生したイベントの実装が必要、 [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)、 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)、および[IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)インターフェイス、だけでなく[IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)と[EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)メソッドです。  
  
 非同期の式の評価では、実装する必要があります、 [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)インターフェイスとその[IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)[および GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)メソッドです。  
  
 同期イベントは、実装する必要があります、 [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)メソッドです。  
  
 文字列形式の出力を書き込む、エンジンを実装する必要があります、 [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)メソッドです。  
  
## <a name="see-also"></a>参照  
 [実行の制御と状態の評価](../../extensibility/debugger/execution-control-and-state-evaluation.md)