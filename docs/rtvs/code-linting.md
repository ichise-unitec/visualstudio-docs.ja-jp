---
title: "R Tools for Visual Studio で R コードを lint する | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
f1_keywords: vs.toolsoptionspages.text_editor.r.lint
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: data-science
ms.openlocfilehash: 76f4ceb040e62e4ebac46e8a791f5dac0d73aff5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="linting-r-code-in-visual-studio"></a>Visual Studio で R コードを lint する

lint とは、潜在的なエラーに加えて、書式設定の問題やコード ファイル内での他のノイズ (見かけ上の空白文字など) を明らかにするためにコードを分析するプロセスです。 lint はまた、識別子の名前付けの方法など、特定のコーディング規則を推奨するのに役立ち、チーム内やその他の状況で共同作業を行う場合に便利です。

R Tools for Visual Studio (RTVS) は、R 用に組み込みの lint を備えており、lint の動作はさまざまなオプションを介して制御されます。 これらのオプションにアクセスするには、**[ツール]、[オプション]、[テキスト エディター]、[Lint]** の順に選択します。

既定では、lint は無効になっています。 lint を有効にするには、**[すべて]、[int の有効化]** オプションの順に進み、このオプションを true に設定します。 このトピックの以降のセクションでは、その他のすべての lint オプションについて説明します。

lint が有効になると、エディター内で入力中に lint が適用されます。 問題は緑色の波線で表示されます。 たとえば、次の図では、RTVS によって 6 つの lint の問題が明らかにされています。具体的には、代入で `<-` ではなく `=` が使用されている、関数の引数の前後にスペースが不足している、パスカル ケースおよび大文字の識別子が使用されている、セミコロンが使用されているなどの問題です。 問題にマウス ポインターを合わせると、説明が表示されます。

![R コードの lint の例](media/linting-01.png)

## <a name="assignment-group"></a>代入グループ

| オプション | 既定値 | lint の結果 |
| --- | --- | --- |
| \<- の適用 | `True` | 代入で `<-` が使用されていない場合を識別します。 |

## <a name="naming-group"></a>名前付けグループ

次のオプションは、別の名前付け規則が使用されている識別子にフラグを設定します。

| オプション | 既定値 | lint の結果 |
| --- | --- | --- |
| キャメル ケースにフラグを付ける | `False` | キャメル ケースを使用している識別子にフラグを設定します。 |
| 長い名前にフラグを付ける | `False` | [名前の最大長] の設定の値を超える長さの名前が付けられている識別子にフラグを設定します。 |
| 複数のドットにフラグを付ける | `True` | 複数のドットを使用している識別子にフラグを設定します。 |
| パスカル ケースにフラグを付ける | `True` | パスカル ケースを使用している識別子にフラグを設定します。 |
| スネーク ケースにフラグを付ける | `False` | アンダー スコアを使用している識別子にフラグを設定します。 |
| 大文字にフラグを付ける | `True` | すべて大文字を使用している識別子にフラグを設定します。 |
| 名前の最大長 | 32 | [長い名前にフラグを付ける] の設定で、この長さが適用されます。 |

## <a name="spacing-group"></a>スペース グループ

これらのオプションでは (既定ではすべてが `True` に設定されている)、リンターがスペースの問題を識別する場所を制御します: 関数名の後、コンマの前後、演算子の前後、左中かっこおよび右中かっこの位置、( の前のスペース、() 内のスペース。

## <a name="statements-group"></a>ステートメント グループ

| オプション | 既定値 | lint の結果 |
| --- | --- | --- |
| 複数 | `True` | 同一行に複数のステートメントが存在する場合を識別します。 |
| セミコロン | `True` | セミコロンの使用を識別します。 |

## <a name="text-group"></a>テキスト グループ

| オプション | 既定値 | lint の結果 |
| --- | --- | --- |
| 行の長さの制限 | `False` | [行の最大長] オプションの値よりも長い行にリンターでフラグを付けるかどうかを設定します。 |
| 行の最大長 | 80 | [行の長さの制限] オプションによって適用される行の長さを設定します。 |

## <a name="whitespace-group"></a>空白グループ

これらのオプションでは (既定ではすべてが `True` に設定されている)、リンターが空白の問題を識別する場所を制御します: タブの使用、二重引用符の使用、末尾の空の行の使用、末尾の空白の使用。