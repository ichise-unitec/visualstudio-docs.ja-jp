---
title: "グラフィックス パイプライン ステージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/09/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.graphics.pipeline
ms.assetid: 2bf5c12e-2a00-401c-8163-4e373d08ad3f
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aabfa9551b591b87631100326e328db0511a3ca4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="graphics-pipeline-stages"></a>グラフィックス パイプライン ステージ
[グラフィックス パイプライン ステージ] ウィンドウでは、個々の描画の呼び出しが Direct3D グラフィックス パイプラインの各ステージでどのように変換されるのか理解できます。  
  
 [パイプライン ステージ] ウィンドウを次に示します。  
  
 ![3D オブジェクト パイプライン ステージを通過します。](media/gfx_diag_demo_pipeline_stages_orientation.png)
  
## <a name="understanding-the-graphics-pipeline-stages-window"></a>[グラフィックス パイプライン ステージ] ウィンドウについて  
 [パイプライン ステージ] ウィンドウは、各描画呼び出しについて、グラフィックス パイプラインの各ステージの結果を個別に視覚化します。 通常なら、パイプラインの途中のステージの結果は表示されず、レンダリングの問題が始まった場所を特定することは困難です。 [パイプライン ステージ] ウィンドウでは、各ステージを個別に視覚化することによって、問題が始まった場所がわかりやすくなります。たとえば、頂点シェーダーのステージでオブジェクトが予期せず画面外に描画された時点が簡単にわかります。  
  
 問題が発生したステージを識別したら、その他の Graphics Analyzer ツールを使用して、データがどのように解釈または変換されたかを確認できます。 多くの場合、レンダリングに関してパイプライン ステージで発生する問題は、頂点の書式記述子が不適切であること、シェーダー プログラムでバグが発生していること、または状態が正しく構成されていないことに関連します。  
  
### <a name="links-to-related-graphics-objects"></a>関連するグラフィックス オブジェクトへのリンク  
 場合によっては、描画呼び出しが特定の方法でグラフィックス パイプラインと対話する理由を判断するために、追加のコンテキストが必要になります。 この追加のコンテキストを容易に見つけられるようにするために、[グラフィックス パイプライン ステージ] ウィンドウは、グラフィックス パイプラインで起こっていることに関連する追加のコンテキストを提供する、1 つ以上のオブジェクトにリンクします。  
  
-   Direct3D 12 では、このオブジェクトは通常、コマンドの一覧です。  
  
-   Direct3D 11 では、このオブジェクトは通常、グラフィックス デバイス コンテキストです。  
  
 これらのリンクは、[グラフィックス パイプライン ステージ] ウィンドウの左上隅にある現在のグラフィックス イベントのシグネチャの一部です。 オブジェクトに関する追加の詳細について調べるには、これらのリンク先を表示します。  
  
### <a name="viewing-and-debugging-shader-code"></a>シェーダー コードの表示およびデバッグ  
 [パイプライン ステージ] ウィンドウのそれぞれのステージの下部にあるコントロールを使用して、頂点シェーダー、ハル シェーダー、ドメイン シェーダー、ジオメトリ シェーダー、およびピクセル シェーダーのコードを検証してデバッグできます。  
  
#### <a name="to-view-a-shaders-source-code"></a>シェーダーのソース コードを表示するには  
  
-   **グラフィックス パイプライン ステージ**ウィンドウで、シェーダーに対応するシェーダーのステージを見つけますを確認します。 次に、プレビュー イメージの下には、次のシェーダー ステージのタイトル リンク — たとえば、次のリンク**頂点シェーダー obj:30**頂点シェーダーのソース コードを表示します。  
  
    > [!TIP]
    >  オブジェクト番号**obj:30**、オブジェクト テーブルや [ピクセル履歴] ウィンドウなどの Graphics Analyzer インターフェイス全体でこのシェーダーを識別します。  
  
#### <a name="to-debug-a-shader"></a>シェーダーをデバッグするには  
  
