---
title: "コードから依存関係図を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: 58c3ea71-2dbc-4963-bf82-40f1924cf973
caps.latest.revision: 64
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b17d12160920952170d042eb46191df66542c80a
ms.openlocfilehash: e51f32303496d20980d7442458cd35350db01687
ms.lasthandoff: 02/22/2017

---
# <a name="create-dependency-diagrams-from-your-code"></a>コードから依存関係図を作成します。
ソフトウェア システムのおおまかな論理アーキテクチャを視覚化するには、作成、*依存関係ダイアグラム*Visual Studio でします。 コードがこのような設計と一致していることを確認するには、依存関係図を使用してコードを検証します。 Visual c# .NET および Visual Basic .NET プロジェクトの依存関係図を作成できます。 この機能をサポートする Visual Studio のバージョンを参照してください[アーキテクチャとモデリング ツールのバージョンのサポート](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)  
  
 ![依存関係図を作成する](../modeling/media/layerdiagramvisualizecode.png "LayerDiagramVisualizeCode")  
  
 依存関係ダイアグラムでは、Visual Studio のソリューション項目と呼ばれる論理的、抽象的なグループに編成できます。*レイヤー*します。 レイヤーを使用して、これらの成果物が実行する主要タスク、またはシステムの主要コンポーネントを示すことができます。 各レイヤーには、より詳細なタスクを示す別のレイヤーを含めることができます。 意図的または既存を指定することも*の依存関係*層の間です。 矢印で表されるこれらの依存関係は、どのレイヤーが、他のレイヤーが表す機能を使用できるか、または現在使用しているかを示します。 コードのアーキテクチャ コントロールを保持するには、目的の依存関係を図で示し、図と照らし合わせてコードを検証します。  
  
 [ビデオ: リアルタイムで、アーキテクチャの依存関係を検証します。](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4) 
  
##  <a name="a-namecreatediagrama-create-a-dependency-diagram"></a><a name="CreateDiagram"></a>依存関係図を作成します。  
 依存関係図を作成する前に、ソリューションにモデリング プロジェクトがあることを確認ください。 
  
> [!IMPORTANT]
>  しない追加、ドラッグ、または別のモデリング プロジェクトまたはソリューション内の別の場所には、モデリング プロジェクトから既存の依存関係図をコピーします。 これで、図を変更しても、元の図からの参照が保持されます。 また、これによってレイヤー検証が正しく機能しないため、要素が欠落したり、図を開こうとすると他のエラーが発生するなど、別の問題が生じる可能性があります。  
>   
>  代わりに、新しい依存関係図をモデリング プロジェクトに追加します。 元の図から新しい図へ要素をコピーします。 モデリング プロジェクトと新しい依存関係図の両方を保存します。  
  
#### <a name="to-add-a-new-dependency-diagram-to-a-modeling-project"></a>新しい依存関係図をモデリング プロジェクトに追加するには  
  
