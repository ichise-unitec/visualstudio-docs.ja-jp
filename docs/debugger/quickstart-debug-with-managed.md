---
title: "Visual Studio デバッガーを使用してマネージ コードを使用してデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords: debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: aa992c0cdcf5c50208aacc8e16d954f4ee35da13
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="debug-with-managed-code-using-the-visual-studio-debugger"></a>Visual Studio デバッガーを使用してマネージ コードでデバッグします。

Visual Studio デバッガーでは、アプリのデバッグに役立つ多くの強力な機能を提供します。 このトピックでは、いくつかの基本的な機能を説明する簡単な方法を説明します。

## <a name="create-a-new-project"></a>新しいプロジェクトを作成する 

1. Visual Studio で、次のように選択します。**ファイル > 新しいプロジェクト**です。

2. **Visual c#**または**Visual Basic**、選択**.NET Core**、中央のペインの **コンソール アプリケーション (.NET Core)**です。

     **[Console App (.NET Core)]** プロジェクト テンプレートが表示されない場合は、**[新しいプロジェクト]** ダイアログ ボックスの左側のウィンドウにある **[Visual Studio インストーラーを開く]** リンクをクリックします。 Visual Studio インストーラーが起動します。 選択、 **.NET デスクトップ開発**と**.NET Core**ワークロード、順に選択**変更**です。

3. ような名前を入力**MyDbgApp**  をクリック**OK**です。

    Visual Studio では、プロジェクトを作成します。

4. Module1.vb または Program.cs で、次のコードに置き換えます

    ```c#
    class Program
    {
        static void Main(string[] args)
        {
        }
    }
    ```

    ```vb
    Module Module1
        Sub Main()
        End Sub
    End Module
    ```

    このコードでは。

    ```c#
    class Program
    {
        private static void doWork()
        {
            LinkedList<int> c1 = new LinkedList<int>();

            c1.AddLast(10);
            c1.AddLast(20);

            LinkedList<int> c2 = new LinkedList<int>(c1);
            int i = c2.First.Value;
            int j = c2.First.Value;
            Console.Write("The first element is ");
            Console.Write(i);
            Console.Write("\n");
            Console.Write("The second element is ");
            Console.Write(j);
            Console.Write("\n");

        }

        static int Main()
        {
            // using namespace std;
            doWork();
            return 0;

        }
    }
    ```

    ```vb
    Imports System.Collections.Generic

    Namespace MyDbgApp
        Class Program
            Private Shared Sub doWork()
                Dim c1 As New LinkedList(Of Integer)()

                c1.AddLast(10)
                c1.AddLast(20)

                Dim c2 As New LinkedList(Of Integer)(c1)
                Dim i As Integer = c2.First.Value
                Dim j As Integer = c2.First.Value
                Console.Write("The first element is ")
                Console.Write(i)
                Console.Write(vbLf)
                Console.Write("The second element is ")
                Console.Write(j)
                Console.Write(vbLf)

            End Sub

            Public Shared Function Main() As Integer
                ' using namespace std;
                doWork()
                Return 0

            End Function
        End Class
    End Namespace
    ```

    > [!NOTE]
    > Visual Basic でのスタートアップ オブジェクトに設定されていることを確認`Sub Main`(**プロパティ > アプリケーション > スタートアップ オブジェクト**)。

## <a name="set-a-breakpoint"></a>ブレークポイントの設定

A*ブレークポイント*は Visual Studio が、実行を中断する位置を示すマーカー コードのために、変数の値またはメモリ、またはコードの分岐が実行を取得するかどうかの動作を確認することができます。 デバッグの最も基本的な機能することをお勧めします。

1. 左側の余白をクリックして、ブレークポイントを設定するには`doWork`関数呼び出し (コードとキーを押して行を選択または**f9 キー**)。

    ![ブレークポイントを設定する](../debugger/media/dbg-qs-set-breakpoint-csharp.png "ブレークポイントを設定します。")

