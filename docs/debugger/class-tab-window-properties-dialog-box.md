---
title: "クラス タブ、ウィンドウのプロパティ ダイアログ ボックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: Window Properties dialog box, Class Tab
ms.assetid: eaec9f07-d580-436d-934d-76c4e59439aa
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cb10cf8a571d37f27244398e6c957c46cee87f8b
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2018
---
# <a name="class-tab-window-properties-dialog-box"></a>[クラス] タブ ([ウィンドウ プロパティ] ダイアログ ボックス)
使用して、**クラス**タブを選択したウィンドウのクラスの情報を表示します。 表示する、[ウィンドウのプロパティ ダイアログ ボックス](../debugger/window-properties-dialog-box.md)にフォーカスを移動する、[ウィンドウ ビュー](../debugger/windows-view.md)ウィンドウです。 ツリーで、ウィンドウの任意のノードを選択し、**プロパティ**から、**ビュー**メニュー。  
  
 次の設定が [利用可能な**クラス**] タブ。  
  
|入力|説明|  
|-----------|-----------------|  
|**クラス名**|このウィンドウ クラスの名前 (または序数)。|  
|**クラスのスタイル**|クラス スタイル コードの組み合わせ。|  
|**クラスのバイト数**|このウィンドウ クラスに関連付けられているアプリケーションに固有のデータ。|  
|**クラスの Atom**|によって返されるクラスを atom、 **RegisterClass**呼び出します。|  
|**インスタンス ハンドル**|クラスを登録したモジュールのインスタンス ハンドル。 インスタンス ハンドルが一意では無効です。|  
|**ウィンドウのバイト数**|このクラスの各ウィンドウに関連付けられている追加のバイト数。 これらのバイトの意味は、アプリケーションによって決まります。 DWORD 形式でのバイト値を表示する を展開します。|  
|**ウィンドウ プロシージャ**|現在のアドレス、 **WndProc**このクラスの windows の関数。 これとは異なります**ウィンドウ プロシージャ**上、**全般** タブ、ウィンドウがサブクラス化された場合。|  
|**メニュー名**|このクラス (メニューがない場合は「なし」) のウィンドウに関連付けられているメイン メニューの名前。|  
|**アイコンのハンドル**|このクラス (アイコンがない場合は「なし」) のウィンドウに関連付けられているアイコンのハンドルです。|  
|**カーソル ハンドル**|このクラス (カーソルが存在しない場合は「なし」) のウィンドウに関連付けられているカーソルのハンドルです。|  
|**背景ブラシ**|このクラスは、または (ブラシが存在しない場合は「なし」) ウィンドウの背景の描画の定義済みの色など * 色のいずれかの windows に関連付けられている背景のブラシのハンドルです。|