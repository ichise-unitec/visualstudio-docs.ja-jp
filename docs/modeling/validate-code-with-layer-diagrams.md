---
title: "依存関係のダイアグラムのコードの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, validating
- validation, dependency diagrams
- validation, code
- code exploration, validating
- architecture, validating
- Visual Studio Ultimate, validating code
- validation, architecture
- validation, dependencies
- MSBuild, tasks
- MSBuild, dependency diagrams
- MSBuild, validating code
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 02c983fb7cd797be377f8821c46b2d7dc38450f9
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2018
---
# <a name="validate-code-with-dependency-diagrams"></a>依存関係のダイアグラムのコードを検証します。

**最新のニュース**: を参照してください[このブログの投稿](https://blogs.msdn.microsoft.com/visualstudioalm/2016/11/30/live-dependency-validation-in-visual-studio-2017/)です。

[ビデオ: リアルタイムで、アーキテクチャの依存関係を検証します。](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4) 

## <a name="why-use-dependency-diagrams"></a>依存関係図を使用する理由

コードが設計と競合しないことを確認するには、Visual Studio での依存関係ダイアグラムのコードを検証します。 これが次の点で役立つ場合があります。  
  
-   依存関係ダイアグラムで、コード内の依存関係との依存関係の競合を検索します。  
  
-   提案された変更によって影響を受ける可能性がある依存関係を見つける。  
  
     たとえば、潜在的なアーキテクチャの変更を表示し、影響を受ける依存関係を表示するコードを検証するには、依存関係ダイアグラムを編集できます。  
  
-   コードを別の設計にリファクターまたは移行する。  
  
     コードを別のアーキテクチャに移動したときに作業が必要なコード、または依存関係を見つけます。  
  
 **必要条件**  
  
-   Visual Studio  
  
-   Team Foundation ビルド サーバーにインストールされた Visual Studio (Team Foundation ビルドを使用してコードを自動的に検証するために必要)  
  
-   依存関係ダイアグラムを含むモデリング プロジェクトのソリューションです。 この依存関係ダイアグラムは、検証する Visual c# .NET または Visual Basic .NET プロジェクトの成果物にリンクする必要があります。 参照してください[コードから依存関係のダイアグラムを作成](../modeling/create-layer-diagrams-from-your-code.md)です。  
  
 この機能をサポートする Visual Studio のバージョンを確認するには、「 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。  
  
 Visual Studio で開いている依存関係図から手動でまたはコマンド プロンプトからコードを検証することができます。 ローカル ビルドまたは Team Foundation ビルドの実行時に、コードを自動的に検証することもできます。 参照してください[Channel 9 ビデオ: デザインし、依存関係のダイアグラムを使用して、アーキテクチャの検証](http://go.microsoft.com/fwlink/?LinkID=252073)です。  
  
> [!IMPORTANT]
>  Team Foundation ビルドを使用してレイヤー検証を実行する場合は、ビルド サーバーに同じバージョンの Visual Studio をインストールすることも必要です。  
  
-   [項目が検証をサポートしているかを参照してください。](#SupportsValidation)  
  
-   [その他の .NET アセンブリおよび検証用のプロジェクトを含める](#IncludeReferences)  
  
-   [コードを手動で検証します。](#ValidateManually)  
  
-   [コードを自動的に検証します。](#ValidateAuto)  
  
-   [レイヤー検証に関する問題をトラブルシューティングします。](#TroubleshootingValidation)  
  
-   [理解し、レイヤー検証エラーを解決するには](#UnderstandingValidationErrors)  

## <a name="live-dependency-validation"></a>ライブの依存関係の検証

Visual Studio のこのリリースで、リアルタイムで依存関係の検証が発生してエラーは、Visual Studio のエラー一覧 ウィンドウですぐに表示されます。

* ライブ評価は c# および Visual Basic.NET のサポートします。 

* ライブの依存関係の検証を使用する場合は、完全なソリューション分析を有効にする、エラー一覧に表示されるゴールド バーから、[オプション] の設定を開きます。 
 - このゴールド バーを却下できるは、ソリューションのアーキテクチャに関する問題をすべてを表示していない場合永続的にします。
 - 完全なソリューション分析を有効にしない場合は、編集されているファイルの場合のみ、分析が行われます。<p /> 

* ライブの検証を有効にするプロジェクトをアップグレードするときに、ダイアログ ボックスは、変換の進行状況を示します。

* ライブの依存関係の検証用のプロジェクトを更新するときに、NuGet パッケージのバージョンはすべてのプロジェクトに対して同一にするはアップグレードされ、使用中で最も高いバージョンです。 

* プロジェクトの更新に新しい依存関係検証プロジェクト トリガーを追加します。 
  
##  <a name="SupportsValidation"></a>項目が検証をサポートしているかを参照してください。  
 複数のアプリ間で共有される Web サイト、Office ドキュメント、プレーン テキスト ファイル、プロジェクトのファイルにレイヤーをリンクできますが、そのレイヤーは検証プロセスは含まれません。 個々のレイヤー間に依存関係が表示されない場合、これらのレイヤーにリンクされているプロジェクトやアセンブリへの参照については、検証エラーは表示されません。 このような参照は、コードがこれらの参照を使用している場合を除き、依存関係と見なされません。  
  
1.  図上の依存関係、1 つまたは複数のレイヤーを選択してを選択するを右クリックし、をクリックして**ビュー リンク**です。  
  
2.  **レイヤー エクスプ ローラー**を見て、**検証をサポート**列です。 値が false の場合、この項目では検証がサポートされません。  
  
##  <a name="IncludeReferences"></a>その他の .NET アセンブリおよび検証用のプロジェクトを含める  
 対応する .NET アセンブリまたはプロジェクトへの参照が自動的に追加された依存関係の図に項目をドラッグすると、**レイヤー参照**モデリング プロジェクト内のフォルダーです。 このフォルダーには、検証時に分析されたアセンブリおよびプロジェクトへの参照が格納されます。 手動で依存関係のダイアグラムにドラッグせず、他の .NET アセンブリおよび検証用のプロジェクトを含めることができます。  
  
1.  **ソリューション エクスプ ローラー**、モデリング プロジェクトを右クリックしてまたは**レイヤー参照**フォルダー、およびクリック**参照の追加**です。  
  
2.  **参照の追加**ダイアログ ボックスで、アセンブリまたはプロジェクトを選択し、をクリックして**OK**です。  
  
##  <a name="ValidateManually"></a>コードを手動で検証します。  
 ソリューション項目にリンクされている依存関係が開いている図がある場合は、実行、**検証**ダイアグラムからのショートカット コマンドです。 実行するコマンド プロンプトを使用することもできます、 **msbuild**コマンドと、 **/p:ValidateArchitecture**カスタム プロパティに設定する**True**です。 たとえば、コードの変更を行う場合、依存関係の競合を早期にキャッチできるようにレイヤー検証を定期的に実行します。  
  
#### <a name="to-validate-code-from-an-open-dependency-diagram"></a>開いている依存関係ダイアグラムからコードを検証するには   
  
1.  図の画面を右クリックし、をクリックして**アーキテクチャの検証**です。  
  
    > [!NOTE]
    >  既定では、**ビルド アクション**依存関係図 (.layerdiagram) ファイルにプロパティに設定**検証**ダイアグラムは、検証プロセスに含まれるようにします。  
  
     **エラー一覧**ウィンドウが、発生したエラーを報告します。 検証エラーの詳細については、次を参照してください。[把握して解決するレイヤーの検証エラー](#UnderstandingValidationErrors)です。  
  
2.  表示するには各エラーの発生元でエラーをダブルクリック、**エラー一覧**ウィンドウです。  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] では、エラーのソースの代わりにコード マップが表示されることがあります。 これは、コードで依存関係の図に指定されていないアセンブリに依存しているか、コードの依存関係ダイアグラムで指定された依存関係がない場合に発生します。 コード マップまたはコードをレビューし、依存関係が必要であるかどうかを検証してください。 コード マップの詳細については、次を参照してください。[ソリューション間の依存関係をマップする](../modeling/map-dependencies-across-your-solutions.md)です。  
  
3.  エラーを管理する、次を参照してください。[検証エラーを管理する](#ManageErrors)です。  
  
#### <a name="to-validate-code-at-the-command-prompt"></a>コマンド プロンプトでコードを検証するには  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] のコマンド プロンプトを開きます。  
  
2.  次のいずれかを選択します。  
  
    -   ソリューションの特定のモデリング プロジェクトに対してコードを検証するには、次のカスタム プロパティを使用して [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] を実行します。  
  
        ```  
        msbuild <FilePath+ModelProjectFileName>.modelproj /p:ValidateArchitecture=true  
        ```  
  
         - または  
  
         モデリングに含まれているフォルダーを参照し、実行してプロジェクト (.modelproj) ファイルおよび依存関係ダイアグラム[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]次のカスタム プロパティを使用。  
  
        ```  
        msbuild /p:ValidateArchitecture=true   
        ```  
  
    -   ソリューションのすべてのモデリング プロジェクトに対してコードを検証するには、次のカスタム プロパティを使用して [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] を実行します。  
  
        ```  
        msbuild <FilePath+SolutionName>.sln /p:ValidateArchitecture=true   
        ```  
  
         - または  
  
         依存関係図が入っているモデリング プロジェクトを含める必要がありを実行しているソリューション フォルダーを参照[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]次のカスタム プロパティを使用します。  
  
        ```  
        msbuild /p:ValidateArchitecture=true  
        ```  
  
     発生したすべてのエラーが表示されます。 詳細については[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]を参照してください[MSBuild](../msbuild/msbuild.md)と[MSBuild タスク](../msbuild/msbuild-task.md)です。  
  
 検証エラーの詳細については、次を参照してください。[把握して解決するレイヤーの検証エラー](#UnderstandingValidationErrors)です。  
  
###  <a name="ManageErrors"></a>検証エラーを管理します。  
 開発プロセスの実行中は、検証時に報告される一部の競合を抑制できます。 たとえば、既に解決したエラーや特定のシナリオに関連しないエラーを抑制できます。 エラーを抑制した場合は、[!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] で作業項目をログに記録することをお勧めします。  
  
> [!WARNING]
>  作業項目を作成またはそれにリンクするには、既に TFS ソース コード管理 (SCC) に接続されている必要があります。 別の TFS SCC への接続を開こうとすると、Visual Studio が現在のソリューションを自動的に閉じます。 作業項目を作成またはそれにリンクしようとする前に、適切な SCC に接続されていることを確認してください。 Visual Studio の今後のリリースでは、SCC に接続されていないとメニュー コマンドを使用できません。  
  
##### <a name="to-create-a-work-item-for-a-validation-error"></a>検証エラーの作業項目を作成するには  
  
-   **エラー一覧**ウィンドウで、エラーを右クリックし、順にポイント**作業項目の作成**、しを作成する作業項目の種類をクリックします。  
  
 これらのタスクで検証エラーを管理を使用して、**エラー一覧**ウィンドウ。  
  
|**目的**|**次の手順します。**|  
|------------|----------------------------|  
|検証中に選択したエラーを抑制する|1 つまたは複数選択したエラーを右クリックし、順にポイント**検証エラーの管理**、クリックして**エラーの抑制**です。<br /><br /> 抑制されたエラーは、取り消し線付きで表示されます。 次回検証を実行したとき、これらのエラーは表示されません。<br /><br /> 抑制されたエラーは、対応する依存関係図ファイルの .suppressions ファイルで追跡されます。|  
|選択したエラーの抑制を停止する|選択されている抑制されたエラーまたはエラーを右クリックし、**検証エラーの管理**、順にクリック**エラーの抑制の停止**です。<br /><br /> 次回検証を実行したとき、抑制されたエラーのうち選択したものが表示されます。|  
|復元のすべての抑制されたエラー、**エラー一覧**ウィンドウ|内を右クリック、**エラー一覧**ウィンドウをポイント**検証エラーの管理**、クリックして**抑制されたエラーの表示**です。|  
|すべての抑制されたエラーを非表示に、**エラー一覧**ウィンドウ|内を右クリック、**エラー一覧**ウィンドウをポイント**検証エラーの管理**、クリックして**抑制されたエラーの非表示に**です。|  
  
##  <a name="ValidateAuto"></a>コードを自動的に検証します。  
 ローカル ビルドを実行するたびにレイヤー検証を実行できます。 チームで Team Foundation ビルドを使用する場合、ゲート チェックインを使用してレイヤー検証を実行できます。これは、カスタム MSBuild タスクを作成することで指定できます。また、ビルド レポートを使用して検証エラーを収集することもできます。 ゲート チェックイン ビルドを作成するを参照してください。[ゲート チェックイン ビルド処理を使用して変更を検証する](http://msdn.microsoft.com/Library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec)です。  
  
#### <a name="to-validate-code-automatically-during-a-local-build"></a>ローカル ビルド時にコードを自動的に検証するには  
  
-   テキスト エディターを使用してモデリング プロジェクト (.modelproj) ファイルを開き、次のプロパティを追加します。  
  
```  
<ValidateArchitecture>true</ValidateArchitecture>  
```  
  
 \- または  
  
1.  **ソリューション エクスプ ローラー**依存関係ダイアグラムまたはダイアグラムを含むモデリング プロジェクトを右クリックし、クリックして**プロパティ**です。  
  
2.  **プロパティ**ウィンドウで、設定、モデリング プロジェクトの**アーキテクチャの検証**プロパティを**True**です。  
  
     これには、検証プロセス内のモデリング プロジェクトが含まれます。  
  
3.  **ソリューション エクスプ ローラー**検証に使用する依存関係図 (.layerdiagram) ファイルをクリックします。  
  
4.  **プロパティ**ウィンドウ、ことを確認して、ダイアグラムの**ビルド アクション**プロパティに設定されている**検証**です。  
  
     これには、検証プロセスに依存関係ダイアグラムが含まれます。  
  
 エラーを管理する [エラー一覧] ウィンドウで、次を参照してください。[検証エラーの管理](#ManageErrors)です。  
  
#### <a name="to-validate-code-automatically-during-a-team-foundation-build"></a>Team Foundation ビルド時にコードを自動的に検証するには  
  
1.  **チーム エクスプ ローラー**ビルド定義をダブルクリックし、クリックして**プロセス**です。  
  
2.  **ビルド プロセス パラメーター**、展開**コンパイル**、次のように入力し、**の MSBuild 引数**パラメーター。  
  
     `/p:ValidateArchitecture=true`  
  
 検証エラーの詳細については、次を参照してください。[把握して解決するレイヤーの検証エラー](#UnderstandingValidationErrors)です。 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] の詳細については、以下のトピックを参照してください。  
  
-   [アプリケーションのビルド](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)  
  
-   [ビルド プロセスの既定のテンプレートを使用します。](http://msdn.microsoft.com/Library/43930b12-c21b-4599-a980-2995e3d16e31)  
  
-   [UpgradeTemplate.xaml に基づいているレガシ ビルドの変更します。](http://msdn.microsoft.com/Library/ee1a8259-1dd1-4a10-9563-66c5446ef41c)  
  
-   [ビルド プロセス テンプレートのカスタマイズ](http://msdn.microsoft.com/Library/b94c58f2-ae6f-4245-bedb-82cd114f6039)  
  
-   [実行中のビルドの進行状況の監視](http://msdn.microsoft.com/Library/e51e3bad-2d1d-4b7b-bfcc-c43439c6c8ef)  
  
##  <a name="TroubleshootingValidation"></a>レイヤー検証に関する問題をトラブルシューティングします。  
 レイヤー検証に関する問題とその解決方法について、次の表で説明します。 これらの問題は、コードと設計の間の競合によって発生するエラーとは異なります。 これらのエラーの詳細については、次を参照してください。[把握して解決するレイヤーの検証エラー](#UnderstandingValidationErrors)です。  
  
|**問題点**|**考えられる原因**|**解決策**|  
|---------------|------------------------|--------------------|  
|検証エラーが予期したとおりに発生しない。|検証は、ソリューション エクスプ ローラーで他の依存関係図からコピーされたおよび同じモデリング プロジェクト内にある依存関係図では機能しません。 この方法でコピーされる依存関係ダイアグラムには、元の依存関係ダイアグラムと同じ参照が含まれています。|依存関係は、新しい図をモデリング プロジェクトに追加します。<br /><br /> 元の依存関係図から新しい図に要素をコピーします。|  
  
##  <a name="UnderstandingValidationErrors"></a>理解とレイヤー検証エラーの解決  
 依存関係図と照らし合わせてコードを検証する場合、コードが設計と競合する場合に、検証エラーが発生します。 たとえば、次の条件のとき、検証エラーが発生する場合があります。  
  
-   成果物が不適切なレイヤーに割り当てられている。 この場合、成果物を移動します。  
  
-   クラスなどの成果物が、アーキテクチャに違反する形で別のクラスを使用している。 この場合、コードをリファクタリングして依存関係を削除します。  
  
 これらのエラーを解決するには、コードを更新して、検証時にエラーが表示されなくなるようにします。 この作業は、反復的な方法で実行します。  
  
 次のセクションでは、これらのエラーで使用される構文を示し、これらのエラーの意味を説明し、エラーを解決または管理するために実行できることを提示します。  
  
|**構文**|**説明**|  
|----------------|---------------------|  
|*ArtifactN*(*ArtifactTypeN*)|*ArtifactN*依存関係図のレイヤーに関連付けられている成果物がします。<br /><br /> *ArtifactTypeN*の種類は、 *ArtifactN*、ように、**クラス**または**メソッド**、たとえば。<br /><br /> MySolution.MyProject.MyClass.MyMethod(Method)|  
|*NamespaceNameN*|名前空間の名前。|  
|*LayerNameN*|依存関係の図のレイヤーの名前です。|  
|*DependencyType*|間の依存関係の種類*Artifact1*と*Artifact2*です。 たとえば、 *Artifact1*が、**呼び出し**との関係*Artifact2*です。|  
  
|**エラーの構文**|**エラーの説明**|  
|----------------------|---------------------------|  
|DV0001:**無効な依存関係**|レイヤー参照に別のレイヤーにマップされているコード要素にマップされます (名前空間、型、メンバー) は、コード要素が、このレイヤーを含む依存関係の検証のダイアグラムでこれらのレイヤー間の依存関係矢印が表示されていないときに、この問題が報告されます。 これは、依存関係の制約違反です。|  
|DV1001:**無効な名前空間の名前**|この問題は、「Namespace 名を許可する」プロパティには、このコード要素が定義されている名前空間が含まれていないレイヤーに関連付けられているコード要素で報告されます。 これは、名前付けの制約違反です。 定義する、「許可 Namespace 名」の構文は、どのコードに関連付けられている要素はレイヤーの名前空間のセミコロンで区切って一覧になることが許可されます。|  
|DV1002: **unreferenceable 名前空間への依存関係**|この問題は、レイヤーに関連付けられているし、レイヤーの"Unreferenceable Namespace"プロパティで定義されている名前空間で定義されている他のコード要素を参照しているコード要素で報告されます。 これは、名前付けの制約違反です。 このレイヤーに関連付けられているコード要素では参照できませんの名前空間のセミコロンで区切られた一覧として「Unreferenceable 名前空間」プロパティが定義されていることに注意してください。|  
|DV1003:**許可しない名前空間の名前**|この問題は、「使用できない Namespace 名」プロパティがこのコード要素が定義されている名前空間を含んでいるレイヤーに関連付けられているコード要素で報告されます。 これは、名前付けの制約違反です。 コードをこのレイヤーに関連付けられている要素は定義されていない名前空間のセミコロンで区切られた一覧として、「許可しない名前空間名」プロパティが定義されていることに注意してください。|  
|DV3001:**不足しているリンク**|レイヤー '*LayerName*'へのリンク'*成果物*' が見つかりません。 アセンブリ参照が存在することを確認してください。|*LayerName*見つけることのできない成果物にリンクします。 たとえば、モデリング プロジェクトでクラスを含むアセンブリへの参照が欠落しているために、クラスへのリンクが欠落している場合があります。|  
|DV9001:**アーキテクチャの分析には、内部エラーが検出されました。**|結果が不完全である可能性があります。 詳細については、ビルド イベント ログの詳細または出力ウィンドウを参照してください。|詳細については、ビルド イベント ログまたは出力ウィンドウを参照してください。|  

 
## <a name="see-also"></a>参照  
 [開発時に、システムを検証します。](../modeling/validate-your-system-during-development.md)   
 [ビデオ: リアルタイムで、アーキテクチャの依存関係を検証します。](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)   
