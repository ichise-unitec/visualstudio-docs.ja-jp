---
title: "コンテナーの既知の問題 | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: heaths
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6edcc59a2d726fbd76fee86b750f21dc468b727e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="known-issues-for-containers"></a>コンテナーの既知の問題

Docker コンテナーに Visual Studio をインストールする場合、いくつかの問題があります。

## <a name="windows-container"></a>Windows コンテナー

Windows コンテナーに Visual Studio Build Tools 2017 をインストールすると、以下の既知の問題が発生します。

* イメージ microsoft/windowsservercore:10.0.14393.1593 に基づいて Visual Studio をコンテナーにインストールできません。 これより古いまたは新しい Windows バージョンでタグ付けされたイメージでは動作します。
* 10.0.14393 より前の Windows SDK バージョンをインストールすることはできません。 一部のパッケージはインストールに失敗し、そのようなパッケージに依存するワークロードは動作しません。
* イメージを構築するときに `-m 2GB` (またはそれ以上) を渡す必要があります。 一部のワークロードではインストール時の既定の 1 GB よりも多くのメモリを必要とします。
* Docker で既定の 20 GB よりも多くのディスクを使用するように構成する必要があります。
* コマンド ラインで `--norestart` を渡す必要があります。 現時点では、コンテナー内から Windows コンテナーを再起動しようとすると、ホストに `ERROR_TOO_MANY_OPEN_FILES` が返されます。

## <a name="build-tools-container"></a>ビルド ツール コンテナー

ビルド ツール コンテナーを使用すると、以下の既知の問題が発生する場合があります。 問題が修正されているどうか、その他の既知の問題があるかどうかについては、https://developercommunity.visualstudio.com を参照してください。

* IntelliTrace はコンテナー内の[一部のシナリオ](https://github.com/Microsoft/vstest/issues/940)では動作しない場合があります。

## <a name="get-support"></a>サポートを受ける
ときには、問題が発生してしまうことがあります。 Visual Studio のインストールが失敗した場合は、「[Troubleshooting Visual Studio 2017 installation and upgrade issues (Visual Studio 2017 のインストールとアップグレードの問題のトラブルシューティング)](troubleshooting-installation-issues.md)」ページをご覧ください。 トラブルシューティングの手順でも解決しない場合は、ライブ チャットでインストールの支援を依頼してください (英語のみ)。 詳細については、[Visual Studio のサポート ページ](https://www.visualstudio.com/vs/support/#talktous)をご覧ください。

他のいくつかのサポート オプションを次に示します。
* Visual Studio インストーラーおよび Visual Studio IDE の両方に表示される [[問題の報告]](../ide/how-to-report-a-problem-with-visual-studio-2017.md) ツールから、製品の問題を Microsoft に報告できます。
* [UserVoice](https://visualstudio.uservoice.com/forums/121579) で、製品に関する提案を投稿できます。
* [Visual Studio 開発者コミュニティ](https://developercommunity.visualstudio.com/)で製品の問題を追跡したり、質問したり、回答を検索したりできます。
* [Gitter コミュニティの Visual Studio に関する掲示板](https://gitter.im/Microsoft/VisualStudio)で、Microsoft や他の Visual Studio 開発者と情報を交換することもできます。  (このオプションでは [GitHub](https://github.com/) アカウントが必要になります)。

## <a name="see-also"></a>関連項目

* [コンテナーにビルド ツールをインストールする](build-tools-container.md)
* [コンテナーの高度な例](advanced-build-tools-container.md)
* [Visual Studio Build Tools 2017 のワークロード ID とコンポーネント ID](workload-component-id-vs-build-tools.md)
