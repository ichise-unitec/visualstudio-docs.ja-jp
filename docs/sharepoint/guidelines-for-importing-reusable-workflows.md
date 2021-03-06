---
title: "再利用可能なワークフローをインポートするためのガイドライン |Microsoft ドキュメント"
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
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- SharePoint development in Visual Studio, reusable workflows
- importing items [SharePoint development in Visual Studio]
- reusable workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a79f277c5cecead23def256e16b8fd69c64b2d36
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="guidelines-for-importing-reusable-workflows"></a>再利用可能なワークフローをインポートするためのガイドライン
  SharePoint Designer で作成された再利用可能なワークフローをインポートするには、再利用可能な SharePoint 2010 ワークフローのインポート プロジェクト テンプレートを使用[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]です。 このテンプレートをインポート、*宣言**ワークフロー* ([!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]-のみ) に変換します、*コード ワークフロー*、いずれかで強化するため、ワークフローであります。[!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]または[!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)]コード。 [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][チュートリアル: SharePoint Designer の再利用可能なワークフローを Visual Studio にインポート](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)です。  
  
 ただし、再利用可能な SharePoint 2010 ワークフローのインポート テンプレートは、ファーム ソリューションのみをインポートすることができます。 サンド ボックス ソリューションとして、ワークフローを展開する場合は、SharePoint 2010 ソリューション パッケージのインポート テンプレートを使用してインポートします。 ただし、これにより、ワークフローをコードに変換できないし、ように変更することはできません。  
  
## <a name="importing-reusable-workflows-by-using-the-import-reusable-workflow-template"></a>再利用可能なワークフロー テンプレートのインポートを使用して、再利用可能なワークフローのインポート  
 SharePoint の再利用可能な 2010 ワークフローのインポート テンプレートを使用して再利用可能なワークフローをインポートする場合は、実行またはと同じように、他のソリューションを変更[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]SharePoint ソリューションがいくつかのアイテムを手動で修正する必要があります。  
  
### <a name="importing-task-forms"></a>タスク フォームのインポート  
 再利用可能な SharePoint 2010 ワークフローのインポート プロジェクト テンプレートはすべての開始との関連付けフォームをインポートしますが、コード ワークフローのスキーマには、1 つのタスク フォームだけで許可されるため、1 つだけタスク フォームをインポートします。 元のワークフロー ソリューションから他のタスク フォームが入れられます、**インポートされたファイルの他の**フォルダー**ソリューション エクスプ ローラー**です。  
  
## <a name="importing-reusable-workflows-by-using-the-import-sharepoint-2010-solution-package-template"></a>SharePoint 2010 ソリューション パッケージ テンプレートのインポートを使用して、再利用可能なワークフローのインポート  
 SharePoint 2010 ソリューション パッケージのインポート テンプレートを使用して再利用可能なワークフローをインポートする場合は、次の点を考慮する必要があります。  
  
-   ワークフローをインポートすると、すぐに展開できで実行[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]で F5 キーを選択します。 ただし、インポートしたソリューション内のワークフローの任意のものを変更すると、展開して、ワークフローを実行する前に、プロジェクト内の要素を手動で修正するがあります。  
  
-   ワークフローは、宣言型であるためにコードを追加できません。 コード ワークフローにワークフローを変換する必要がありますにインポートする[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]再利用可能な SharePoint 2010 ワークフローのインポート テンプレートを使用しています。  
  
-   デザイン ビューで、ワークフロー デザイナー (.xoml) ファイルを編集できますが、お勧めソース ビューで、編集、ワークフロー デザイナーには、偽のエラーが表示されるためです。  
  
-   ワークフローでのデバッグは、宣言型のコンテンツに対しては機能しません。 ブレークポイントを設定、[!INCLUDE[wfd2](../sharepoint/includes/wfd2-md.md)]はヒットしません。  
  
## <a name="importing-globally-reusable-workflow-solutions"></a>グローバルに再利用可能なワークフロー ソリューションのインポート  
 再利用可能な SharePoint 2010 のワークフローのインポート テンプレートを使用してグローバルに再利用可能なワークフローをインポートすることはできません。 グローバルに再利用可能なワークフローをインポートするには、非グローバルに再利用可能なワークフローに変換する必要があるか、SharePoint 2010 ソリューション パッケージのインポート テンプレートを使用する必要があります。  
  
 ワークフローに変換するには、SharePoint Designer でグローバルに再利用可能なワークフローのコピーを作成 (ワークフローのショートカット メニューを開き、を選択して**コピーとして保存**)。 SharePoint の再利用可能な 2010 ワークフローのインポート テンプレートで新しい再利用可能なワークフローをインポート[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]です。  
  
 変更せず、グローバルに再利用可能なワークフローをインポートするには、SharePoint 2010 ソリューション パッケージのインポート テンプレートを使用します。 このメソッドを使用する場合、ワークフローはコード ワークフローには変換されないと、宣言型ワークフローのままです。  
  
## <a name="see-also"></a>参照  
 [既存の SharePoint サイトからアイテムをインポートします。](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [チュートリアル: SharePoint Designer の再利用可能なワークフローの Visual Studio へのインポート](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)  
  
  