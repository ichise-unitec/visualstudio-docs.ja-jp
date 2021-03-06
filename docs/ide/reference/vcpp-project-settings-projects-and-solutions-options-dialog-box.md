---
title: "[VC++ プロジェクトの設定][オプション] ダイアログ ボックス - [プロジェクトおよびソリューション] | Microsoft Docs"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.Projects.VCBuild
helpviewer_keywords:
- builds [Visual Studio], logs
- build process [C++]
- files [Visual Studio], built by C/C++ compiler
- file extensions, built by C or C++ compiler
- cl.exe compiler, file extensions
- extensions, files built by C or C++ compiler
- BuildLog.htm
ms.assetid: 56420efd-6a95-464e-b890-e2b38c48d66a
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7f24c1cd65d4669f326f866fbc04160d32daa4a1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="vc-project-settings-projects-and-solutions-options-dialog-box"></a>[VC++ プロジェクトの設定] ([オプション] ダイアログ ボックス - [プロジェクトおよびソリューション])
このダイアログ ボックスを使用すると、ログ、パフォーマンス、サポートするファイルの種類に関連する [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] のビルド設定とプロジェクト設定を定義できます。  
  
### <a name="to-access-this-dialog-box"></a>このダイアログ ボックスを表示するには  
  
1.  **[ツール]** メニューの **[オプション]**をクリックします。  
  
2.  **[プロジェクトおよびソリューション]** をクリックし、**[VC++ プロジェクトの設定]** をクリックします。  
 
## <a name="build-logging"></a>[ビルドのログ]  
 **はい**  
  ビルド ログ ファイルの生成をオンにします。 このオプションを指定すると、プロジェクトの中間ファイル ディレクトリに BuildLog.htm ファイルが生成されます。 新しくビルドを実行するたびに、以前の BuildLog.htm ファイルは上書きされます。  
  
 **No**  
  ビルド ログ ファイルの生成をオフにします。  

## <a name="show-environment-in-log"></a>[ログで環境を表示]  
 **はい**  
 ビルド ログ ファイルに環境変数をリストします。 このオプションを使用すると、[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] プロジェクトのビルド中に、すべての環境変数がビルド ログ ファイルにエコーされます。  
  
 **No**  
 ビルド ログ ファイルから環境変数を除外します。  

## <a name="build-timing"></a>[ビルド時間]  
 **はい**  
  ビルドの時間測定をオンにします。 このオプションをオンにすると、ビルドが完了するまでに要した時間がアウトプット ウィンドウに表示されます。 詳細については、「[[出力] ウィンドウ](../../ide/reference/output-window.md)」を参照してください。  
  
 **No**  
 ビルドの時間測定をオフにします。  
   
## <a name="maximum-concurrent-c-compilations"></a>[同時実行する C++ コンパイルの最大数]  
  C++ の並列コンパイルに使用する CPU コアの最大数を指定します。  
  
## <a name="extensions-to-include"></a>[含める拡張子]  
  プロジェクトに移植できるファイルのファイル名拡張子を指定します。  

## <a name="extensions-to-hide"></a>[表示しない拡張子]  
  **[すべてのファイルを表示]** が有効になっているときに**ソリューション エクスプローラー**に表示されないファイルのファイル名拡張子を指定します。  

 ## <a name="build-customization-search-path"></a>[ビルドのカスタマイズの検索パス]  
  .rules ファイルを含むディレクトリの一覧を指定します。これは、プロジェクトのビルド ルールを定義するときに役立ちます。  

# <a name="solution-explorer-mode"></a>[ソリューション エクスプローラー モード]  
 **[プロジェクト内のファイルのみ表示]**  
  プロジェクト内のファイルだけが表示されるように、**ソリューション エクスプローラー**を構成します。  
  
 **[すべてのファイルを表示]**  
  プロジェクト内のファイルとディスク上のファイルがプロジェクト フォルダー内に表示されるように、**ソリューション エクスプローラー**を構成します。  

## <a name="enable-project-caching"></a>プロジェクトのキャッシュを有効にする
**はい**  
Visual Studio がプロジェクト データをキャッシュすることで、次にプロジェクトを開いたときにプロジェクト ファイルから再計算せずにキャッシュされたデータを読み込めるようになります。 キャッシュされたデータを使用すると、プロジェクトの読み込み時間を大幅に短縮できます。   

**No**  
キャッシュされたプロジェクト データを使用しません。 プロジェクトが読み込まれるたびにプロジェクト ファイルを解析します。

## <a name="see-also"></a>関連項目  
 [C/C++ プログラムのビルド](/cpp/build/building-c-cpp-programs)   
 [C/C++ ビルドのリファレンス](/cpp/build/reference/c-cpp-building-reference)