---
title: "Visual Studio SDK の用語集 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "用語集 [Visual Studio SDK]"
ms.assetid: b64d432b-c39b-4904-ad18-3c3218b6e3aa
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# Visual Studio SDK の用語集
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

この用語集で使用される用語の定義を提供する、 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] ドキュメントです。  
  
## 用語  
 アドインの追加  
 ユーティリティ アプリケーション、ドライバー、またはその他のソフトウェアの主なアプリケーションに追加します。 Visual Studio 統合開発環境 \(IDE\) でアドインを IDE の機能を拡張するオートメーション ベースのアプリケーションです。  
  
 オートメーション モデル  
 以前のバージョンの Visual Studio 機能拡張モデルとして知られている、オートメーション モデルは、ことができるプログラミング インターフェイスでは、そのドライブの IDE を基になるルーチンにアクセスします。 アドイン、ウィザード、およびマクロは、コントロールにオートメーション モデルのオブジェクトを使用または IDE の機能を拡張します。  
  
 コマンド UI コンテキスト  
 UI コマンドやツールバーなどの要素の可視性を持つ、GUID の関連付けです。 コマンド UI コンテキストは、ウィンドウにアタッチされていない点で、選択範囲のコンテキストとは異なりします。  
  
 コマンド UI コンテキストを使用できます。  
  
-   特定のウィンドウがアクティブになったときに表示されるツールバーに GUID を割り当てます。  
  
-   ロードまたは VSPackage を実行することがなく、コマンドの可用性に GUID を割り当てます。  
  
-   影響を与えるアクティブなバインドをキーの GUID を割り当てます。  
  
-   マクロの記録を有効にするための GUID を割り当てます。  
  
