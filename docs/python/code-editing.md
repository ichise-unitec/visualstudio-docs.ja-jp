---
title: "Visual Studio での Python コードの編集 | Microsoft Docs"
ms.custom: 
ms.date: 07/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 16f0e7d406e042d16fff4fbe257b62bac97253c3
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2018
---
# <a name="editing-python-code"></a>Python コードの編集

開発者は、コード エディターで多くの時間を費やすので、[Visual Studio での Python のサポート](installation.md)は、生産性を向上させる機能を提供します。 機能には、IntelliSense 構文の強調表示、オートコンプリート、署名ヘルプ、メソッドのオーバーライド、検索、ナビゲーションが含まれます。 

このトピックの内容:

- [IntelliSense](#intellisense) (入力候補、シグネチャ ヘルプ、クイック ヒント、コードの色分け表示)
- [コード スニペット](#code-snippets)
- [コードのナビゲーション](#navigating-your-code)

Visual Studio でのコードの編集に関する全般的な説明については、「[コード エディターとテキスト エディターでのコードの作成](../ide/writing-code-in-the-code-and-text-editor.md)」をご覧ください。 また、コードの特定のセクションに注意を集中するのに役立つ [Visual Studio のアウトライン機能](../ide/outlining.md)についての記事もご覧ください。 Python のサポートには、Visual Studio オブジェクト ブラウザーの使用が含まれています (**[表示] > [その他のウィンドウ] > [オブジェクト ブラウザー]** を選択するか、Ctrl + W、J キーを押します)。各モジュールで定義されているクラスとそれらのクラスで定義されている関数を調べることができます。 

また、エディターは Visual Studio の対話型のウィンドウと統合され、この 2 つ間で容易にコードを交換できます。 詳細については、「[チュートリアル ステップ 3: 対話型 REPL ウィンドウを使用する](vs-tutorial-01-03.md)」と[対話型ウィンドウの使用 - 対話型コマンドにコードを送信する](interactive-repl.md#send-code-to-interactive-command)に関する項目を参照してください。

Python コードの編集の概要については、「[Editing Python Code](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=r2iQH5LWE_4605918567)」 (Python コードの編集) (Microsoft Virtual Academy、2 分 30 秒) をご覧ください。

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Editing-Python-Code-r2iQH5LWE_4605918567]

## <a name="intellisense"></a>IntelliSense

IntelliSense により、[入力候補](#completions)、[シグネチャ ヘルプ](#signature-help)、[クイック ヒント](#quick-info)、[コードの色分け表示](#code-coloring)が提供されます。 パフォーマンスを向上するために、IntelliSense はプロジェクト内の各 Python 環境に対して生成される入力候補データベースを使用します。 パッケージを追加、削除、更新した場合はデータベースの更新が必要になる可能性があります。 データベースの状態は、**[IntelliSense]** タブの **[Python Environments (Python 環境)]** ウィンドウ (ソリューション エクスプローラーの兄弟ウィンドウ) に表示されます (「[Python Environments](python-environments.md)」 (Python 環境) を参照してください)。 

### <a name="completions"></a>入力候補

入力候補は、エディター内の現在の場所に入力するのに適している可能性があるステートメント、識別子、その他の単語として表示されます。 一覧に表示される項目はコンテキストに基づいており、誤った選択肢や不適切な選択肢を除くようにフィルター処理されています。 入力候補は別のステートメント (`import` など) や演算子 (ピリオドを含む) を入力したときによく表示されますが、Ctrl + J、Space キーを押すことでいつでも表示できます。

![メンバー入力候補](media/code-editing-completions-simple.png)

入力候補一覧が開いたら、方向キーまたはマウスを使用するか、入力を続けることによって目的の入力候補を検索できます。 多くの文字を入力するほど一覧が絞り込まれ、可能性の高い入力候補が表示されます。 次のようなショートカットも使用できます。

- 名前の先頭ではない文字を入力する ('parse' を入力して 'argparse' を検索するなど)
- 単語の先頭の数文字のみを入力する ('abc' を入力して 'AbstractBaseClass' を検索する、'air' を入力して 'as_integer_ratio' を検索するなど)
- 文字をスキップする ('b64' を入力して 'base64' を検索するなど)

以下に、いくつかの例を示します。

![フィルター処理されたメンバー入力候補](media/code-editing-completion-filtering.png)

変数または値の後にピリオドを入力するとメンバー入力候補が自動的に表示され、可能性がある型のメソッドと属性が表示されます。 複数の型の可能性がある変数の場合は、すべての型のすべての候補が一覧に表示され、各入力候補がどの型でサポートされるかを示した追加情報も表示されます。 入力候補がすべての型でサポートされる場合は、注釈なしで表示されます。

![複数の型のメンバー入力候補](media/code-editing-completion-types.png)

既定では、"dunder" メンバー (先頭および末尾にダブル アンダースコアが付いたメンバー) は表示されません。 一般に、このようなメンバーに直接アクセスしてはいけません。 しかし、必要な場合は、先頭に二重アンダー スコアを入力すると、これらの入力候補が一覧に追加されます。

![プライベートのメンバー入力候補](media/code-editing-completion-dunder.png)

`import` および `from ... import` ステートメントでは、インポートできるモジュールの一覧が表示されます。 `from ... import` を使用すると、一覧には指定したモジュールからインポートできるメンバーが含まれています。

![インポートの入力候補](media/code-editing-completion-import.png)

`raise` および `except` ステートメントでは、エラーの種類として可能性があるクラスの一覧が表示されます。 この一覧にはすべてのユーザー定義例外は含まれていない可能性がありますが、入力に適した組み込みの例外をすばやく見つけるのに役立ちます。

![例外の入力候補](media/code-editing-completion-exception.png)

@ を入力するとデコレーターが開始され、可能性があるデコレーターが表示されます。 これらの項目の多くはデコレーターとして使用できないため、ライブラリのドキュメントを確認して、どれを使用するかを判断する必要があります。

![デコレーターの入力候補](media/code-editing-completion-decorator.png)

> [!Tip]
> 入力候補の動作は、**[ツール] > [オプション] > [テキスト エディター] > [Python] > [詳細設定]** で構成できます。 この設定の **[Filter list based on search string (検索文字列に基づいて一覧をフィルター処理する)]** では、入力の際に入力候補がフィルター処理されます (既定ではオンになっています)。また、**[Member completion displays intersection of members (メンバー入力候補にメンバーの積集合を表示する)]** では、可能性のあるすべての型でサポートされている入力候補のみが表示されます (既定ではオフになっています)。 「[Options - completion results](options.md#completion-results)」(オプション - メンバー入力候補の結果) を参照してください。

### <a name="signature-help"></a>シグネチャ ヘルプ

関数を呼び出すコードの作成中に始め `(` を入力するとシグネチャ ヘルプが表示され、利用できるドキュメントとパラメーター情報が表示されます。 これは関数呼び出し内で Ctrl + Shift + Space キーを押して表示することもできます。 表示される情報は関数のソース コード内のドキュメント文字列によって異なりますが、すべての既定値が含まれます。

![シグネチャ ヘルプ](media/code-editing-signature-help.png)

> [!Tip]
> シグネチャ ヘルプを無効にするには、**[ツール] > [オプション] > [テキスト エディター] > [Python] > [全般]** に移動し、**[ステートメント入力候補] > [パラメーター情報]** をオフにします。

### <a name="quick-info"></a>クイック ヒント

識別子にマウス ポインターを置くと、クイック ヒントが表示されます。 クイック ヒントには、識別子に応じて、可能性のある値または型、利用できるドキュメント、戻り値の型、定義の場所が表示されます。

![クイック ヒント](media/code-editing-quick-info.png)

### <a name="code-coloring"></a>コードの色分け表示

コードの色分け表示は、コード分析の情報を使用して、変数、ステートメント、その他のコード部分を色分けして示します。 たとえば、モジュールまたはクラスを参照する変数を関数やその他の値とは異なる色で表示したり、パラメーター名をローカル変数やグローバル変数とは異なる色で表示したりできます (既定では、関数は太字では表示されません)。

![コードの色分け表示](media/code-editing-code-coloring.png)

色をカスタマイズするには、**[ツール] > [オプション] > [環境] > [フォントおよび色]** に移動し、**[表示アイテム]** の一覧で Python のエントリを変更します。

![[フォントおよび色] のオプション](media/code-editing-customize-colors.png)

> [!Tip]
> コードの色分け表示を無効にするには、**[ツール] > [オプション] > [テキスト エディター] > [Python] > [詳細設定]** に移動し、**[その他のオプション] > [Color names based on type (種類に基づく色の名前)]** をオフにします。 「[Options - Miscellaneous Options](options.md#miscellaneous-options)」(オプション ∸ その他のオプション) を参照してください。


## <a name="code-snippets"></a>コード スニペット

コード スニペットは、ショートカットを入力して Tab キーを押すか、**[編集] > [IntelliSense] > [コード スニペットの挿入]** **[ブロックの挿入]** コマンドを使用することでファイルに挿入できるコード フラグメントです。 たとえば、`class` を入力した後で Tab キーを押すと、クラスの残りの部分が生成されます。 強調表示されたフィールド間を Tab キーで移動して名前と基底クラスのリストを上書きし、Enter キーを押して本文の入力を開始できます。

![コード スニペット](media/code-editing-code-snippets.png)

利用可能なコード スニペットは、コード スニペット マネージャーで確認できます (**[ツール] > [コード スニペット マネージャー]**) を選択し、言語として **[Python]** を選択します。

![コード スニペット マネージャー](media/code-editing-code-snippets-manager.png)

独自のスニペットの作成方法については、「[チュートリアル: コード スニペットを作成する](../ide/walkthrough-creating-a-code-snippet.md)」をご覧ください。 

便利なコード スニペットを作成したので共有したいとお考えの場合は、ぜひ gist に投稿して[マイクロソフトまでお知らせください](https://github.com/Microsoft/PTVS/issues)。 Visual Studio の将来のリリースに含めさせていただく可能性があります。


## <a name="navigating-your-code"></a>コードのナビゲーション

Visual Studio の Python のサポートとして、ソース コードが提供されているライブラリ、[ナビゲーション バー](#navigation-bar)、[[定義へ移動]](#go-to-definition)、[[移動]](#navigate-to)、[[すべての参照の検索]](#find-all-references) など、コード内のナビゲーションを迅速にするためのさまざまな手段が用意されています。 また、Visual Studio の[オブジェクト ブラウザー](../ide/viewing-the-structure-of-code.md#BKMK_ObjectBrowser)も使用できます。

### <a name="navigation-bar"></a>[ナビゲーション バー]

ナビゲーション バーは各エディター ウィンドウの上部に表示され、2 つのレベルの定義リストを含みます。 左側のドロップダウン リストには、現在のファイル内の最上位のクラスと関数の定義が表示されます。右側のドロップダウン リストには、左側に表示されているスコープ内の定義のリストが表示されます。 エディター内を移動するとこれらのリストが現在のコンテキストを示すように更新され、リストからエントリを選択してそのエントリに直接ジャンプすることもできます。

![ナビゲーション バー](media/code-editing-navigation-bar.png)

> [!Tip]
> ナビゲーション バーを非表示にするには、**[ツール] > [オプション] > [テキスト エディター] > [Python] > [全般]** を選択し、**[設定] > [ナビゲーション バー]** をオフにします。

### <a name="go-to-definition"></a>[定義へ移動]

**[定義へ移動]** を使用すると、識別子 (関数名、クラス、変数など) の使用場所から、その識別子が定義されているソース コードにすばやくジャンプできます。 これは、識別子を右クリックして **[定義へ移動]** を選択するか、識別子にキャレットを置いて F12 キーを押すと起動されます。 この機能は、ソース コードが利用可能ならばコードと外部ライブラリ全体で機能します。 ライブラリのソース コードを利用できない場合に **[定義へ移動]** を使用すると、モジュール参照の関連する `import` ステートメントにジャンプするか、エラーが表示されます。

![[定義へ移動]](media/code-editing-go-to-definition.png)

### <a name="navigate-to"></a>移動

**[編集] > [移動]** コマンド (Ctrl + コンマ キー) を実行すると、エディター内に検索ボックスが表示されます。ボックスに任意の文字列を入力すると、その文字列を含む関数、クラス、変数を定義しているコード内の箇所が表示されます。 この機能は **[定義へ移動]** の機能と似ていますが、識別子の使用場所を探す必要がありません。

任意の名前をダブルクリックするか、方向キーで選択して Enter キーを押すと、その識別子の定義に移動します。

![移動](media/code-editing-navigate-to.png)

### <a name="find-all-references"></a>[すべての参照の検索]

**[すべての参照の検索]**は、特定の識別子の定義場所と使用場所の両方 (インポートと代入を含む) を見つけるのに便利な方法です。 これは、識別子を右クリックして **[すべての参照の検索]** を選択するか、識別子にキャレットを置いて Shift + F12 キーを押すと起動されます。 一覧内の項目をダブルクリックすると、その場所に移動します。

![[すべての参照の検索] の結果](media/code-editing-find-all-references.png)