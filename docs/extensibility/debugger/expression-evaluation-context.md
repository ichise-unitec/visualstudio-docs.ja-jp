---
title: "式の評価コンテキスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ab4e57f500c2dfbfe673713c784cbc93ff52a73d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluation-context"></a>式の評価コンテキスト
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 、デバッグ、**式の評価コンテキスト**:  
  
-   式の評価のコンテキストを表します。 一般に、評価コンテキストは、変数、パラメーター、関数、およびメソッドを評価するための構文のスコープに対応します。 たとえば、スタック フレームに関連付けられている式の評価コンテキスト (該当する場合) は、ローカル変数、メソッドのパラメーター、およびクラス メンバーを評価するため、コンテキストが提供されます。  
  
-   プログラムがブレークポイントで停止したときに存在します。 式自体は、バインディング、および特定のコンテキスト内で評価するための準備が整っている解析された式を表すデータ構造です。  
  
     詳しくは、式を使用して作成、 [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)メソッドです。 式を評価するときに、変数または引数とその値の型と名前を含む印刷可能な文字列を生成します。 この文字列は、[ウォッチ] ウィンドウまたは IDE の [ローカル] ウィンドウに表示されます。  
  
     指定された、`BSTR`と[IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md)デバッグ エンジン (DE) を作成できるインターフェイスを[IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md)式を解析してインターフェイスです。 指定された、`IDebugExpression2`インターフェイス、デが同期または非同期の式の評価から得られた値を取得できます。 変数または引数の型と名前と共に、この値は、表示するための IDE に送信されます。  
  
## <a name="see-also"></a>参照  
 [式の評価インターフェイス](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)