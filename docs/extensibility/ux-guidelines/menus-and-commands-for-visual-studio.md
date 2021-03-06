---
title: "メニューと Visual Studio のコマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a1ed675-2bd1-4603-ba3a-f40dfb5cfb69
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ce4e297b698952135ef9f771243577789719dbae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="menus-and-commands-for-visual-studio"></a>メニューと Visual Studio のコマンド
## <a name="command-usage"></a>コマンドの使用方法  
  
### <a name="overview"></a>概要  
 多くの個別製品を構成するスイートは、Microsoft Office とは異なりは、Visual Studio には、グローバルの Visual Studio IDE には、そのコマンド セット原因となる各ある多くの製品が含まれています。 IDE では、フィルター コンテキストに基づく、ユーザーに利用可能な機能によって何千ものコマンドの複雑さを管理します。  
  
 デザイン ウィンドウからコードが編集ウィンドウに切り替えるなどのユーザーのコンテキストが変更された機能に関係のない新しいコンテキストは表示されなくなります。 同時に、プロパティおよびツールボックスのオプションなど、関連の動的な情報と共に新しい機能サーフェスします。 ユーザーは、使用可能なコマンド セットのスワップを確認する必要がありますできません。 ユーザーが散漫いらだったりして表示または消失しているコマンドの場合、UI の設計では調整が必要です。 ユーザーの現在のコンテキストは常に IDE のタイトル バー、プロパティ ウィンドウまたはプロパティ ページ ダイアログ ボックスでなど、1 つまたは複数の方法で表示されます。  
  
 コマンド バーの UI に柔軟性を確保します。 唯一のコマンドは、環境は、メイン メニューおよび両方をカスタマイズしても非表示にするメイン コマンド バーの Visual Studio に備わって構造体します。 他のコマンド バーが表示され、アプリケーションの状態に基づいて表示されなくなります。 ツール ウィンドウおよびドキュメント エディターでは、埋め込みツールバー、ウィンドウの端にも格納できます。  
  
#### <a name="basic-guidelines"></a>基本的なガイドライン  
  
##### <a name="use-existing-shared-commands-command-groups-and-menus-whenever-possible"></a>既存の共有のコマンド、コマンド グループ、および可能な限りメニューを使用します。  
 コマンドは、コンテキストに基づいて通常示さ、ので、使用すると既存の共有メニューおよびコマンド グループはコマンドの構造はコンテキストでの変更の間で比較的安定していることになります。 共有のコマンドを再利用し、関連するコマンドを共有の近くに新しいコマンドを配置することも IDE の複雑さを軽減しよりユーザー フレンドリなエクスペリエンスを作成します。 新しいコマンドを定義する必要が、既存の共有コマンド グループに配置することを試みます。 新しいグループを定義する場合は、配置、関連するコマンド グループの近くに既存の共有 メニューで新しいトップレベルのメニューを作成する前にします。  
  
##### <a name="do-not-create-icons-for-every-command"></a>すべてのコマンドのアイコンを作成しないでください。  
 コマンド アイコンを作成する前に、十分に検討します。 アイコンは、コマンドに対してのみ作成する必要があります。  
  
-   既定のツールバーに表示されます。  
  
-   ユーザーが経由のツールバーに追加する可能性が高い、**カスタマイズしています.**ダイアログ。  
  
-   別のマイクロソフト製品に同じアクションに関連付けられたアイコンがあります。  
  
##### <a name="limit-the-addition-of-keyboard-shortcuts"></a>キーボード ショートカットの追加の制限  
 大多数のユーザーは、すべての使用できるショートカット キーの一部を使用します。 確かでない場合は、機能をキーボード ショートカットを連結しません。 ユーザーの作業では、新しいショートカットを追加する前にチームが発生します。  
  
##### <a name="give-commands-a-default-menu-placement"></a>既定のメニューの配置コマンドを提供します。  
 コマンドが他のユーザーによっては、カスタマイズして、それに従って設計することに注意してください。 非表示のコマンドのようなものはありません。 Visual Studio のすべてのコマンドが表示されます、**ツール > カスタマイズ**ダイアログ ボックスで、コマンド ウィンドウで、オートコンプリート、**ツール > オプション > キーボード**ダイアログ、および開発ツール環境 (DTE)。 ユーザーが見つけやすいように、名前と、.ctc ファイルのツールヒント コマンドを指定してください。  
  
