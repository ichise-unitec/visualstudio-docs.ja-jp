---
title: "方法: エンティティ間の関連付けを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AssociationGroupTool
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associations between entities
- BDC [SharePoint development in Visual Studio], associations between entities
- Business Data Connectivity service [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associate external content types
- Business Data Connectivity service [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], associate external content types
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 49b4d68a8d957462954c998d96e9309944cdb9f5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-an-association-between-entities"></a>方法: エンティティ間に関連付けを作成する
  関連付けを作成することで、ビジネス データ接続 (BDC) モデルのエンティティ間のリレーションシップを定義することができます。 Visual Studio では、各アソシエーションに関する情報をモデルのコンシューマーに提供するメソッドを生成します。 これらのメソッドは、SharePoint web パーツ、リスト、またはユーザー インターフェイス (UI) でデータ間の関係を表示するカスタム アプリケーションで使用できます。  
  
 BDC デザイナーでの関連付けの 2 つの種類を作成することができます。 外部キーに基づくアソシエーションとキーを使用しない外部のアソシエーション。 詳細については、次を参照してください。[アソシエーション間でエンティティを作成する](../sharepoint/creating-an-association-between-entities.md)です。  
  
### <a name="to-create-an-association-between-entities"></a>エンティティ間の関連付けを作成するには  
  
1.  **BusinessDataConnectivity**のタブ、**ツールボックス**、選択、**アソシエーション**項目。  
  
2.  BDC デザイナーで、ソース エンティティを選択し、転送先エンティティを選択します。  
  
     **関連付けエディター**が表示されます。  
  
3.  外部キーに基づく関連付けを作成する場合は、選択、**外部キーの関連付け**チェック ボックスをオンします。  
  
    1.  **ソース ID**の列、**識別子のマッピング**テーブルに表示される各一致する型記述子の横にある識別子を選択、**フィールド**列です。  
  
         など、**ソース ID**列で、選択`ContactID` の横に、`ReadList.salesOrderList.SalesOrderList.SalesOrder.ContactID`記述子を入力し、`ReadItem.salesOrder.SalesOrder.ContactID`記述子を入力します。  
  
4.  外部キーを使用しない関連付けを作成する場合は、オフ、**外部キーの関連付け**チェック ボックスをオンします。  
  
5.  **[OK]** を選択します。  
  
6.  BDC デザイナーでは、ソース エンティティと転送先エンティティの間の関連付けを表す線が表示されます。  
  
     Visual Studio では、転送先エンティティのサービス クラスとソース エンティティのサービス クラスに、アソシエーション ナビゲーター メソッドを追加します。 アソシエーションのナビゲーション方法の詳細については、次を参照してください。[サポートされている操作](http://go.microsoft.com/fwlink/?LinkId=169286)です。  
  
7.  ソース エンティティの関連付けナビゲーター メソッドでは、移行先のエンティティのコレクションを返すコードを追加します。  
  
8.  転送先エンティティの関連付けナビゲーター メソッドでは、関連するソース エンティティを返すコードを追加します。  
  
     ナビゲーターの関連付けの方法の例については、次を参照してください。[アソシエーション間でエンティティを作成する](../sharepoint/creating-an-association-between-entities.md)です。  
  
## <a name="see-also"></a>参照  
 [エンティティ間の関連付けを作成します。](../sharepoint/creating-an-association-between-entities.md)   
 [ビジネス データ接続モデルの設計](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [方法: Finder メソッドを追加](../sharepoint/how-to-add-a-finder-method.md)   
 [方法: Specificfinder メソッドを追加します。](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [方法: Creator メソッドを追加](../sharepoint/how-to-add-a-creator-method.md)   
 [方法: Deleter メソッドを追加](../sharepoint/how-to-add-a-deleter-method.md)   
 [方法: Updater メソッドを追加](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC モデルのデザイン ツールの概要](../sharepoint/bdc-model-design-tools-overview.md)   
 [方法: メソッドにパラメーターを追加](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [方法: メソッド インスタンスの定義](../sharepoint/how-to-define-a-method-instance.md)   
 [方法: パラメーターの型記述子を定義します。](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [チュートリアル: ビジネス データを使用した SharePoint での外部リストの作成](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)  
  
  