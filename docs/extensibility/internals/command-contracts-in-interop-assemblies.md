---
title: "相互運用機能アセンブリ内のコントラクトをコマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d32a49d780f6ae7929f1442ee70a8085724ca6e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="command-contracts-in-interop-assemblies"></a>相互運用機能アセンブリ内のコマンドのコントラクト
使ってコマンドを処理するための基本的なコントラクト、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>インターフェイスは、環境が呼び出す、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>メソッドはサポートされている場合と、コマンドはサポートされているかどうかを判断する、その状態とテキストを判別します。 次に、環境の呼び出し、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>コマンドを実行するメソッド。  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>メソッドの処理は、すべてのコマンドは同じです。 それ以降の通信は (たとえば、ドロップダウン リストの場合) に必要な場合、呼び出すことで管理されて、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>適切なパラメーターを持つメソッドです。 これらのパラメーターの解釈は、指定されたコマンドによって異なります。  
  
 コマンド ターゲットでは、出力パラメーターの値が返された場合、呼び出し元は常が割り当てられているすべてのリソースを解放します。 このパラメーターは、バリアントでは、リソースを解放バリアントをクリアします。  
  
 コマンドが、階層ウィンドウ内で動作する必要がの場合、<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>インターフェイスを使用する必要があります。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>インターフェイスのようなメソッドと類似のコントラクトには:<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A>と<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>です。  
  
## <a name="see-also"></a>参照  
 [Vspackage がユーザー インターフェイス要素を追加する方法](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Vspackage でルーティング コマンド](../../extensibility/internals/command-routing-in-vspackages.md)   
 [実装](../../extensibility/internals/command-implementation.md)