-   **グラフィックス パイプライン ステージ**ウィンドウで、シェーダーに対応するシェーダーのステージの検索をデバッグします。 次に、プレビュー イメージの下に次のように選択します。**デバッグの開始**です。 既定で、HLSL デバッガーへのこのエントリ ポイントは、対応するステージのシェーダーの最初の呼び出しに設定されます。つまり、この描画呼び出し中にシェーダーによって処理される最初のピクセル、頂点、またはプリミティブです。 経由でアクセスできる特定のピクセルまたは頂点のこのシェーダーの呼び出し、**グラフィックス ピクセル履歴**です。  
  
### <a name="the-pipeline-stages"></a>パイプライン ステージ  
 [パイプライン ステージ] ウィンドウには、描画呼び出し中にアクティブであったパイプラインのステージだけが視覚化されます。 グラフィックス パイプラインの各ステージは、前のステージからの入力を変換し、次のステージに結果を渡します。 最初のステージである入力のアセンブラーは、アプリからのインデックスおよび頂点のデータを入力として取得します。最後のステージである出力マージャーは、新しくレンダリングされたピクセルをフレームバッファーの現在の内容と結合するか、ターゲットを出力としてレンダリングして、画面に表示する最終的なイメージを生成します。  
  
> [!NOTE]
>  計算シェーダーがでサポートされていない、**グラフィックス パイプライン ステージ**ウィンドウです。  
  
 **入力アセンブラー**  
 入力アセンブラーは、アプリによって指定されるインデックスと頂点のデータを読み取り、それらをグラフィックス ハードウェア用にアセンブルします。  
  
 [パイプライン ステージ] ウィンドウで、入力アセンブラーの出力がワイヤー フレーム モデルとして視覚化されます。 結果について詳しく見てを選択して**入力アセンブラー**で、**グラフィックス パイプライン ステージ**アセンブルされた頂点をモデル エディターを使用してフル 3D で表示するウィンドウです。  
  
> [!NOTE]
>  場合、`POSITION`セマンティックが存在しない入力アセンブラーの出力で、何も表示、**入力アセンブラー**段階です。  
  
 **頂点シェーダー**  
 頂点シェーダー ステージは、通常、変換、スキンの適用、照明の適用などの操作を実行して、頂点を処理します。 頂点シェーダーは入力として取得するのと同じ数の頂点を生成します。  
  
 [パイプライン ステージ] ウィンドウで、頂点シェーダーの出力がワイヤー フレーム ラスター イメージとして視覚化されます。 結果について詳しく見てを選択して**頂点シェーダー**で、**グラフィックス パイプライン ステージ**イメージ エディターでの処理済みの頂点を表示するウィンドウです。  
  
