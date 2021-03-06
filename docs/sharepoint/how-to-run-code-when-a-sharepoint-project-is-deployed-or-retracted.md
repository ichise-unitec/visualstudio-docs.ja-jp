---
title: "方法: 実行コードと、SharePoint プロジェクトの配置または取り消し時 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 74eb6585be1b90da906141db4ef89c0705efa0b9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted"></a>方法: SharePoint プロジェクトの配置時または取り消し時にコードを実行する
  SharePoint プロジェクトの配置時または取り消し時に、その他のタスクを実行する場合は、Visual Studio によって生成されるイベントを処理することができます。 詳細については、次を参照してください。[を拡張する SharePoint のパッケージ化と配置](../sharepoint/extending-sharepoint-packaging-and-deployment.md)です。  
  
### <a name="to-run-code-when-a-sharepoint-project-is-deployed-or-retracted"></a>SharePoint プロジェクトのコードを実行するには、配置時または取り消し  
  
1.  プロジェクト項目の拡張機能、プロジェクトの拡張機能、または新しいプロジェクト項目の種類の定義を作成します。 詳細については、次のトピックを参照してください。  
  
    -   [方法: SharePoint プロジェクト項目の拡張機能を作成する](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [方法: SharePoint プロジェクトの拡張機能を作成する](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [方法: SharePoint プロジェクト項目の種類を定義する](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  アクセス、拡張機能で、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService>オブジェクト。 詳細については、次を参照してください。[する方法: SharePoint プロジェクト サービスを取得](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)です。  
  
3.  処理、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentStarted>と<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentCompleted>プロジェクト サービスのイベントです。  
  
4.  イベントのハンドラーを使用して、<xref:Microsoft.VisualStudio.SharePoint.DeploymentEventArgs>パラメーターを現在の展開セッションに関する情報を取得します。 たとえば、展開の現在のセッションでは、プロジェクトとされているかどうかを判断できます配置時または取り消しできます。  
  
 次のコード例は、処理する方法を示します、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentStarted>と<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentCompleted>プロジェクトの拡張機能内のイベントです。 この拡張機能に追加のメッセージを書き込みます、**出力**ウィンドウの展開が開始し、SharePoint プロジェクトの完了時にします。  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#12](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handleprojectdeploymentevents.cs#12)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#12](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handleprojectdeploymentevents.vb#12)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例では、次のアセンブリへの参照が必要です。  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>拡張機能の配置  
 拡張機能を展開するには、作成、[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]アセンブリおよびその他の拡張機能を配布するファイルの拡張機能 (VSIX) にパッケージ化します。 詳細については、次を参照してください。 [Visual Studio での SharePoint ツールの拡張機能の配置](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)です。  
  
## <a name="see-also"></a>参照  
 [SharePoint の拡張のパッケージ化と配置](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [方法: 配置手順の実行時にコードを実行する](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)  
  
  