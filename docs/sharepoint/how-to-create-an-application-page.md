---
title: "方法: アプリケーション ページを作成 |Microsoft ドキュメント"
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
- VB
- CSharp
helpviewer_keywords:
- application pages [SharePoint development in Visual Studio], adding
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9429f2834997ce5ad2c3359fb04c164995dd2e12
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-an-application-page"></a>方法: アプリケーション ページを作成する
  1 つまたは複数の SharePoint サイトの ASP.NET web ページを作成することができます。 SharePoint では、これらのページはアプリケーション ページと呼ばれます。 サイトのページとは異なり、アプリケーション ページには、ページの背面に実行されるコードが含まれています。 詳細については、次を参照してください。 [for SharePoint アプリケーション ページを作成する](../sharepoint/creating-application-pages-for-sharepoint.md)です。  
  
### <a name="to-create-an-application-page"></a>アプリケーション ページを作成するには  
  
1.  Visual Studio で、SharePoint プロジェクトを開くか作成します。  
  
     詳細については、次を参照してください。 [SharePoint プロジェクトとプロジェクト項目テンプレート](../sharepoint/sharepoint-project-and-project-item-templates.md)です。  
  
2.  **ソリューション エクスプローラー**で、プロジェクト ノードを選択します。  
  
3.  メニュー バーで、次のように選択します。**プロジェクト**、**新しい項目の追加**です。  
  
4.  **新しい項目の追加** ダイアログ ボックスで、展開、 **SharePoint**  ノードを選択し、 **2010**項目。  
  
5.  SharePoint テンプレートの一覧で選択**アプリケーション ページ**です。  
  
6.  **名前**ボックス、アプリケーション ページの名前を指定し、選択、**追加**ボタンをクリックします。  
  
     複数のフォルダーとファイルがプロジェクトに追加されます。 これらのファイルに関する詳細については、次を参照してください。 [for SharePoint アプリケーション ページを作成する](../sharepoint/creating-application-pages-for-sharepoint.md)です。  
  
     **ソース**Visual Web Developer デザイナーで、ASP.NET ページのファイルのビューが表示されます。 コントロールを追加して、ページをデザインすることができます、**ツールボックス**コンテンツ プレース ホルダーに配置することです。 詳細については、次を参照してください。[ソース ビュー、Web ページ デザイナー](http://msdn.microsoft.com/en-us/5911396b-fe51-4150-9ff1-b085f812862f)です。  
  
7.  コントロールのイベントを処理する場合は、アプリケーション ページのコード ファイルにコードを追加します。  
  
     コード ファイルでは、ASP.NET ページのファイルのノードを展開する場合に表示されます、.cs または .vb ファイルの拡張子は、プロジェクトの言語に応じて。 アプリケーション ページを作成する方法のエンド ツー エンド例は、次を参照してください。[チュートリアル: SharePoint アプリケーション ページを作成する](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)です。  
  
## <a name="see-also"></a>参照  
 [For SharePoint アプリケーション ページの作成](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [チュートリアル: SharePoint アプリケーション ページの作成](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)  
  
  