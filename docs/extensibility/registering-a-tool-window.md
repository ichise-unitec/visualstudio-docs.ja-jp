---
title: "ツール ウィンドウを登録する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 908a850b1e86ffc2e8337096266849efeaf04a51
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="registering-a-tool-window"></a>ツール ウィンドウを登録します。
使用して、ツール ウィンドウを登録する<xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute>と<xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>例  
  
```csharp  
  
      [ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 上記のコードで、 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> persistedwindowpane がおよび DynamicWindowPane ツール ウィンドウを Visual Studio に登録します。 永続化されたツール ウィンドウをドッキングされでタブ**ソリューション エクスプ ローラー**、およびダイナミック ウィンドウで、既定の開始位置とサイズが与えられます。 動的なウィンドウが作成された一時的なものでスタートアップ時に作成されていないことを示します。 これは、システム レジストリ内の ToolWindows キー DontForceCreate 値を書き込みます。 詳細については、次を参照してください。[ツール ウィンドウの表示構成](../extensibility/tool-window-display-configuration.md)です。