> [!NOTE]
>  場合、`POSITION`または`SV_POSITION`セマンティックが頂点シェーダーの出力に存在しませんし、何も表示、**頂点シェーダー**段階です。  
  
 **ハル シェーダー** (Direct3D 11 および Direct3D 12 のみ)  
 ハル シェーダーのステージのプロセスは、行、三角形、四角形などの下位画面を定義するポイントを制御します。 出力として、固定機能テセレーション ステージに渡される上位のジオメトリ パッチとパッチ定数を生成します。  
  
 ハル シェーダー ステージは、[パイプライン ステージ] ウィンドウで視覚化されません。  
  
 **テッセレータ ステージ**(Direct3D 11 および Direct3D 12 のみ)  
 テッセレータ ステージは、ハル シェーダーの出力によって表されるドメインを前処理する、機能が固定された (プログラミング不可能な) ハードウェア ユニットです。 出力として、ドメインのサンプリング パターンと、これらのサンプルを接続する小さいプリミティブのセット (ポイント、線、三角形) を作成します。  
  
 テッセレータ ステージは、[パイプライン ステージ] ウィンドウで視覚化されません。  
  
 **ドメイン シェーダー** (Direct3D 11 および Direct3D 12 のみ)  
 ドメイン シェーダー ステージは、ハル シェーダーからの上位ジオメトリ パッチと、テセレーション ステージからのテセレーションの要因をまとめて処理します。 テセレーションの要因には、テッセレータ入力の要因と出力の要因を含めることができます。 出力として、テッセレータの要因に基づいて、出力パッチのポイントの頂点の位置を計算します。  
  
 ドメイン シェーダー ステージは、[パイプライン ステージ] ウィンドウで視覚化されません。  
  
 **ジオメトリ シェーダー**  
 ジオメトリ シェーダー ステージは、点、線、三角形などのプリミティブ一式、および端が隣接するプリミティブの頂点に関する省略可能な頂点データを処理します。 頂点シェーダーとは異なり、ジオメトリ シェーダーが生成するプリミティブは、入力として取得した数より多くても少なくてもかまいません。  
  
 [パイプライン ステージ] ウィンドウで、ジオメトリ シェーダーの出力がワイヤー フレーム ラスター イメージとして視覚化されます。 結果について詳しく見てを選択して**ジオメトリ シェーダー**で、**グラフィックス パイプライン ステージ**イメージ エディターでの処理済みのプリミティブを表示するウィンドウです。  
  
 **ストリーム出力ステージ**  
 ストリーム出力ステージは、ラスタライズする前に変換されたプリミティブを取得し、それをメモリに書き込むことができます。そこからデータをグラフィックス パイプラインの初期段階への入力として再利用したり、CPU によって再び読み取ることができます。  
  
 ストリーム出力ステージは、[パイプライン ステージ] ウィンドウで視覚化されません。  
  
 **ラスタライザー ステージ**  
 ラスタライザー ステージは、スキャン ライン変換を実行することで、ベクター プリミティブ (ポイント、線、三角形) をラスター イメージに変換する、機能が固定した (プログラミング不可能な) ハードウェア ユニットです。 ラスタライズ処理中に、頂点は同種のクリップ領域に変換され、クリップされます。 ピクセル シェーダーは出力としてマップされ、頂点ごとの属性がプリミティブで補間され、ピクセル シェーダーのための準備が完了します。  
  
 ラスタライザー シェーダー ステージは、[パイプライン ステージ] ウィンドウで視覚化されません。  
  
 **ピクセル シェーダー**  
 ピクセル シェーダー ステージは、ラスタライズされたプリミティブと、補間された頂点データをまとめて処理し、色や深度などのピクセル単位の値を生成します。  
  
 [パイプライン ステージ] ウィンドウで、ピクセル シェーダー出力は、フルカラー ラスター イメージとして視覚化されます。 結果について詳しく見てを選択して**ピクセル シェーダー**で、**グラフィックス パイプライン ステージ**イメージ エディターでの処理済みのプリミティブを表示するウィンドウです。  
  
 **出力マージャー**  
 出力マージャー ステージは、新しく描画されるピクセルと、該当するバッファーの既存のコンテンツ (色、深度、ステンシル) の効果を結合し、これらのバッファーで新しい値を生成します。  
  
 [パイプライン ステージ] ウィンドウで、出力マージャー出力は、フルカラー ラスター イメージとして視覚化されます。 結果について詳しく見てを選択して**出力マージャー**で、**グラフィックス パイプライン ステージ** ウィンドウをマージされたフレームバッファーを表示します。  
  
### <a name="vertex-and-geometry-shader-preview"></a>頂点シェーダーとジオメトリ シェーダーのプレビュー  
 頂点またはジオメトリ シェーダーのステージを選択すると、**パイプライン ステージ** ウィンドウで表示できますへの入力呼び出し力シェーダーからの下のパネルです。  ここでは、詳細については、入力アセンブラー ステージによってアセンブルされた後、シェーダーに指定された頂点の一覧があります。  

 ![頂点シェーダー ステージの入力バッファー ビューアー](media/gfx_diag_vertex_shader_inbuffers.png)  
  
 頂点シェーダー ステージの結果を表示するには、頂点シェーダーによって変換された後で、頂点シェーダー ステージ サムネイルを選択して、フルサイズのラスタライズされたメッシュのワイヤー フレームを表示します。  
  
 ![頂点シェーダー ステージの結果プレビュー](media/gfx_diag_vertex_shader_preview.png)  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル: 頂点の網かけによるオブジェクトの不足](walkthrough-missing-objects-due-to-vertex-shading.md)   
 [チュートリアル: 網かけによるレンダリング エラーのデバッグ](walkthrough-debugging-rendering-errors-due-to-shading.md)