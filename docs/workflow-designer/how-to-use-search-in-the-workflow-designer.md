---
title: "方法: ワークフロー デザイナーで検索を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
caps.latest.revision: "3"
ms.author: sdanie
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 20e4cca7723a47b5735301c54a67029f0f956c49
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>ワークフロー デザイナーで検索を使用する方法
より大規模で複雑なワーク フローの作成を容易にするために、ワークフロー デザイナー内で検索を使用して、キーワードで項目を検索できます。 デザイナーでは、置換はサポートされないことに注意してください。 検索では、デザイナーで次の項目が検索されます。  
  
## <a name="quick-find"></a>クイック検索  
 クイック検索はデザイナー内で次の項目を検索します。  
  
-   <xref:System.Activities.Activity> オブジェクト、<xref:System.Activities.Statements.FlowNode> オブジェクト、<xref:System.Activities.Statements.State> オブジェクト、遷移、およびその他のカスタム フロー制御項目のプロパティ。  
  
-   変数  
  
-   引数  
  
-   式  
  
#### <a name="using-quick-find"></a>クイック検索の使用  
  
1.  ワークフロー デザイナーを開いた状態で、キーを押します**Ctrl + F**、または選択**編集**、**検索し、置換**、**クイック検索**です。  
  
2.  検索用語を入力してください、**検索** テキスト ボックス をクリック**次を検索**です。  
  
3.  検索用語が現在のワークフローで検索されます。 アクティビティの表示名がデザイナーで見つかったことを示すスクリーンショットを次に示します。  
  
     ![検索結果をワークフロー デザイナーで](../workflow-designer/media/designersearch.png "DesignerSearch")  
  
## <a name="find-in-files"></a>フォルダーを指定して検索する  
 [フォルダーを指定して検索] を使用すると、XAML ファイルなどのワークフロー ファイル内で文字列が検索されます。  
  
#### <a name="using-find-in-files"></a>フォルダーを指定して検索の使用  
  
1.  Visual Studio で、キーを押して**ctrl キーと shift キーを押しながら F**、または選択**編集**、**検索し、置換**、**ファイル内の検索**  
  
2.  検索項目を入力してください、**検索** テキスト ボックスをクリック**すべて検索**  
  
3.  検索結果に表示される、 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]**の検索結果**ビュー。 結果の項目をダブルクリックすると、ワークフロー デザイナーで一致する項目を含むアクティビティに移動します。