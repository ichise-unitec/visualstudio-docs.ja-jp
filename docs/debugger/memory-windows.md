---
title: "[メモリ] ウィンドウ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.memory"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "[メモリ 1] ウィンドウ"
  - "文字列 [Visual Studio]、表示"
  - "デバッガー [Visual Studio]、[メモリ] ウィンドウ"
  - "メモリ [Visual Studio]、デバッグ"
  - "デバッグ [Visual Studio]、[メモリ] ウィンドウ"
  - "バッファー、表示"
ms.assetid: 7f7a0439-10e4-4966-bb2d-51f04cda4fe2
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# [メモリ] ウィンドウ
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**\[メモリ\]** ウィンドウには、アプリケーションが使用しているメモリ空間の内容が表示されます。  **\[ウォッチ\]** ウィンドウ、**\[クイック ウォッチ\]** ダイアログ ボックス、**\[自動変数\]** ウィンドウ、および **\[ローカル\]** ウィンドウには、メモリ内の特定の位置に格納された変数の内容が表示されます。  一方、**\[メモリ\]** ウィンドウには大きな画像が表示されます。  これは、ほかのウィンドウではうまく表示されない大きなデータ \(バッファーや長い文字列など\) をチェックする場合に便利です。  ただし、**\[メモリ\]** ウィンドウの機能は、データの表示だけではありません。  \[メモリ\] ウィンドウには、データ、コード、または未使用メモリの不要なランダム ビットを問わず、メモリ空間内のすべての要素が表示されます。  
  
 **\[メモリ\]** ウィンドウは、**\[オプション\]** ダイアログ ボックスの **\[デバッグ\]** ノードで、アドレスレベルのデバッグが有効な場合にのみ、使用できます。  **\[メモリ\]** ウィンドウは、メモリの概念を認識しないスクリプトや SQL などの言語では使用できません。  
  
## \[メモリ\] ウィンドウを開く  
  
#### \[メモリ\] ウィンドウを開くには  
  
1.  デバッグを開始します \(デバッグ モードでない場合\)。  
  
2.  **\[デバッグ\]** メニューの **\[ウィンドウ\]** をポイントします。  **\[メモリ\]** をポイントし、**\[メモリ 1\]**、**\[メモリ 2\]**、**\[メモリ 3\]**、または **\[メモリ 4\]** をクリックします  \([!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] の下位エディションで提供される **\[メモリ\]** ウィンドウは 1 つです。  これらのエディションを使用している場合は、単に **\[メモリ\]** をクリックします\)。  
  
## \[メモリ\] ウィンドウでのページング  
 **\[メモリ\]** ウィンドウには、通常とは動作の異なる垂直スクロール バーがあります。  最近のコンピューターのアドレス空間はきわめて大きくなっており、スクロール バーのつまみをクリックして任意の位置にドラッグすると、簡単に表示範囲から外れてしまいます。  このため、つまみは "スプリング" のようになっており、ドラッグしても常にスクロール バーの中央に戻ります。  ネイティブ コード アプリケーションの場合、1 ページ単位の上下移動はできますが、自由にスクロールすることはできません。  
  
 上位のメモリ アドレスは、ウィンドウの下部に表示されます。  上位アドレスを表示するには、スクロール アップではなくスクロール ダウンする必要があります。  
  
#### メモリ内で 1 ページずつ上下に移動するには  
  
1.  1 ページ下に \(上位メモリ アドレスに\) 移動するには、垂直スクロール バーのつまみの下の部分をクリックします。  
  
2.  1 ページ上に \(下位メモリ アドレスに\) 移動するには、垂直スクロール バーのつまみの上の部分をクリックします。  
  
## メモリ位置の選択  
 ドラッグ アンド ドロップを使用するか、**\[アドレス\]** ボックスで値を編集すると、選択したメモリ内の位置に瞬時に移動できます。  **\[アドレス\]** ボックスには、数値だけでなく、アドレスとして評価される式も指定できます。  既定では、**\[メモリ\]** ウィンドウの **\[アドレス\]** ボックスの式は、プログラムの実行時に再評価されるライブ式として処理されます。  ライブ式は非常に便利です。  たとえば、ポインターが指すメモリを確認するときに使用できます。  
  
#### ドラッグ アンド ドロップを使用してメモリ位置を選択するには  
  
1.  任意のウィンドウで、メモリ アドレス、またはメモリ アドレスを含むポインター変数を選択します。  
  
2.  アドレスまたはポインターを **\[メモリ\]** ウィンドウにドラッグします。  
  
#### メモリ位置を編集して選択するには  
  
1.  **\[メモリ\]** ウィンドウで、**\[アドレス\]** ボックスをクリックします。  
  
2.  表示するアドレスを入力するか貼り付けて、**Enter** キーを押します。  
  
## \[メモリ\] ウィンドウでの情報の表示方法の変更  
 **\[メモリ\]** ウィンドウでのメモリの内容の表示方法をカスタマイズできます。  既定では、メモリの内容は 16 進形式の 1 バイトの整数として表示され、列数は現在のウィンドウ幅によって自動的に決定されます。  
  
#### メモリの内容の表示形式を変更するには  
  
1.  **\[メモリ\]** ウィンドウをマウスの右ボタンでクリックします。  
  
2.  表示形式を選択します。  
  
#### \[メモリ\] ウィンドウの列数を変更するには  
  
1.  **\[メモリ\]** ウィンドウの上部にあるツール バーで、**\[列\]** の一覧を探します。  
  
2.  **\[列\]** の一覧で、表示する列数を選択するか、**\[自動\]** を選択してウィンドウ幅に収まるように列数を自動的に調整させます。  
  
 プログラムの実行時に **\[メモリ\]** ウィンドウの内容が変化しないようにする必要がある場合は、ライブ式の評価をオフにできます。  
  
#### ライブ評価のオンとオフを切り替えるには  
  
1.  **\[メモリ\]** ウィンドウをマウスの右ボタンでクリックします。  
  
2.  ショートカット メニューの **\[自動的に再評価\]** をクリックします。  
  
     ライブ評価がオンになっている場合は、このオプションがオンになっており、クリックするとオフに切り替わります。  ライブ評価がオフになっている場合は、このオプションがオフになっており、クリックするとオンに切り替わります。  
  
 **\[メモリ\]** ウィンドウの上部にあるツール バーの表示\/非表示を切り替えることができます。  ツール バーが非表示になっている間は、\[アドレス\] ボックスや他のツールにはアクセスできません。  
  
#### ツール バーを切り替えるには  
  
1.  **\[メモリ\]** ウィンドウをマウスの右ボタンでクリックします。  
  
2.  ショートカット メニューの **\[ツール バーの表示\]** をクリックします。  
  
     直前の状態に応じて、ツール バーが表示されるか非表示になります。  
  
## メモリ内でポインターを追跡する  
 ネイティブ コード アプリケーションでは、レジスタ名をライブ式として使用できます。  たとえば、スタック ポインターを使用して、スタックを追跡できます。  
  
#### メモリ内でポインターを追跡するには  
  
1.  **\[メモリ\]** ウィンドウの **\[アドレス\]** ボックスに、ポインター式を入力します。  ポインター変数は、現在のスコープ内にあることが必要です。  言語によっては、逆参照が必要な場合があります。  
  
2.  **ENTER** キーを押します。  
  
     ここで **\[ステップ\]** などの実行コマンドを使用すると、ポインターが変化するたびに、表示されるメモリ アドレスが自動的に変化します。  
  
## 参照  
 [デバッガーでのデータ表示](../debugger/viewing-data-in-the-debugger.md)