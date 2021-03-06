---
title: "依存関係 &#39;dependency2&#39; の依存関係 &#39;dependency1&#39; はアセンブリではありません。 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.notcomplusassembly2"
ms.assetid: e3b96601-458e-40de-81ea-ddcae9b42996
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 依存関係 &#39;dependency2&#39; の依存関係 &#39;dependency1&#39; はアセンブリではありません。
プロジェクト システムが、アセンブリ \(dependency2\) の特定の依存関係 \(dependency1\) は .NET アセンブリではないと判別しました。  
  
 **このエラーを解決するには**  
  
-   アセンブリが [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] または .NET Framework に組み込まれていた場合は、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] を再インストールします。  
  
     または  
  
-   適切なサード パーティ製コントロールを再インストールします。  
  
     このエラーがプロジェクトのビルドを妨げることはありません。 ただし、実行時エラーが発生する場合があります。  
  
## 参照  
 [壊れた参照のトラブルシューティング](../ide/troubleshooting-broken-references.md)   
 [NIB 方法: &#91;参照の追加&#93; ダイアログ ボックスを使用して参照を追加または削除する](http://msdn.microsoft.com/ja-jp/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Assemblies in the Common Language Runtime](http://msdn.microsoft.com/ja-jp/33a0bc6a-6bb3-44c7-ada7-4a046e8c0945)