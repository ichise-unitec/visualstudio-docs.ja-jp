---
title: "方法: ワークフロー内のブレークポイントを設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e41b21c9-c061-4358-8e2f-eb5e412864a8
caps.latest.revision: "10"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 4c9a3124ddefc892207ccc821b80056baab14166
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-breakpoints-in-workflows"></a>方法 : ワークフロー内のブレークポイントを設定する
[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]を使用すると、Visual Basic コードまたは C# コードを使用する場合と同じように、グラフィカル ワークフローにブレークポイントを設定できます。 設定したそれぞれのブレークポイントで、ワークフローの実行が停止します。  
  
 ブレークポイントが 3 つの状態:*保留*、*バインド*、および*エラー*です。 ブレークポイントは、設定時には "保留" になり、穴のない赤いアイコンで表示されます。 特定の種類のワークフローがランタイムによって読み込まれると、ブレークポイントの状態は "バインド" になります。 不適切な形式のブレークポイントを指定した場合 (アクティビティ名が無効など) は、エラー ウィンドウが表示されます。 ブレークポイントはブレークポイント ウィンドウに追加されますが、小さな x 印が付きます。  
  
> [!NOTE]
>  呼び出されるワークフローに対してブレークポイントを設定することはできません。  
  
> [!WARNING]
>  オプションを選択することを確認してください**[マイ コードのみ (マネージのみ)**から、**ツール**、**オプション**、**デバッグ**する前に] メニュー。デバッグします。 別のシーケンス内で入れ子になった 2 つのシーケンスがあり、最初の内部シーケンスにブレークポイントを設定する場合、以下のキーを押して**F11**場合、2 つ目の内部シーケンスにステップインしません、 **マイ コードのみ (マネージのみ)**オプションが選択されていません。  
  
> [!WARNING]
>  XAML ファイルのプロパティへの完全パスが正確でない場合、ワークフロー内のブレークポイントにヒットしません。XAML ファイルへの完全パスは、プロジェクトやソリューションを別のフォルダーや別のコンピューターへ移動すると正確ではなくなります。Ctrl キーを押しながら S キーを押すと、完全パスのプロパティが保存および更新されます。  
  
### <a name="to-set-a-breakpoint-on-an-activity-in-the-design-view"></a>デザイン ビューでアクティビティにブレークポイントを設定するには  
  
1.  デバッガーを中断する位置にあるアクティビティを選択します。  
  
2.  **デバッグ**メニューの **ブレークポイントの切り替え**です。 アクティビティの左上端に赤色のアイコンが表示されます。  
  
     または、ショートカット キーも**F9**キーをアクティビティを右クリックし、選択するか、アクティビティを選択すると**ブレークポイント**し**ブレークポイントの挿入**、コンテキスト メニュー。  
  
## <a name="see-also"></a>参照  
 [方法: ワークフロー デバッガーを呼び出す](../workflow-designer/how-to-invoke-the-workflow-debugger.md)   
 [ワークフロー デザイナーにワークフローのデバッグ](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)   
 [方法: ワークフロー デザイナーを使用して XAML をデバッグする](../workflow-designer/how-to-debug-xaml-with-the-workflow-designer.md)