##### <a name="do-not-duplicate-shared-commands-on-an-embedded-toolbar"></a>埋め込みツールバー上の共有のコマンドと重複しません。  
 ユーザーのフォーカスの領域の近くにコマンドを配置すると便利です。 これを行う方法の 1 つは、エディター ツール ウィンドウまたはドキュメントの上部にある埋め込みツールバーを作成するのにです。 ツールバーの配置コマンドをウィンドウ内でコンテンツの地域に固有にする必要があります。 これらのツールバー上の共有のコマンドと重複しません。 たとえば、埋め込みツールバー内の [保存] アイコンを配置ことはありません。  
  
### <a name="content-and-command-visibility"></a>コンテンツとコマンドの可視性  
 コマンドは、次のスコープに存在します。**環境**、**階層**、および**ドキュメント**です。 コマンドの配置で信頼するためには、それぞれのスコープを把握しています。  
  
 コマンド、**環境**スコープ プライマリ コンテキストを確立および複数のコンテキスト間で共有されます。 表示の設定やドキュメントおよびツール ウィンドウの配置を変更します。 スコープには、環境でコマンド**新しいプロジェクト**、**サーバーへの接続**、**プロセス アタッチ**、**切り取り**、 **コピー**、**貼り付け**、**検索**、**オプション**、**カスタマイズ**、**新しいウィンドウ**、および**ヘルプを表示**です。  
  
 コマンド、**階層**スコープの管理などの Visual Studio の階層**プロジェクト**、**チーム**、および**データ**です。 たとえば、プロジェクトのサブコンテキスト - に関係する**デバッグ**、**ビルド**、**テスト**、**アーキテクチャ**、または**分析**. スコープには、階層内のコマンド**新しい項目の追加**、**新しいクエリ**、**プロジェクト設定**、**新しいデータ ソースの追加**、 **パフォーマンス ウィザードを起動して**、および**新しいダイアグラム**です。  
  
 コマンド、**ドキュメント**コード、デザイン、または作業項目クエリ (WIQ) など、ドキュメントの内容のスコープ動作します。 これらもツール ウィンドウのビューを操作またはそのツール ウィンドウに固有ではそれ以外の場合。 ドキュメント スコープのコマンドは、の自体などの階層に固有であるファイル オブジェクトにも対処**プロジェクトから削除**です。 スコープには、ドキュメント内のコマンド**リファクター > の名前を変更**、**作業項目のコピーを作成する**、**すべて展開**、**すべて折りたたむ**、および**ユーザー タスクの作成**です。  
  
### <a name="command-placement-decisions"></a>コマンド配置の決定  
 コマンドを作成することが決まっている、適切な配置とキーボード ショートカットを作成するかどうかを決定する必要があります。 コマンドを配置する場所を確立するためにこの意思決定パスに従います。  
  
 ![コマンド配置の意思決定グラフ](../../extensibility/ux-guidelines/media/0501-a_commandplacement.png "0501 a_CommandPlacement")  
  
 **Visual Studio でのコマンド配置の意思決定パス**  
  
### <a name="command-placement-in-menus"></a>メニューにコマンドの配置  
  