1.  **アーキテクチャ**] メニューの [選択**新しい依存関係図**します。  
  
2.  **テンプレート**、選択**依存関係ダイアグラム**します。  
  
3.  図に名前を付けます。  
  
4.  **モデリング プロジェクトに追加**を参照し、ソリューションに既存のモデリング プロジェクトを選択します。  
  
     または  
  
     選択**新しいモデリング プロジェクトを作成する**新しいモデリング プロジェクトをソリューションに追加します。  
  
    > [!NOTE]
    >  依存関係のダイアグラムは、モデリング プロジェクト内に存在しなければなりません。 ただし、ソリューション内のどの場所にある項目にもリンクできます。  
  
5.  必ず、モデリング プロジェクトと依存関係ダイアグラムの両方を保存してください。  

## <a name="drag-and-drop-or-copy-and-paste-from-a-code-map"></a>ドラッグ ドロップ、またはコピーして貼り付けるには、コード マップから

1. 使用して、ソリューションのコード マップを生成、**アーキテクチャ**メニュー。 

2. 製品コード内の依存関係を適用する場合は、ソリューション フォルダーと「テスト アセット」を削除するコード マップのフィルターを適用することを検討してください。

3. 生成されたコード マップで「外部」のノードまたはを展開し、名前空間の依存関係を強制するかどうかに応じて、外部のアセンブリを表示およびコード マップから省略可能なアセンブリを削除します。 

4. 使用して、ソリューションの新しい依存関係図を作成、**アーキテクチャ**メニュー

5. コード マップ上のすべてのノードを選択 (を使用して_Ctrl_ + _A_、かキーを押してラバー バンドの選択を使用して、 _shift キーを押し_キー をクリックしてドラッグすると、リリースを実行する前にします。

6. ドラッグ アンド ドロップ、または、コピーや貼り付け、新しい依存関係の検証の図に、選択した要素です。 

7. これは、現在のアプリケーション アーキテクチャを示します。 対象を決定するアーキテクチャと依存関係のダイアグラムを適宜変更します。

![コード マップから生成された依存関係図](media/dependency-validation-01.png)
  
##  <a name="a-namecreatelayersa-create-layers-from-artifacts"></a><a name="CreateLayers"></a>成果物からレイヤーを作成します。  
 レイヤーは、プロジェクト、コード ファイル、名前空間、クラス、メソッドなど、Visual Studio ソリューションの項目から生成できます。 これにより、レイヤーと項目の間のリンクが自動的に作成され、レイヤー検証プロセスに含まれます。  
  
 Word 文書や PowerPoint プレゼンテーションなどの検証をサポートしない項目にレイヤーをリンクすることもできます。こうすると、仕様や計画にレイヤーを関連付けることができます。 複数のアプリが共有するプロジェクトのファイルにレイヤーをリンクすることもできます。ただし、これらのレイヤーは検証プロセスには含まれず、"レイヤー 1"、"レイヤー 2" などの汎用名で表示されます。  
  
 リンクされた項目が検証をサポートしているかを表示するには、開く**レイヤー エクスプ ローラー**を調べると、**検証をサポート**アイテムのプロパティです。 参照してください[の成果物にリンクを管理する](#Managing)です。  
  
|**目的**|**次の手順します。**|  
|------------|----------------------------|  
|1 つの成果物を表すレイヤーを生成する|<ol><li>これらのソースから依存関係ダイアグラムへの項目をドラッグします。<br /><br /> <ul><li>**ソリューション エクスプローラー**<br /><br />         ファイルやプロジェクトなどをドラッグできます。</li><li>コード マップ<br /><br />         参照してください[ソリューション間の依存関係をマップ](../modeling/map-dependencies-across-your-solutions.md)と[コード マップを使ったアプリケーションのデバッグ](../modeling/use-code-maps-to-debug-your-applications.md)します。</li><li>**クラス ビュー**または**オブジェクト ブラウザー**</li></ul><br />     レイヤーが図に表示され、成果物にリンクされます。</li><li>レイヤーの名前を、関連するコードや成果物の役割を表す名前に変更します。</li></ol> **重要:**バイナリ ファイルを依存関係のダイアグラムにドラッグしても、モデリング プロジェクトへの参照は自動的に追加しません。 検証するバイナリ ファイルを手動でモデリング プロジェクトに追加する必要があります。 **バイナリ ファイルをモデリング プロジェクトに追加するには** <ol><li>**ソリューション エクスプ ローラー**、モデリング プロジェクトのショートカット メニューを開きを選択し、**既存項目の追加**します。</li><li>**既存項目の追加**バイナリ ファイルを参照] ダイアログ ボックスでを選択し、[ **OK**します。     バイナリ ファイルがモデリング プロジェクトに表示されます。</li><li>**ソリューション エクスプ ローラー**、バイナリ ファイルを追加して、キーを押します**f4 キーを押して**を開くには、**プロパティ**ウィンドウです。</li><li>各バイナリ ファイルで設定、**ビルド アクション**プロパティを**検証**します。</li></ol>|  
|選択したすべての成果物を表す&1; つのレイヤーを生成する|同時にすべての成果物を依存関係のダイアグラムにドラッグします。<br /><br /> レイヤーが図に表示され、すべての成果物にリンクされます。|  
|選択した各成果物を表すレイヤーを生成する|プレス アンド ホールド、 **SHIFT**キーすべてのアイテム、依存関係図に、同時にドラッグします。 **注:**を使用する場合、 **SHIFT**キー範囲の項目を選択し、キーを離すと、アイテムを選択した後にします。 成果物を図にドラッグするときは、キーを再び押して、押したままにします。 <br /><br /> 各成果物を表すレイヤーが図に表示され、各成果物にリンクされます。|  
|成果物をレイヤーに追加する|成果物をレイヤーにドラッグします。|  
|リンクされない新しいレイヤーを生成する|**ツールボックス**、展開、**依存関係ダイアグラム**セクションし、ドラッグ、**レイヤー**依存関係のダイアグラムにします。<br /><br /> 複数のレイヤーを追加するには、ツールをダブルクリックします。 完了したら、選択、**ポインター**ツールまたはキーを押して、 **ESC**キー。<br /><br /> または<br /><br /> 依存関係図のショートカット メニューを開き、選択**追加**、にして**レイヤー**します。|  
|入れ子になったレイヤーを生成する|既存のレイヤーを別のレイヤー上へドラッグします。<br /><br /> または<br /><br /> レイヤーのショートカット メニューを開き、選択**追加**、にして**レイヤー**します。|  
|複数の既存レイヤーを含む新しいレイヤーを生成する|レイヤーを選択し、ショートカット メニューを開き、選択すると、し、**グループ**します。|  
|レイヤーの色を変更する|設定の**色**プロパティを使用する色にします。|  
|レイヤーに関連付けられている成果物を、指定した名前空間に所属させることができないように指定する|レイヤーの名前空間を入力**禁止された名前空間**プロパティです。 セミコロンを使用して (**;**) 名前空間を分離します。|  
|レイヤーに関連付けられている成果物が、指定した名前空間に依存できないように指定する|レイヤーの名前空間を入力**Namespace 依存関係の禁止**プロパティです。 セミコロンを使用して (**;**) 名前空間を分離します。|  
|レイヤーに関連付けられている成果物を、指定した名前空間のいずれかに必ず所属させるように指定する|レイヤーの名前空間を入力**名前空間のために必要な**プロパティです。 セミコロンを使用して (**;**) 名前空間を分離します。|  
  
 レイヤーの数字は、レイヤーにリンクされている成果物の数を示します。 ただし、この数値を読み取るときには、次の点に注意してください。  
  
-   1 つのレイヤーが他の成果物を含む&1; つの成果物にリンクされているが、他の成果物に直接リンクされていない場合、その数字にはリンクされた成果物のみが含まれます。 ただし、レイヤー検証時の分析にはそれらの他の成果物も含まれます。  
  
     たとえば、1 つのレイヤーが 1 つの名前空間にリンクされている場合、その名前空間に複数のクラスが含まれていても、リンクされた成果物の数は 1 です。 レイヤーに名前空間の各クラスへのリンクもある場合、その数字にはリンクされたクラスが含まれます。  
  
-   1 つのレイヤーに成果物にリンクされた他のレイヤーが含まれている場合は、そのコンテナー レイヤーの数字にそれらの成果物が含まれていなくても、コンテナー レイヤーはそれらの成果物にリンクされます。  
  
##  <a name="a-namemanaginga-manage-links-between-layers-and-artifacts"></a><a name="Managing"></a>レイヤーと成果物の間のリンクを管理します。  
  
1.  依存関係図、レイヤーのショートカット メニューを開いてにして**リンクの表示**します。  
  
     **レイヤー エクスプ ローラー**選択したレイヤーに関する成果物のリンクを示しています。  
  
2.  これらのリンクを管理するには、次のタスクを行います。  
  
|**目的**|**レイヤー エクスプ ローラー**|  
|------------|---------------------------|  
|レイヤーと成果物のリンクを削除する|成果物のリンクのショートカット メニューを開きを選択し、**削除**します。|  
|リンクを別のレイヤーに移動する|成果物のリンクを図上の既存のレイヤーにドラッグします。<br /><br /> または<br /><br /> 1.成果物のリンクのショートカット メニューを開きを選択し、**切り取り**します。<br />2.依存関係図、レイヤーのショートカット メニューを開いてにして**貼り付け**します。|  
|リンクを別のレイヤーにコピーする|1.成果物のリンクのショートカット メニューを開きを選択し、**コピー**します。<br />2.依存関係図、レイヤーのショートカット メニューを開いてにして**貼り付け**します。|  
|既存の成果物のリンクから新しいレイヤーを生成する|成果物のリンクを図上の空白領域にドラッグします。|  
|リンクされた成果物が依存関係図と照らし合わせた検証をサポートしていることを確認します。|見て、**検証をサポート**成果物のリンクの列です。|  
  
##  <a name="a-namediscoveringa-reverse-engineer-existing-dependencies"></a><a name="Discovering"></a>既存の依存関係をリバース エンジニア リング  
 依存関係が存在するのは、あるレイヤーに関連付けられている成果物が、別のレイヤーに関連付けられている成果物を参照している場合です。 たとえば、あるレイヤー内のクラスが、別のレイヤー内のクラスを保持する変数を宣言する場合などです。 図のレイヤーにリンクされている成果物の既存の依存関係はリバース エンジニアリングできます。  
  
> [!NOTE]
>  成果物の種類によっては、依存関係をリバース エンジニアリングできないものもあります。 たとえば、テキスト ファイルにリンクされているレイヤーから、またはそのレイヤーに対して依存関係をリバース エンジニアリングすることはできません。 リバース エンジニア リングできる依存関係のあるどの成果物を表示するには、1 つまたは複数のレイヤーのショートカット メニューを開いてにして**リンクの表示**します。 **レイヤー エクスプ ローラー**、確認、**検証をサポート**列です。 依存関係は成果物についてこのコラムのリバース エンジニア リングにできません**False**します。  
  
-   1 つまたは複数のレイヤーを選択したレイヤーのショートカット メニューを開き順に選択**依存関係の生成**します。  
  
 通常は、不要な依存関係がいくつか見つかります。 これらの依存関係を編集して、目的の設計に準拠するようアラインできます。  
  
##  <a name="a-nameeditdependenciesa-edit-layers-and-dependencies-to-show-the-intended-design"></a><a name="EditDependencies"></a>レイヤーと依存関係を表示して目的の設計を編集します。  
 システムまたは対象とするアーキテクチャを対象となる変更を記述するには、依存関係図を編集します。  
  
|**目的**|**次の手順を実行します。**|  
|------------|-----------------------------|  
|依存関係の方向を変更または制限する|設定の**方向**プロパティです。|  
|新しい依存関係を生成する|使用して、**依存関係**と**双方向の依存関係**ツールです。<br /><br /> 複数の依存関係を描画するには、ツールをダブルクリックします。 完了したら、選択、**ポインター**ツールまたはキーを押して、 **ESC**キー。|  
|レイヤーに関連付けられている成果物が、指定した名前空間に依存できないように指定する|レイヤーの名前空間を入力**Namespace 依存関係の禁止**プロパティです。 セミコロンを使用して (**;**) 名前空間を分離します。|  
|レイヤーに関連付けられている成果物を、指定した名前空間に所属させることができないように指定する|レイヤーの名前空間を入力**禁止された名前空間**プロパティです。 セミコロンを使用して (**;**) 名前空間を分離します。|  
|レイヤーに関連付けられている成果物を、指定した名前空間のいずれかに必ず所属させるように指定する|レイヤーの名前空間を入力**名前空間のために必要な**プロパティです。 セミコロンを使用して (**;**) 名前空間を分離します。|  
  
##  <a name="a-nameeditlayouta-change-how-elements-appear-on-the-diagram"></a><a name="EditLayout"></a>図上の要素を表示する方法を変更します。  
 プロパティを編集して、レイヤーのサイズ、形状、色、位置、または依存関係の色を変更できます。  
  
##  <a name="a-namecodemapsa-discover-patterns-and-dependencies-on-a-code-map"></a><a name="Codemaps"></a>パターンと、コード マップ上の依存関係を検出します。  
 依存関係図を作成するときに作成することも**コード マップの**です。 これらの図を利用することで、コードを検証するときに、パターンと依存関係を見つけやすくなります。 ソリューション エクスプローラー、クラス ビュー、またはオブジェクト ブラウザーを使用して、アセンブリ、名前空間、およびクラスを調べることができます。これらは、通常は既存のレイヤーに対応しています。 コード マップについての詳細は、次を参照してください。  
  
-   [ソリューション間の依存関係をマップする](../modeling/map-dependencies-across-your-solutions.md)  
  
-   [コード マップを使用してアプリケーションをデバッグする](../modeling/use-code-maps-to-debug-your-applications.md)  
  
-   [コード マップ アナライザーを使用して潜在的な問題を検索する](../modeling/find-potential-problems-using-code-map-analyzers.md)  
  
## <a name="see-also"></a>関連項目  
 [ビデオ: リアルタイムで、アーキテクチャの依存関係を検証します。](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)   
 [依存関係図: リファレンス](../modeling/layer-diagrams-reference.md)   
 [依存関係図: ガイドライン](../modeling/layer-diagrams-guidelines.md)   
 [依存関係図をコードを検証します。](../modeling/validate-code-with-layer-diagrams.md)   
 [コードの視覚化](../modeling/visualize-code.md)