-   デバッグ モードをアクティブ化、またはデザインと、エディターでの実行モードを切り替える GUID を割り当てます。  
  
 コンポーネント  
 そのアプリケーションで、ソフトウェアの実装に関する情報は既に存在せず、アプリケーションの機能の一部を実行可能なソフトウェアの一部です。 コンポーネントとアプリケーション間の通信では、スタイルの OLE インターフェイスを通じてのみです。  
  
 コンポーネント マネージャー  
 サービスを `SOleComponentManager`, 、最上位のコンポーネントの非ユーザー インターフェイスの調整サービスを提供します。`SOleComponentManager` サービスを実装して、 `IOleComponentManager` インターフェイスです。  
  
 コンポーネント UI マネージャー  
 サービスを `SOleComponentUIManager`, 、ユーザー インターフェイスの調整のサービスを提供します。`SOleComponentUIManager` サービスを実装して、 `IOleComponentUIManager` と `IOleInPlaceComponentUIManager` インターフェイスです。  
  
 コンテキスト バッグ  
 `IVsUserContext` オブジェクト \(COM オブジェクト\)、環境のコンポーネントにアタッチします。 このオブジェクトは、検索キーワード、F1 キーワード、およびコンポーネントに関連する属性を格納します。 コンテキスト バッグは、さらに、それらにリンクされている任意のサブコンテキスト バッグをポイントします。  
  
 コンテキストのプロバイダー  
 関連付けられているコンテキスト バッグ IDE 内のコンポーネント。 このようなコンポーネントには、ツール ウィンドウ、エディター、またはプロジェクトの階層が含まれます。  
  
 designer  
 ユーザーが \(フォーム、ボタン、およびその他のコントロール\) の UI の要素を操作できるようにするプログラミング インターフェイスです。  
  
 DocData  
 世界では、ドキュメントの基になるデータをカプセル化する COM オブジェクトがドキュメント\/ビューの分離がある場合 \(たとえば、テキスト エディターの場合、なりますすべてのテキスト エディター ビューを基になるテキスト バッファー\)。 EditorFactory がこのオブジェクトを指定しない場合、IDE は代わりに 1 つが製造されます。 このオブジェクトの役割は、データの永続性を管理して、複数の共有セマンティクスが同じには、このビュー `DocData`します。 場合、 `DocData` サポートしています、 `IOleCommandTarget` 、インターフェイス、UIShell のコマンド ルーティングに含まれることができます。  
  
 DocObject  
 テクノロジは、ホストによって提供されるフレーム内で UI をホストするために使用します。 サポートする任意の埋め込みに関係する用語の具体的には、 `IOleDocument` し、関連するインターフェイスです。 このテクノロジには、COM ドキュメントの実装の詳細、Visual Basic 5.0 でツール ウィンドウ、Visual Basic 6.0 での ActiveX デザイナーなどの多くの潜在的なアプリケーションがあります。  
  
 ドキュメント  
 ドキュメント全体を包括的に参照する — 両方、 `DocData` と `DocView`です。 など、DocumentFrame が含まれています、 `DocView`, への参照も維持されますが、 `DocData` を永続化を処理します。  
  
 DocView  
 表示して、基になる操作、ユーザーが対話する、DocObject\/埋め込み\/ペイン `DocData`します。 ユーザーが含まれているドキュメント\/ビューの分離のメリットを利用できないことに注意してください、 `DocObject` インターフェイスを設計します。 ユーザーでは、全体の DocObject を使用して、抽象的 \(と小さい形式化された\) と呼ばれる、基になるデータの概念を使用する代わりにビューとして機能する `DocData`です。`DocView` オブジェクトは、IDE のドキュメントのフレーム オブジェクト \(MDI 子ウィンドウ\) を常に埋め込まれます。  
  
 DTE  
 `DTE` \(開発ツールの機能拡張\) のオブジェクトは最上位のアクセス ポイントを使用すると、プログラムでの自動化や、IDE を拡張する Visual Studio オートメーション モデルにします。  
  
 ダイナミック ヘルプ\] ウィンドウ  
 IDE によって実装され、検索キーワードまたは F1 ヘルプ トピックの一覧を表示するツール ウィンドウです。  
  
 エディター  
 実装するコード \(クラス、CLSID\)、 `DocView`です。 実装して `DocData` ビュー\/データの分離がサポートされている場合。  
  
 拡張機能  
 変更、カスタマイズ、または IDE に追加する機能です。 オートメーション モデルまたは Vspackage を使用して拡張機能を作成します。  
  
 外部エディター  
 Microsoft Word などの IDE に固有ではないエディターです。 独自のメカニズムによって登録されているし、IDE の外部で使用することができます。 このエディターを埋め込むことができる場合は、IDE のウィンドウ内で表示されます。 埋め込むことができない、独立したトップレベル ウィンドウが作成されます。  
  
 階層構造  
 ツリー ノードの各ノードのプロパティのセットに関連付けられています。  
  
 独立した最上位のコンポーネント  
 モードレスの最上位ウィンドウを使用して、スタンドアロンのアプリケーション ウィンドウとして効果的に動作させることができますはインプロセスでオブジェクトとして実装するコンポーネント。 そのため、独立した最上位コンポーネントでは、モーダルかどうかと、IDE とメッセージ ループのサービスを調整する必要があります。 プロセス内のオブジェクトには、独自のメッセージ ループはありません。  
  
 情報プロバイダー  
 情報プロバイダーは、キーワードを検索できの形式で、トピックの一覧を返すモジュール `IVsUserContextItem` オブジェクトです。 情報プロバイダーに F1 および検索キーワードの項目を指定するには、コンパイル済みヘルプ ファイルを登録 \(します。HxS\) システムとします。 これらのファイルでヘルプ トピックを使用して、ダイナミック ヘルプ\] ウィンドウに表示され、ユーザーが f1 キーを押したかどうかを示すトピックの一覧を提供します。  
  
 インプレースでのコンポーネント  
 実装する VSPackage オブジェクト、 `IOleInPlaceComponent` を視覚的に、IDE によって所有されているドキュメント ウィンドウ内にあるウィンドウを管理するインターフェイスです。 インプレースでのコンポーネントは、標準 OLE メニュー結合; に参加していません。代わりに、ユーザー インターフェイス要素を IDE に統合します。  
  
 インプレースでコンポーネントの 2 種類があります。 ハードウェア配線インプレース コンポーネントおよびコンポーネントのコントロールです。  
  
 ハードウェア配線インプレース構成要素では、メニューのツールバー、およびプレース ホルダーとして表示された IDE に直接の組み込まれているかどうかは、IDE のユーザー インターフェイスに緊密に統合されているコマンドがあります。  
  
 コンポーネントのコントロールが、IDE に統合されて、独自のユーザー インターフェイス要素のいずれかがありません。代わりに、IDE のメニューのコマンド、およびツールバーを使用します。 たとえば、太字のコマンドは、フォームに埋め込まれているリッチ テキスト コントロール内で選択されている単語を太字を使用可能性があります。 ただし、コンポーネント コントロールが動的にインストールされているコンポーネントに固有の UI 要素が表示されることを要求することができます。  
  
 言語サービス  
 により、開発者は VSPackage テキスト マークを付け、色分けなど、コンピューター言語のコード エディターの機能を実装するオブジェクトのセットです。  
  
 他のファイル プロジェクト  
 任意のプロジェクトに含まれていない開いているファイルの保管に使用するプロジェクト。 このプロジェクト内の項目の一覧は保存されません。  
  
 プロジェクト  
 プロジェクトが、階層のオブジェクトの構成または COM オブジェクトを実装する、 `IVsHierarchy` インターフェイスです。  
  
 プロジェクトに固有のデザイナーまたはエディター  
 プロジェクトの種類とは無関係に使用できないデザイナー。 プロジェクトに固有のすべてのデザイナーは、レジストリ内のエディター ファクトリの情報を入力してください。 IDE し、インスタンス化できるデザイナー特定のファイルの種類が特定のプロジェクトで開かれるたびにします。  
  
 プロジェクトの種類\] ウィンドウ  
 常にグローバルな選択状態のコンテキストから、現在アクティブなプロジェクトの階層と項目を追跡するウィンドウです。 プロジェクトの種類の windows を使用して、 `SVsTrackSelectionEx` サービス変更の IDE のアラートを生成して、ユーザーにフィードバックを表示したりします。 ソリューション エクスプ ローラーでは、プロジェクトの種類\] ウィンドウの例を示します。  
  
 \[プロパティ\] ウィンドウ  
 旧プロパティ ブラウザーです。  
  
 プロジェクトの参照に基づく  
 同じディレクトリにあるプロジェクトのファイルを必要としないプロジェクトです。 代わりに、その他の関連性のないディレクトリからファイルへの参照が格納され、プロジェクト自体で管理されています。  
  
 実行中のドキュメント テーブル  
 IDE はすべて現在開いているドキュメントの一覧を保持する内部構造体です。 この一覧には、ドキュメントの現在編集されているかどうかに関係なくメモリ内のすべての開いているドキュメントが含まれます。 ドキュメントは、保存すると、エディター、プロジェクト内のファイルまたはメイン プロジェクト ファイル \(たとえば、\*.vcproj ファイル\) で開かれているストアド プロシージャを含む任意の項目です。  
  
 選択コンテキスト  
 IDE ですべてのウィンドウの詳細の一部であり、アクティブな選択範囲の追跡に使用されるデータ。 選択範囲のコンテキストで構成されます。  
  