2. これでキーを押します**f5 キーを押して**(かを選択して**デバッグ > [デバッグ開始]**)。

    ![ブレークポイントにヒット](../debugger/media/dbg-qs-hit-breakpoint-csharp.png "ブレークポイントにヒット")

    デバッガーでは、ブレークポイントを設定するが一時停止します。 デバッガーとアプリの実行が一時停止して、ステートメントは黄色の矢印で示されます。 は、行、`doWork`関数呼び出しがまだ実行されていません。

    > [!TIP]
    > ループまたは再帰では、ブレークポイントがある多数のブレークポイントが頻繁にステップを実行する必要がある場合を使用するか、[条件付きブレークポイント](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)を特定の条件が満たされた場合にのみ、コードが中断されるかどうかを確認します。 これは、時間を節約できますもやすくしたり再現が困難な問題をデバッグします。

## <a name="navigate-code"></a>コード内を移動します。

続行する、デバッガーに指示するさまざまなコマンドがあります。 Visual Studio 2017 の有用なコード ナビゲーション コマンドを示します。

- ブレークポイントで一時停止、中には、ステートメントを合わせる`c1.AddLast(20)`緑まで**をクリックして実行**ボタン![実行 をクリックする](../debugger/media/dbg-tour-run-to-click.png "RunToClick")が表示され、キーを押し、**をクリックして実行**ボタンをクリックします。

    ![クリックして実行](../debugger/media/dbg-qs-run-to-click-csharp.png "実行 をクリックするには")

    アプリの実行を継続を呼び出す`doWork`、され、ボタンをクリックしたコードの行で一時停止します。

    使用される共通のキーボード コマンド コードのステップ実行を含める**F10**と**F11**です。 複数の詳細な手順については、次を参照してください。、[ビギナーズ ガイド](../debugger/getting-started-with-the-debugger.md)です。

## <a name="inspect-variables-in-a-datatip"></a>データヒントで変数を検査します。

1. 現在のコード行 (黄色実行ポインターによってマーク) を合わせると、`c1`データヒントを表示する、マウスを持つオブジェクト。

    ![[データヒント] 表示](../debugger/media/dbg-qs-data-tip-csharp.png "データヒントを表示")

    データヒントは、の現在の値を表示、`c1`変数のプロパティを検査することができます。 デバッグする場合、予期しない値を表示する場合、おそらく前または呼び出し元の行のコードでバグがあります。 

2. 現在のプロパティ値を見てにデータヒントを展開し、`c1`オブジェクト。

3. 値を表示する継続できるように、データヒントをピン留めする場合`c1`コードを実行するときに、小規模のピン アイコンをクリックします。 (固定したデータヒントは任意の場所に移動できます)。

## <a name="edit-code-and-continue-debugging"></a>コードを編集およびデバッグを続行

デバッグ セッションの途中で、コードでテストを実行する変更を識別する場合、行うことができます、すぎます。

1. 2 番目のインスタンスをクリックして`c2.First.Value`変更と`c2.First.Value`に`c2.Last.Value`です。

2. キーを押して**F10** (または**デバッグ > ステップ オーバー**) 何度か、デバッガーを進めるし、編集済みのコードを実行します。

    ![エディット コンティニュ](../debugger/media/dbg-qs-edit-and-continue-csharp.gif "エディット コンティニュ")

    **F10 キーを押して**(まだをスキップする、コードが実行される) それらへのステップ インではなく関数経由で、時間が手順デバッガー 1 つのステートメントを進めます。

エディット コンティニュを使用して機能の制限の詳細については、次を参照してください。[エディット コンティニュ](../debugger/edit-and-continue.md)です。

## <a name="next-steps"></a>次の手順

- デバッガーの詳細については、次を参照してください。[デバッガーを起動し、コード内を移動](../debugger/getting-started-with-the-debugger.md)です。
- ブレークポイントの詳細についてを参照してください。[ブレークポイントを使用する](../debugger/using-breakpoints.md)です。

## <a name="see-also"></a>参照  
 [Visual Studio でのデバッグ](../debugger/index.md)  
 [デバッガー機能ツアー](../debugger/debugger-feature-tour.md)
