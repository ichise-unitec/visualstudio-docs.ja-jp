---
title: "方法: SharePoint プロジェクトに既存の BDC モデル ファイルを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.BDC.ImportDialog
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], import a model
- Business Data Connectivity service [SharePoint development in Visual Studio], reuse a model
- BDC [SharePoint development in Visual Studio], import a model
- BDC [SharePoint development in Visual Studio], remove a model
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: f5f13377211a6b8a7a2035d85e1423be9d2bbb72
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project"></a>方法: 既存の BDC モデル ファイルを SharePoint プロジェクトに追加する
  パッケージをカスタマイズし、Visual Studio を使用してモデル ファイル (.bdcm) を SharePoint ファームのプロジェクトに追加することによって、ビジネス データ接続 (BDC) モデルを再配置できます。 詳細については、次を参照してください。[ビジネス データ接続モデルを作成する](../sharepoint/creating-a-business-data-connectivity-model.md)です。  
  
### <a name="to-add-a-bdc-model-file-to-a-sharepoint-project"></a>BDC モデル ファイルを SharePoint プロジェクトに追加するには  
  
1.  **ソリューション エクスプ ローラー**、SharePoint プロジェクトのフォルダーを選択します。  
  
2.  メニュー バーで、次のように選択します。**プロジェクト**、**既存項目の追加**です。  
  
3.  **既存項目の追加** ダイアログ ボックスで、プロジェクトに追加する、ファイルを選択し、選択するモデルの定義ファイルの場所を参照、**追加**ボタンをクリックします。  
  
     モデルが定義されていない場合、 *.NET アセンブリの種類の基幹業務 (LOB) システム*、**追加の .NET アセンブリの LobSystem**  ダイアログ ボックスが表示されます。  
  
4.  ダイアログ ボックスが表示されている場合、次の手順のいずれかを実行します。  
  
    -   カスタム コードを記述し、インポートされたモデルのメタデータを定義するを選択して、デザイナーを使用する場合、 **[はい]**ボタンをクリックし、システムの名前を選択し、 **OK**ボタンをクリックします。  
  
    -   それ以外の場合、選択、**なし**ボタンをクリックしを選択し、 **OK**ボタンをクリックします。  
  
     **ビジネス データ接続モデル**項目は、プロジェクトに追加します。  
  
## <a name="see-also"></a>参照  
 [ビジネス データ接続モデルを作成します。](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [方法: BDC モデルを作成](../sharepoint/how-to-create-a-bdc-model.md)   
 [方法: リソース ファイルを使用して、ローカライズされた名前、プロパティ、およびアクセス許可](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [方法: BDC 機能にカスタム アセンブリを含める](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [SharePoint へのビジネス データの統合](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  