---
title: "テストの領域 8: プラグインの切り替え |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], switching plug-ins
- source control plug-ins, switching
ms.assetid: 01370792-b5da-4e46-9ce2-7dd326587141
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9f6a518d618b3a98ec85cbbe015d3b2c5fc7a710
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="test-area-8-plug-in-switching"></a>テストの領域 8: プラグインの切り替え
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]統合開発環境 (IDE) では、ユーザー インターフェイス (UI) を持つ、現在のソース管理プラグインを変更します。 このテストの領域は、ソリューションのソース管理を使用するプラグインを選定するプロセスのテスト_ケースを提供します。  
  
## <a name="command-menu-access"></a>コマンド メニューへのアクセス  
 次[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]統合開発環境] メニューの [パスは、テストの場合に使用されます。  
  
-   現在のソース管理プラグイン:**ツール** -> **オプション** -> **ソース管理** -> **プラグインの選択**.  
  
-   ソースの変更管理のバインディング:**ファイル** -> **ソース管理** -> **ソース管理の変更**しています.  
  
## <a name="common-expected-behavior"></a>共通の想定される動作  
 ソース管理ソリューションのプラグインを変更するは、Visual Studio を終了するか、またはソリューションを再読み込みせず可能です。 さらに、現在のソース管理プラグインは自動的にそのソリューションが読み込まれるときに、ソリューションで使用される 1 つに変更します。  
  
## <a name="test-cases"></a>テスト ケース  
 プラグインの切り替えテスト区分の特定のテスト_ケースを次に示します。  
  
### <a name="case-8a-automatic-change"></a>8 a の場合: 自動変更  
  
#### <a name="expected-behavior"></a>想定される動作  
 ユーザーには、ソース管理下にあるソリューションが読み込まれると、ソリューションが自動的に読み込まれ、適切なソース管理プラグインは、現在選択されています。  
  
|アクション|テスト ステップ|期待される結果を確認するには|  
|------------|----------------|--------------------------------|  
|自動のソース管理プラグインの変更|1.最新のテスト プラグインの選択 (**ツール** -> **オプション** -> **ソース管理** -> **プラグイン選択範囲**)。<br />2.新しいプロジェクトを作成します。<br />3.ソリューションをソース管理に追加します。<br />4.別のプラグインを選択 (たとえば、 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)])。<br />5.アンロード ソリューション プロンプトに同意します。<br />6.ディスクからソリューションを再度開きます。|ソリューションが開かれます。<br /><br /> テスト対象プラグインは、現在のソース管理プラグインです。|  
  
### <a name="case-8b-solution-based-change"></a>Case 8b: ソリューションに基づく変更  
  
#### <a name="expected-behavior"></a>想定される動作  
 ソリューションには、その関連付けられているソース管理プラグイン変更されたことができます。  
  
|アクション|テスト ステップ|期待される結果を確認するには|  
|------------|----------------|--------------------------------|  
|ソリューションのプラグインの変更|1.最新のテスト プラグインの選択 (**ツール** -> **オプション** -> **ソース管理** -> **プラグイン選択範囲**)。<br />2.新しいプロジェクトとソリューションを作成します。<br />3.ソリューションをソース管理に追加します。<br />4.ソース管理からソリューションをバインド解除 (を使用して、**ソース管理の変更** ダイアログ ボックス)。<br />5.別のプラグインを選択 (たとえば、 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)])。<br />6.アンロードされた場合は、ディスクからソリューションを再読み込みされます。<br />7.ソリューションをソース管理に追加します。<br />8.ソース管理からソリューションをバインド解除 (を使用して**ソース管理の変更** ダイアログ ボックス)。<br />9.もう一度テスト プラグインを選択します。<br />10.アンロードされた場合は、ディスクからソリューションを再読み込みされます。<br />11.元の場所に、ソリューションをバインド (を使用して、**ソース管理の変更** ダイアログ ボックス)。|ソリューションをソース管理に使用して追加された、選択したプラグインします。|  
  
## <a name="see-also"></a>参照  
 [ソース管理プラグイン向けのテスト ガイド](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)