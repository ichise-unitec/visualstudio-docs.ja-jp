---
title: "[その他の XML、テキスト エディター オプション] ダイアログ ボックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd3fff31-cddc-422d-a2f0-a5a1ef492afd
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4773bf87e89bd504b477d9a1a31dfe961a3f29ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="miscellaneous-xml-text-editor-options-dialog-box"></a>[その他] ([オプション] ダイアログ ボックス - [テキスト エディター] - [XML])
このダイアログ ボックスでは、XML エディターのオートコンプリートとスキーマの設定を変更することができます。 アクセスすることができます、**オプション**からダイアログ ボックス、**ツール**メニュー。  
  
> [!NOTE]
>  選択すると、これらの設定は使用可能な**テキスト エディター**フォルダー、 **XML**フォルダー、し、 **その他**オプションを**のオプション**  ダイアログ ボックス。  
  
## <a name="auto-insert"></a>自動挿入  
 **終了タグ**  
 オートコンプリート設定がオンのときに、タグが既に閉じられていない場合には、開始タグを閉じるためにユーザーが右山かっこ (>) を入力すると、エディターによって自動的に終了タグが追加されます。 これが既定の動作です。  
  
 空の要素の完了は、オートコンプリート設定に依存するわけではありません。 バックスラッシュ (/) を入力することで、いつでも空の要素をオートコンプリートできます。  
  
 **属性値の引用符**  
 XML 属性の作成時にエディターは `=" "` という文字を挿入し、二重引用符の内側にキャレット (^) を配置します。  
  
 既定でオンになっています。  
  
 **名前空間の宣言**  
 エディターは、必要に応じて名前空間の宣言を自動的に挿入します。  
  
 既定でオンになっています。  
  
 **その他のマークアップ (コメント、CDATA)**  
 コメント、CDATA、DOCTYPE、処理命令、およびその他のマークアップのオートコンプリートを有効にします。  
  
 既定でオンになっています。  
  
## <a name="network"></a>ネットワーク  
 **Dtd とスキーマを自動的にダウンロードします。**  
 HTTP の場所から、スキーマやドキュメント型定義 (DTD) を自動的にダウンロードします。 この機能は、プロキシ サーバーの自動検出を有効にした System.Net を使用します。  
  
 既定でオンになっています。  
  
## <a name="outlining"></a>アウトライン  
 **[ファイルが開かれたときにアウトライン モードを実行する]**  
 ファイルが開かれたときにアウトライン機能をオンにします。  
  
 既定でオンになっています。  
  
## <a name="caching"></a>キャッシュ  
 **スキーマ**  
 スキーマ キャッシュの場所を指定します。 参照ボタン (**.**) が表示されます、**ディレクトリの参照** ダイアログ ボックスで、現在のスキーマ キャッシュの場所。 別のディレクトリを選択またはダイアログ ボックスで、フォルダーを選択することができます右クリックしを選択し、**開く**ディレクトリに参照してください。  
  
## <a name="see-also"></a>参照  
 [XML ドキュメントのプロパティと [プロパティ] ウィンドウ](../xml-tools/xml-document-properties-properties-window.md)   
 [XML エディターのコンポーネント](../xml-tools/xml-editor-components.md)