#### <a name="main-menu-bar"></a>メイン メニュー バー  
 メイン メニュー バーでは、UI に影響を与えるコンテキスト固有] メニューの [パッケージのコマンドの標準の場所をする必要があります。 メイン メニュー バーは、環境を使用して、コントロールのコマンドを表示することで他のコマンドの構造とは異なります。 その他のすべてのコマンド バーでは、コンテキスト外であるコマンドを無効にするかどうか、メニューまたはツールバーに配置されます。  
  
 環境では、メイン メニュー バーに組み込まれているが、IDE 全体とタスクの複数のドメイン間で共通するコマンドのセットを定義します。 これらのコマンドは常に表示に関係するは、Vspackage が環境に読み込まれます。 Vspackage では、このコマンドのセットを拡張できます、設定は各製品のコマンドの配置からのコマンドは各チームの責任です。  
  
 Visual Studio のメイン メニューの構造は、次のメニュー カテゴリに分類できます。  
  
##### <a name="core-menus"></a>コア メニュー  
  
-   ファイル  
  
-   編集  
  
-   表示  
  
-   ツール  
  
-   ウィンドウ  
  
-   ヘルプ  
  
##### <a name="project-specific-menus"></a>プロジェクト固有のメニュー  
  
-   プロジェクト  
  
-   ビルド  
  
-   デバッグ  
  
##### <a name="context-specific-menus"></a>特定のコンテキスト メニュー  
  
-   チーム  
  
-   データ  
  
-   テスト  
  
-   アーキテクチャ  
  
-   解析  
  
##### <a name="document-specific-menus"></a>ドキュメントに固有のメニュー  
  
-   形式  
  
-   テーブル  
  
##### <a name="when-designing-main-menus-adhere-to-these-rules"></a>メイン メニューを設計する場合は、これらの規則に従います。  
  
-   特定のコンテキストで 25 の最上位アイテムを超えない  
  
-   メニューは、600 ピクセルの高さを超えることはありません。  
  
-   Ultimate SKU と一般的なプロファイルなどの複数のコンテキストでのメイン メニューを評価します。  
  
-   ポップアップ メニューは許容されます。  
  
-   サブメニューには、少なくとも 3 つの項目と 7 個を含める必要があります。  
  
-   サブメニューが深いレベルの 1 つだけを移動する必要があります - 一部の Visual Studio メニュー項目がカスケードのサブメニューがあるけれども、このパターンはお勧めできません  
  
-   6 個の区切り記号を使用します。 グループは、次の図に従う必要があります。  
  
     ![メイン メニューのグループ化のためのガイドライン](../../extensibility/ux-guidelines/media/0501-b_mainmenus.png "0501 b_MainMenus")  
  
-   図に各グループ化する必要はありません、中に、その他のグループを追加するは制限されます。  
  
-   各グループは、2 ~ 7 のメニュー項目が必要です。  
  
#### <a name="main-menu-ordering"></a>メイン メニューが順序付け  
 新しい最上位の項目を追加する前に、既存のトップレベル メニューにコマンドを配置することを検討します。 新しいトップレベルのメニューに追加する場合は、正しい場所に配置することを確認します。 メニューは、プロジェクト、コンテキスト、またはドキュメントに特定するかどうかを決定します。 簡潔なトップレベルのメニューの名前を保持し、1 つだけの単語を使用します。  
  
 コア メニューには、ブックエンド コマンドの残りの部分が必要があります。 ファイル、編集、およびビューは常に左、およびツール、ウィンドウ、およびヘルプは、右側に常にする必要があります。  
  
#### <a name="context-menus"></a>コンテキスト メニュー  
 説明が困難なインターフェイスで結果コンテキスト メニュー内の過度の機能を配置することです。 主要な機能がすべては、メイン メニュー バーを使用する必要があります。 コマンドの配置は、重複しているコマンドを避けるために既存のコマンドを使用して調整する必要があります。 コンテキスト メニューは、シェルは、コンテキスト メニューで、ソリューション、プロジェクト ノード、またはプロジェクト項目はかどうかに応じて含める必要がある標準のメニュー グループを定義します。  
  
 コンテキスト メニューを設計する場合は、さらに、メイン メニューの場合と同じルールに従います。  
  
-   25 のトップレベルのメニュー項目を超えないことです。  
  
-   ポップアップ メニューが許容されるが、必要があります 1 階層を超えないように-決してカスケード フライアウトを使用します。  
  
-   6 個の区切り記号を使用します。  
  
### <a name="command-placement-in-toolbars"></a>ツールバーのコマンドの配置  
  
#### <a name="general-toolbars"></a>[全般] ツールバー  
 ツールバーの配置の設計と、ときに、これらの標準に従います。  
  
-   ボタンの 1 つ以上の動詞を使用しないでください。 ボタンを 1 つ 1 つのアクションを = です。  
  
-   ラベルを強調する必要がある場合にのみ、アイコンと共にテキストを使用します。  
  
-   コンボ ボックスは 1 つのセッションで複数回切り替えるはプロパティにのみ使用します。 それ以外の場合、別の場所のプロパティを公開します。  
  
-   コンボ ボックスの幅には、ボックス + 30% 内の最も長いアイテムの幅を等しく必要があります。 たとえば、最も長いが 200 ピクセルの場合は、し、コンボ ボックスも 260 ピクセルにする必要があります。  
  
-   区切り記号の使用を制限します。 ドロップダウン リストの横にある区切り記号の使用は、ドロップダウン自体の図形が、表示する区切り記号として機能するためのアンチ パターンでは、です。  
  
-   6 つのアイコンに 3 種類のアイコンのグループを含める必要があります。  
  
-   修飾子は、複数の便利なコマンドの結果、最後の設定を格納する分割ボタンを使用します。  
  
     ![Visual Studio での分割ボタン](../../extensibility/ux-guidelines/media/0501-c_splitbuttons.png "0501 c_SplitButtons")  
  
     **分割ボタンの例です。左側の 6 つのコマンドは、1 つのボタンに代わりに適合できます。**  
  
#### <a name="product-specific-toolbars"></a>製品固有のツールバー  
 各製品には、既定のツールバーを含む頻繁に使用して重要なコマンド、および各製品の既定のツールバーが初めて、製品のインストール後に Visual Studio が起動するときに表示する必要がありますを指定できます。  
  
 また、製品は、共有コマンド グループと、IDE によって提供されるメニューを活用していることも必要があります。 各共有コマンド グループは、ユーザーにとって意味のある方法で関連するコマンドを整理するためのものを共有 メニューに配置されます。 この共有のコマンドの構造を活用して複雑さを軽減するために重要です。  
  
#### <a name="global-toolbars"></a>グローバル ツールバー  
 グローバル ツールバーでは、すぐに 1 行の右上に収まる必要があります。 新しいグローバル ツールバーを作成するときに、ツールバーの種類のガイドラインに従います。  
  
 **ツールバーの一般的なガイドライン:**  
  
-   各ツールバーは、コモン コントロール (グリッパー、オーバーフロー) に 24 ピクセルを持っています。  
  
-   各ツール バー ボタンは、22 ピクセル幅の広いパディングを含めてです。 分割ボタン、アイコンを行う別の 11 ピクセルの幅を追加します。  
  
-   ツールバーの間でのコマンドの重複が許可されます。  
  
 **ドキュメント固有ツールバー**特定のファイルの種類がアクティブなときに表示され、別のファイルの種類がアクティブになったときに表示されなくなります。  
  
-   ドキュメントに固有のツールバーには、複数の 12 個のボタンがありません。  
  
-   ツールバーの幅の合計は 300 ピクセルを超えないことがあります。  
  
-   1 つの埋め込みツールバーまたはドキュメント固有の 1 つのグローバル ツールバーのいずれかが、各ファイルの種類を持つことができます。  
  
 **コンテキスト固有のツールバー**表示時に特定のコンテキスト セットがあり、長期間アクティブなままになる傾向があります。  
  
-   コンテキスト固有のすべてのツールバーのボタンの上限は 18 です。  
  
-   ほとんどのユーザーは、コンテキストがアクティブな場合、このツールバーのコマンドを使用一貫しない場合、関連付けないこのツールバー コンテキストを使用します。  
  
-   コンテキストを終了するときに、ツールバーが消えることを確認します。 スタートアップ時にこれらのツールバーの [なし] が表示されます。  
  
 **ツールバーとコンテキストがありません**自動的に表示されることはありません。 これらは、のみと、ユーザーがアクティブにそれらを表示します。 下 200 ピクセル、幅の最大値を保持します。  
  
### <a name="general-organization-and-shell-defined-groups"></a>一般的な組織とシェル定義グループ  
 既存の共有のコマンド、コマンド グループ、およびメニューを使用します。 新しいコマンドを定義する必要が、既存の共有コマンド グループに配置することを試みます。 新しいグループを定義する必要がある、関連するコマンドのグループに近い既存の共有 メニューに新しいトップレベルのメニューを作成する前に配置することを試みます。 これにより、IDE で一貫性のあるコマンド配置を確保しながらコマンド複雑さが軽減されます。  
  
 共有**形式**通常デザイナー スタイルのドキュメント ウィンドウのコンテキストで表示] メニューの [が次の図に示すましょう。  
  
 ![コールアウト付き visual Studio の書式 メニュー](../../extensibility/ux-guidelines/media/0501-d_formatmenu.png "0501 d_FormatMenu")  
  
 **Visual Studio のメニュー グループ**  
  
### <a name="reducing-and-reusing-commands"></a>減らすと、コマンドを再利用  
 コマンドは、通常に基づいて表示コンテキスト、ユーザーが特定の時点ではコマンドの数を減らすためにされます。 ただし、既存の共有メニュー再利用することも必要があります、コンテキストでの変更の間で安定したコマンドの構造が比較的に保たれるようにするコマンドのグループ。  
  
 共有のコマンドを再利用し、関連するコマンドを共有の近くに新しいコマンドを置くことは、IDE の複雑さを軽減しよりユーザー フレンドリなエクスペリエンスを作成します。  
  
## <a name="naming-commands"></a>コマンドの名前を付ける  
  
### <a name="naming-conventions"></a>名前付け規則  
 ユーザーを検索し、コマンドラインを使用してまたはキーボードのショートカットへのバインドのいずれかのコマンドを実行するため、一貫性のあるコマンドの名前を付けることが重要です。 コマンド名は、どのような目的は、ツールバーにある、またはカスケードまたはコンテキスト メニューに表示される際のコマンドを理解して、ユーザーにも役立ちます。  
  
#### <a name="when-naming-commands"></a>ときに名前を付けるコマンド。  
  
-   簡単にローカライズされるように、テキストを構築します。 テキストのローカライズに関する詳細は、次を参照してください。 [for Visual Studio の国際対応](http://msdn.microsoft.com/en-us/1cc35051-8126-441f-bea9-059245a47b1d)です。  
  
-   簡潔にします。 コマンドは、以下の 3 つの単語を使用する必要があります。  
  
-   タイトル文字の大文字と小文字を使用します。 各単語の最初の文字が大文字で入力する必要があります。 Visual Studio でのテキスト書式の詳細については、次を参照してください。[テキストのスタイル](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle)です。  
  
-   コマンドを配置する場所を考慮に入れておきます。 トップレベル メニューまたはフライアウトですか。 たとえば、ときフライアウト、最上位レベルのコマンドの配置コマンドをグループ化する必要があります"Align"フライアウト コマンド必要があります「左」「右」、"Center"、「両端揃え、」などです。 フライアウト コマンド「左揃え」または「Align 権限」という名前に重複します。  
  
     ![Visual Studio の書式 メニュー](../../extensibility/ux-guidelines/media/0502-a_formatmenu.png "0502 a_FormatMenu")  
  
### <a name="using-icons-with-commands"></a>コマンドでアイコンの使用  
 適度に使用するコマンドのペアリングのアイコンの使用中です。 コマンドと、一意のイメージを関連付けると、そのコマンドを識別するためのユーザーの権限が hastens、ビジュアルや非効率性が過剰に使用するイメージで発生します。 次の規則は、コマンドのアイコンを作成するかどうかを決定する際に役立ちます。  
  
#### <a name="use-an-icon-with-a-command-only-if"></a>アイコンを使用して、コマンドの場合にのみ使用します。  
  
-   同じコマンドでは、Microsoft Office アプリケーションのいずれかなど、目立つ別のマイクロソフト製品に関連付けられている、アイコンがあります。  
  
-   コマンドは、既定のツールバーに配置されます。  
  
-   ユーザーがツールバーを使用してに追加すると思われる specialty コマンドは、コマンド、 **「カスタマイズ…」**ダイアログ。  
  
## <a name="access-and-shortcut-keys"></a>アクセスやショートカット キー  
  
### <a name="overview"></a>概要  
 キーボードのキーの割り当ての 2 種類があります。  
  
-   **アクセス キー** (アクセラレータとも呼ばれます) キーボードとアクセスできるように、メニュー コマンド実行の各ラベルに ダイアログ ボックスの UI。 アクセス キーは、アクセシビリティのためにほとんどの場合は、すべてのメニューとダイアログ ボックスのほとんどのコントロールに割り当てられて、記録する、現在のウィンドウのみに影響することはできません、およびローカライズされているをします。  
  
-   **ショートカット キー**コントロール (Ctrl) とファンクション (Fn) のキー シーケンスを使用して、ほとんどの場合。 ためのものより高度なユーザーとヘルパーの生産性の点でします。 最もよく使用されるコマンドにのみ割り当てられていて、メイン メニューの処理をバイパスしてクイック アクセスを許可します。 ショートカット キーが記録するため、その理由必要がありますに割り当てるプロファイル方式で一貫性のあります。 ショートカット キー スキームでは、プロファイルからを異なる場合があります。 ユーザーはを通じてキーのショートカットをカスタマイズ**ツール > オプション > キーボード**です。  
  
### <a name="assigning-access-keys"></a>アクセス キーの割り当てください。  
 アクセス キーは、Alt と英数字のキーで構成されます。 例外なしには、各メニュー項目にアクセス キーを指定します。 Windows とアクセス キーを割り当てるための一般的な規則に従ってください。 たとえば、アクセス キーを**ファイル > 新規**は常に**alt キーを押し、F、N**です。  
  
 せずに (大文字または小文字) には、' i' または 'l' 小文字などシングル ピクセル幅の文字を使用して区別するために困難なのでディセンダー (g、j、p、q、および y) を持つ文字は使用しないでください。  
  
 可能な場合は、重複するキーを使用しないでください。 重複は回避できませんの場合は、メニュー システムは、キーを使用しているすべてのコマンド間で循環して競合を処理します。 例として、[ファイル] メニューで、"N"のアクセス キーと重複するコマンドの"Number"という仮想の**alt キーを押し、F、N** 、新しいファイルを作成し、 **alt キーを押し、F、N、N**は"Number"コマンドを実行します。  
  
### <a name="assigning-shortcut-keys"></a>ショートカット キーの割り当てください。  
 すべてのコマンドで不要な税のシステムやユーザー メモリ) の場合は過剰ため新しいショートカット キーの割り当てを回避します。 カスタマー エクスペリエンス向上プログラム (CEIP) からのデータは、Visual Studio のユーザーが統合されたショートカットの小さなサブセットのみを使用することを示します。  
  
 ショートカットを定義するときに、これらの規則に従います。  
  
-   **制御 (Ctrl) とファンクション (Fn) のキー シーケンスを使用します。**  
  
-   **Preserve は、ショートカットを頻繁に使用されます。** 最も一般的なショートカットを維持します。  
  
-   **エディターのショートカットを簡単に入力します。** 型へのショートカットを開発者がコードを書き込み中にほとんど必要があることのコマンドにバインドします。 たとえば、 **Edit.InvokeSmartTag** ctrl キーと同様にクイック ショートカット キーが存在する必要があります +/といない Alt + Shift + f10 キー。  
  
-   **一貫してテーマが適用されたショートカットを目指しています。**  
  
-   **どの修飾子が使用するキーを決定する Windows のガイドラインに従います。** ドキュメント全体に適用されるコマンドなどの大規模な効果を持つコマンドを Ctrl キーの組み合わせを使用します。 Shift キーの組み合わせを使用して、拡張したり、標準のショートカット キーの操作を補完するコマンド。 Ctrl キーを押しながら alt キーの組み合わせを使用しないでください。  
  
-   **余分なショートカットを削除します。** 従来の機能がある場合は、アクセス キーが同じコマンドにすばやくアクセスを提供する場合は、極端な infrequency (10 回 CEIP データからよりも少なくなります) または中程度 infrequency を (CEIP データから 100 回よりも少なくなります) で使用されるショートカットを削除することを検討してください。 例: alt キーを押し、H、C で/ヘルプの目次が開きます。  
  
 ショートカットの可用性を確認する簡単な方法はありません。 ショートカットを追加する場合は、次の手順に従います。  
  
1.  一覧を確認[Visual Studio 2013 ショートカット](http://visualstudioshortcuts.com/2013/)で自分をグループ化するのと同様のコマンドがあるかを確認します。  
  
2.  移動して**ツール > オプション > 環境 > キーボード**し、ショートカットをテストします。 各キーボード マップ スキームが下にある一覧に「次の追加キーボード マップ スキームを適用します」確認します。 一意のショートカットを共有、全般、c#、VB、および C++ のプロファイルを確認してください。 ショートカットのでは、その場所のいずれかにマップされていない場合があります。