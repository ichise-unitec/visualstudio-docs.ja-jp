---
title: "方法: 展開し、SharePoint ソリューションをローカル SharePoint サイトにパブリッシュ |Microsoft ドキュメント"
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
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: b5b3ab297612ec48027af8d4eb74956d1d255443
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site"></a>方法: SharePoint ソリューションをローカルの SharePoint サイトに配置および発行する
  展開したり、開発用コンピューター上のローカル SharePoint サーバーに SharePoint ソリューションを発行することができます。 展開プロセスは、SharePoint サーバーに .wsp ファイルをコピー、ソリューションをインストールし、機能をアクティブにし、します。 発行プロセスは、SharePoint サーバーに .wsp ファイルをコピーおよびインストールのみです。 SharePoint で有効にすることがアクティブ化する必要があります手動でします。  
  
## <a name="to-deploy-a-sharepoint-solution-to-the-local-sharepoint-server"></a>ローカルの SharePoint サーバーに SharePoint ソリューションを展開するには  
  
1.  **ソリューション エクスプ ローラー**、配置するプロジェクトを選択します。  
  
2.  メニュー バーで、次のように選択します。**ビルド**、**ソリューションの配置**です。  
  
     .Wsp ファイルが作成され、ローカルの SharePoint サーバーにインストールします。 また、機能がアクティブにします。  
  
## <a name="to-publish-a-sharepoint-solution-to-a-local-sharepoint-server"></a>SharePoint ソリューションをローカル SharePoint サーバーに発行するには  
  
1.  **ソリューション エクスプ ローラー**、ショートカット メニューを開き、SharePoint プロジェクトを発行し、選択するを**発行**です。  
  
2.  **発行** ダイアログ ボックスで、選択、**ファイル システムに公開**オプション ボタンをクリックします。  
  
3.  **ターゲットの場所**テキスト ボックスは、ローカル パスを入力し、、**発行**ボタンをクリックします。  
  
     Visual Studio で発行の進行状況が表示される**出力**ウィンドウです。 プロセスが完了したら、ソリューション (.wsp) ファイルはローカル SharePoint サーバーにインストールされます。 ただし、その必要がありますまだアクティブに SharePoint で使用します。 ソリューション ファイルが既に存在する場合、エラーが発生し、既存のファイルを上書きするかどうかを確認します。 パッケージをアップグレードする方法についてでリモート パッケージのアップグレードに関するセクションを参照して[する方法: 配置、発行、およびリモート サーバー上の SharePoint ソリューションのアップグレード](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)です。  
  
## <a name="see-also"></a>参照  
 [方法: 配置、発行、およびリモート サーバー上で SharePoint ソリューションのアップグレード](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)   
 [SharePoint ソリューション パッケージの作成](../sharepoint/creating-sharepoint-solution-packages.md)   
 [方法: SharePoint ソリューション パッケージをカスタマイズします。](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [方法: パッケージ デザイナーを使用してパッケージのフィーチャーおよび項目を追加および削除する](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  