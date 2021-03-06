---
title: "Visual Studio デバッガーを使用して C++ を使用してデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords: debugger
ms.assetid: 639e430b-6d2d-46bd-b738-8c60dfb384f1
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ddf6aadc6b2debcb7423df589fb11739039c6476
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="debug-with-c-using-the-visual-studio-debugger"></a>Visual Studio デバッガーを使用して C++ でのデバッグします。

Visual Studio デバッガーでは、アプリのデバッグに役立つ多くの強力な機能を提供します。 このトピックでは、いくつかの基本的な機能を説明する簡単な方法を説明します。

## <a name="create-a-new-project"></a>新しいプロジェクトを作成する 

1. Visual Studio で、次のように選択します。**ファイル > 新しいプロジェクト**です。

2. **Visual C**、選択**Windows デスクトップ**、中央のペインの  **Windows コンソール アプリケーション**です。

    表示されない場合、 **Windows コンソール アプリケーション**プロジェクト テンプレートをクリックして、**開いている Visual Studio インストーラー**の左側のウィンドウ内のリンク、**新しいプロジェクト** ダイアログ ボックス。 Visual Studio インストーラーが起動します。 選択、 **C++ を使用したデスクトップ開発**ワークロード、順に選択**変更**です。

3. ような名前を入力**MyDbgApp**  をクリック**OK**です。

    Visual Studio では、プロジェクトを作成します。

4. MyDbgApp.cpp で次のコードに置き換えます

    ```c++
    int main()
    {
        return 0;
    }
    ```

    このコードを (削除しないでください`#include "stdafx.h"`)。

    ```c++
    #include <list>  
    #include <iostream>

    using namespace std;

    void doWork()
    {
        list <int> c1;

        c1.push_back(10);
        c1.push_back(20);

        const list <int> c2 = c1;
        const int &i = c2.front();
        const int &j = c2.front();
        cout << "The first element is " << i << endl;
        cout << "The second element is " << j << endl;

    }

    int main()
    {
        doWork();
    }
    ```

## <a name="set-a-breakpoint"></a>ブレークポイントの設定

A*ブレークポイント*は Visual Studio が、実行を中断する位置を示すマーカー コードのために、変数の値またはメモリ、またはコードの分岐が実行を取得するかどうかの動作を確認することができます。 デバッグの最も基本的な機能することをお勧めします。

1. 左側の余白をクリックして、ブレークポイントを設定するには`doWork`関数呼び出し (コードとキーを押して行を選択または**f9 キー**)。

    ![ブレークポイントを設定する](../debugger/media/dbg-qs-set-breakpoint.png "ブレークポイントを設定します。")

2. これでキーを押します**f5 キーを押して**(かを選択して**デバッグ > [デバッグ開始]**)。

    ![ブレークポイントにヒット](../debugger/media/dbg-qs-hit-breakpoint.png "ブレークポイントにヒット")

    デバッガーでは、ブレークポイントを設定するが一時停止します。 デバッガーとアプリの実行が一時停止して、ステートメントは黄色の矢印で示されます。 は、行、`doWork`関数呼び出しがまだ実行されていません。

    > [!TIP]
    > ループまたは再帰では、ブレークポイントがある多数のブレークポイントが頻繁にステップを実行する必要がある場合を使用するか、[条件付きブレークポイント](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)を特定の条件が満たされた場合にのみ、コードが中断されるかどうかを確認します。 これは、時間を節約できますもやすくしたり再現が困難な問題をデバッグします。

    アドレスの値 (NULL の検索) を確認するブレークポイントも使用する C++ では、メモリ関連の障害をデバッグするとき、およびカウントを参照します。 

## <a name="navigate-code"></a>コード内を移動します。

続行する、デバッガーに指示するさまざまなコマンドがあります。 Visual Studio 2017 の有用なコード ナビゲーション コマンドを示します。

- ブレークポイントで一時停止、中には、ステートメントを合わせる`c1.push_back(20)`緑まで**をクリックして実行**ボタン![実行 をクリックする](../debugger/media/dbg-tour-run-to-click.png "RunToClick")が表示され、キーを押し、**をクリックして実行**ボタンをクリックします。

    ![クリックして実行](../debugger/media/dbg-qs-run-to-click.png "実行 をクリックするには")

    アプリの実行を継続を呼び出す`doWork`、され、ボタンをクリックしたコードの行で一時停止します。

    使用される共通のキーボード コマンド コードのステップ実行を含める**F10**と**F11**です。 複数の詳細な手順については、次を参照してください。、[ビギナーズ ガイド](../debugger/getting-started-with-the-debugger.md)です。

## <a name="inspect-variables-in-a-datatip"></a>データヒントで変数を検査します。

1. 現在のコード行 (黄色実行ポインターによってマーク) を合わせると、`c1`データヒントを表示する、マウスを持つオブジェクト。

    ![[データヒント] 表示](../debugger/media/dbg-qs-data-tip.png "データヒントを表示")

    データヒントは、の現在の値を表示、`c1`変数のプロパティを検査することができます。 デバッグする場合、予期しない値を表示する場合、おそらく前または呼び出し元の行のコードでバグがあります。 

2. 現在のプロパティ値を見てにデータヒントを展開し、`c1`オブジェクト。

3. 値を表示する継続できるように、データヒントをピン留めする場合`c1`コードを実行するときに、小規模のピン アイコンをクリックします。 (固定したデータヒントは任意の場所に移動できます)。

## <a name="edit-code-and-continue-debugging"></a>コードを編集およびデバッグを続行

デバッグ セッションの途中で、コードでテストを実行する変更を識別する場合、行うことができます、すぎます。

1. 2 番目のインスタンスをクリックして`c2.front()`変更と`c2.front()`に`c2.back()`です。

2. キーを押して**F10** (または**デバッグ > ステップ オーバー**) 何度か、デバッガーを進めるし、編集済みのコードを実行します。

    ![エディット コンティニュ](../debugger/media/dbg-qs-edit-and-continue.gif "エディット コンティニュ")

    **F10 キーを押して**(まだをスキップする、コードが実行される) それらへのステップ インではなく関数経由で、時間が手順デバッガー 1 つのステートメントを進めます。

エディット コンティニュを使用して機能の制限の詳細については、次を参照してください。[エディット コンティニュ](../debugger/edit-and-continue.md)です。

## <a name="next-steps"></a>次の手順

- デバッガーの詳細については、次を参照してください。[デバッガーを起動し、コード内を移動](../debugger/getting-started-with-the-debugger.md)です。
- ブレークポイントの詳細についてを参照してください。[ブレークポイントを使用する](../debugger/using-breakpoints.md)です。

## <a name="see-also"></a>参照  
 [Visual Studio でのデバッグ](../debugger/index.md)  
 [デバッガー機能ツアー](../debugger/debugger-feature-tour.md)