-   ポインター、 `IVsHierarchy` プロジェクト階層のインターフェイス  
  
-   プロジェクト項目の項目の識別子です。  
  
-   ポインター、 `ISelectionContainer` アクティブなオブジェクトのプロパティへのアクセスを提供するインターフェイスです。  
  
-   要素の値の配列。  
  
 service  
 1 つの COM オブジェクト内に存在する COM インターフェイスの一連のコントラクト。 GUID により識別される、サービスを作成するときに、サービスを実行する COM インターフェイスのセットを定義します。 COM オブジェクトでは、サービスを使用して、相互に通信します。  
  
 ソリューション  
 ユーザーは、使用する関連プロジェクトのグループです。  
  
 標準的なデザイナー  
 プロジェクトの種類に関係なく使用できるデザイナー。 すべての標準的なデザイナーは、レジストリ内のエディター ファクトリの情報を入力してください。 IDE し、インスタンス化できるデザイナー特定の拡張子を持つファイルが開かれるたびにします。 データは、ファイルに保存する必要があります。  
  
 標準エディター  
 どの特定のプロジェクトの種類に関係なく使用できるエディターです。 このようなエディターがある EditorFactories レジストリに登録します。 これにより、IDE を見つけて、エディターを起動できます。  
  
 標準の OS エディター  
 いない Visual Studio は、埋め込まれたアイテムを特定します。 よく知られている Win32 キーを使用して登録されている \(たとえば、Win32 エクスプ ローラーを呼び出す方法を認識する\)。 このようなエディターを埋め込むことができる場合、エディターは、IDE では、その場所にも表示します。 それ以外の場合、このようなエディターの独立したトップレベル ウィンドウが作成されます。  
  
 サブコンテキスト バッグ  
 `IVsUserContext` オブジェクト コンテキスト バッグにリンクします。 このオブジェクトは、検索キーワード、F1 キーワード、および IDE コンポーネント内の選択項目の属性を格納します。 サブコンテキストの例では、ツール ウィンドウまたはエディターでのキーワードで、コマンドがあります。  
  
 タスク一覧  
 IDE によって実装され、アクティブなタスクの一覧を表示するツール ウィンドウです。  
  
 テキスト バッファー  
 オブジェクトの共通名 `VSTextBuffer`します。  
  
 テキスト ビュー  
 オブジェクトの共通名 `VSTextView`します。  
  
 ツールの最上位のコンポーネント  
 IDE のユーザー インターフェイスと緊密に調整、モードレスのポップアップ ウィンドウとして動作するコンポーネント。 独立した最上位のコンポーネントと同様にツールの最上位のコンポーネントのモダリティと、IDE とメッセージ ループのサービスも調整する必要があります。  
  
 最上位のコンポーネント  
 IDE ウィンドウのクライアント領域ではなくモードレス トップレベル ウィンドウを管理する VSPackage オブジェクトです。 最上位のコンポーネントは、実装、 `IOleComponent` アクセスなどのメッセージ ループのサービスのアイドル時間を利用するインターフェイスです。  
  
 UI がアクティブ  
 VSPackage オブジェクトが表示され、現在フォーカスがあります。  
  
 UI の階層  
 実装する COM オブジェクト、 `IVsUIHierarchy` 階層を表示できるようにするインターフェイスです。 UI の \[階層\] ウィンドウを実装して、 `ISelectionContainer` インターフェイスのプロパティ\] ウィンドウを更新する。 必要に応じて、他のプロジェクトの種類の windows はこの実装を使用できます。  
  
 VSCT  
 Visual Studio コマンド テーブルです。 .Vsct ファイルには、配置、メニューのツールバー、および XML 形式でコマンドの動作に関する情報が含まれています。  
  
 VSPackage  
 次の 1 つ以上提供することによって、Visual Studio IDE を拡張するソフトウェアのインストールの一部: ユーザー インターフェイス、サービス、プロジェクトの種類、またはエディターとデザイナーです。 VSPackage を実装する COM オブジェクトから成る、 `IVsPackage` インターフェイスと 1 つまたは複数の他の COM オブジェクトを選択し、その他の機能をサポートするその他のインターフェイスを実装します。 さらに、VSPackage は特定の登録が必要です。