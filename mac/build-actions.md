---
title: "ビルド アクション"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: 78b0e715ca44c613b6a7ee839c0656e301308588
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2017
---
# <a name="build-actions"></a>ビルド アクション 

Visual Studio for Mac プロジェクトのすべてのファイルにビルド アクションが含まれています。これは、ビルド中、ファイルに行われる処理を制御します。 設定するには、下の画像のように、ファイルをクリックし、**[ビルド アクション]** を選択ます。

![](media/projects-and-solutions-image1.png)

C# プロジェクトの一般的ビルド アクションには次のようなものがあります。

* **なし** - このファイルはビルドに含まれていません。IDE から簡単にアクセスできるようにプロジェクトに追加されています。
* **コンパイル** - このファイルはソース ファイルとして C# コンパイラに渡されます。
* **EmbeddedResource** - このファイルはアセンブリに埋め込むリソースとして C# コンパイラに渡されます。 コンパイラに渡されたら、`System.Reflection` 名前空間を利用し、アセンブリからファイルを読むことができます。
* **コンテンツ** - ASP.NET プロジェクトの場合、展開時、このファイルはサイトの一部として追加されます。 Xamarin.iOS プロジェクトと Xamarin.Mac プロジェクトの場合、アプリ バンドルに含まれます。

ソリューション エクスプローラーでは、複数のファイルを選択できます。バンドル アクションを一度に複数のファイルに設定できます。

また、特定のプロジェクトのビルド アクションがあります。 たとえば、Xamarin.iOS プロジェクトには **BundleResource** ビルド アクションがあります。このアクションは、アプリ バンドルの一環としてファイルを追加します。 Xamarin.Android 固有のビルド アクションに関する詳細は、developer.xamarin.com の[ビルド プロセス](https://developer.xamarin.com/guides/android/under_the_hood/build_process/#Build_Actions) ガイドでご覧いただけます。