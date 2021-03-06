---
title: "コンテキスト メニュー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 69048a35514ac35556e04ed5266ff58b21b31e0d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="context-menus"></a>コンテキスト メニュー
コンテキスト メニューは、ユーザーがクライアント領域のアクティブな領域で右クリックしたときに表示し、マウスの右ボタンが離されたときにクリアします。  
  
## <a name="editor-context-menus"></a>エディター コンテキスト メニュー  
 インターセプトして`ECMD_SHOWCONTEXTMENU`、言語サービスは、エディターに表示されるコンテキスト メニューを制御できます。 表示するには、独自のコンテキスト メニューに渡されるときにこのコマンドを処理して<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>を呼び出して<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>です。 このコマンドを処理しない場合は、エディターの提供される標準のコンテキスト メニューが表示されます。 マーカーあたりごとに、コンテキスト メニューの内容を制御することもできます。 詳細については、次を参照してください。[レガシ API でテキスト マーカーを使用して](../extensibility/using-text-markers-with-the-legacy-api.md)と[レガシ言語サービス コマンドの傍受](../extensibility/internals/intercepting-legacy-language-service-commands.md)です。  
  
## <a name="see-also"></a>参照  
 [レガシ言語サービスの開発](../extensibility/internals/developing-a-legacy-language-service.md)   
 [メニューとコマンドの拡張](../extensibility/extending-menus-and-commands.md)