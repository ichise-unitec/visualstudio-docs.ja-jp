---
title: "方法: ワークフロー コンソール アプリケーションを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
caps.latest.revision: "16"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: fcadbe113e92c761559161bdd8a7eba6e95937d3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-workflow-console-application"></a>ワークフロー コンソール アプリケーションを作成する方法
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] を利用して、無人または有人のプロセスの実行のためのワークフローを作成できます。 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]は、このようなワークフローを作成するためのデザイン サーフェイスを備えています。 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]は、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 内からワークフローを作成する場合に使用でき、デザイナーを再ホストする他のアプリケーションに統合することもできます。  
  
 このトピックでは、[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] の[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]を使用して、コンソール アプリケーションのワークフローを作成する方法について説明します。  
  
### <a name="to-create-a-workflow-console-application"></a>ワークフロー コンソール アプリケーションを作成するには  
  
1.  [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] を起動します。  
  
2.  **ファイル**] メニューのをポイント**新規**、し、[**プロジェクト.**.  
  
     **[新しいプロジェクト]** ダイアログ ボックスが表示されます。  
  
3.  **インストールされたテンプレート**ペインで、**ワークフロー**いずれかから、 **Visual c#**または**Visual Basic**に応じてグループの場合、言語の設定。  
  
4.  中央のペインで選択**ワークフロー コンソール アプリケーション**です。  
  
5.  **名前**を識別しやすくようにプロジェクトのわかりやすい名前を入力します。  
  
6.  **場所**ボックスで、プロジェクトを保存ディレクトリを入力**参照**まで移動します。  
  
7.  **ソリューション**ボックスで、新しいソリューションの名前を入力します。 をクリックして**OK**アプリケーションを作成します。  
  
    > [!NOTE]
    >  ワークフロー コンソール アプリケーションを既存のソリューションに追加する場合でそのソリューションを開きます[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]で、ソリューションを右クリックして**ソリューション エクスプ ローラー**を選択して**追加**、し**新しいプロジェクト.**を開くには、**新しいプロジェクト** ダイアログ ボックス。 上記の手順を実行します。  
  
8.  プロジェクト テンプレートで XAML のワークフロー定義が作成され、コンソール アプリケーション定義がソース コードに記述されます。 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]で、作成したワークフロー用のキャンバスが開かれて表示されます。  
  
9. ワークフローを作成するには、アクティビティから、またはその他のワークフロー項目をドラッグ、**ツールボックス**で、ワークフロー デザイン サーフェイスにします。  
  
## <a name="see-also"></a>参照  
 [ワークフロー プロジェクトの作成](../workflow-designer/creating-a-workflow-project.md)