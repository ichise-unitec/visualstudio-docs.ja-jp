---
title: "方法: 組み込みの装飾が可能な項目を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 545d5fa19182678ec1610fa7b689332e272f9962
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-built-in-colorable-items"></a>方法: 組み込みの装飾が可能な項目を使用して
組み込みの装飾が可能な項目を使用する前にする必要がありますまずシグナルを送信、統合開発環境 (IDE) 独自カスタム装飾が可能な項目をこの例で提供していない<xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>オブジェクト。 これを行う言語サービスのレジストリ エントリを設定します。  
  
### <a name="to-use-built-in-colorable-items"></a>組み込みの装飾が可能な項目を使用するには  
  
1.  HKEY_LOCAL_MACHINE\VisualStudio \\*X.Y*\Languages\Language Services\\*言語名*ここで、 *X.Y* のバージョン[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]と*言語名*名前と呼ばれる、DWORD レジストリ エントリの値を作成、使用する言語の`RequestStockColors`します。  
  
2.  設定、`RequestStockColors`レジストリ エントリの値を 1 にします。  
  
     レジストリ エントリを colorizer を作成した後<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>方法は、のメンバーを使用することができます、<xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS>エディターで使用する色の属性の配列を埋めるために列挙します。  
  
    > [!NOTE]
    >  カスタムの装飾が可能な項目を指定する場合は、このレジストリ エントリを設定しないでください。 詳細については、次を参照してください。[カスタムの装飾が可能なアイテム](../../extensibility/internals/custom-colorable-items.md)です。  
  
## <a name="see-also"></a>参照  
 [カスタム エディターの構文の色分け](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [従来の言語サービスの構文の色分け](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [構文の色分けを実装します。](../../extensibility/internals/implementing-syntax-coloring.md)   
 [カスタムの装飾が可能な項目](../../extensibility/internals/custom-colorable-items.md)   
 [レガシ言語サービスを登録します。](../../extensibility/internals/registering-a-legacy-language-service2.md)